---
title: "ATA(Advanced Threat Analytics) 공격 시뮬레이션 플레이북"
description: "이 가이드를 통해 고객들은 Windows 운영 체제에 대한 자격 증명 도용 공격, 공개적으로 사용 가능한 연구 도구를 사용하여 이러한 작업을 수행하는 방법 및 Microsoft ATA가 이러한 위협을 감지하는 방법 등을 알 수 있습니다."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 03/13/2017
ms.topic: solution
ms.prod: 
ms.service: advanced-threat-analytics
ms.technology: techgroup-identity
ms.assetid: da5eda7c-29bb-429f-9366-72495667c010
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cff5b87f6c5d0b9aa987631fefe5bf74e3a43862
ms.openlocfilehash: 41672ccdbd2c868add70e423b7dbc8048713259b
ms.lasthandoff: 03/14/2017


---

# <a name="advanced-threat-analytics-attack-simulation-playbook"></a>ATA(Advanced Threat Analytics) 공격 시뮬레이션 플레이북

이 가이드는 Pass-the-Hash, Pass-the-Ticket, Overpass-the-Hash 등과 같은 자격 증명 도용 및 공개적으로 사용 가능한 연구 도구를 사용하여 이러한 작업을 수행하는 방법에 대해 알아볼 수 있도록 도와줍니다. 이 시뮬레이션 플레이북은 공격자가 사용하는 유효한 인터넷 도구로 작성된 시나리오를 기반으로 하며, 그래프형 사고 방식으로 공격자처럼 생각하고 도용한 자격 증명으로 환경 내에서 이동하며, Microsoft ATA(Advanced Threat Analytics)를 사용하여 사용자 환경에서 이러한 활동을 감지하는 방법을 보여주기 위해서 제공됩니다.

이 가이드에 나와 있는 공격 시나리오는 다음과 같습니다.

- DNS 정찰
- 디렉터리 서비스 열거
- SMB 세션 열거
- 자격 증명 수집(lsass.exe)
- Overpass-the-Hash
- Pass-the-Ticket
- 원격 코드 실행
- 스켈레톤 키
- DC 동기화

> [!IMPORTANT]
> 이 가이드에 제공되는 단계는 랩 환경에서만 수행해야 합니다. 프로덕션 환경에서는 수행하면 안 됩니다.

## <a name="configuring-your-lab-environment"></a>랩 환경 구성

뒷부분의 실험을 비롯하여 모든 실험에서 이러한 지침을 자세히 따르는 것이 좋습니다.  수행할 몇 가지 설정, 특히&4;대의 컴퓨터,&3;명의 사용자 및 일부 연구 소프트웨어는 인터넷을 차단할 수 있습니다.

ATA를 설치하고 90일 평가판을 구하는 방법에 대한 자세한 내용은 [Advanced Threat Analytics 평가판](http://aka.ms/ataeval)을 참조하십시오. 

> [!IMPORTANT]
> 이 가이드는 ATA 1.7 버전을 기준으로 작성되었습니다.


### <a name="scenario"></a>시나리오

이 랩의 예에서는 JeffV가 자신의 워크스테이션 관리자입니다.  많은 IT 상점에서는 관리자 권한으로 실행되는 사용자 계층이 여전히 존재합니다.  이 시나리오에서는 악의적 사용자가 침입 후 작업을 수행할 환경에서 관리자 액세스 권한을 이미 가지고 있기 때문에 로컬 권한 상승 공격이 필요하지 않습니다. 
 
그러나 IT 상점에서 관리자가 아닌 계정을 사용하여 권한을 축소하는 경우에도 로컬 권한 상승을 위해 다른 형태의 공격(알려진 응용 프로그램 취약점, 제로 데이 등)이 실행됩니다. 이 경우 이 가이드에서는 악의적 사용자가 Victim-PC에서 로컬 권한 상승을 수행했다고 가정합니다.  이 가상 랩에서는 JeffV에게 스피어피싱 전자 메일을 보내 이 작업이 수행되었습니다. 자세한 내용은 이 가이드의 뒷부분에 설명되어 있습니다.


### <a name="servers-and-workstations"></a>서버 및 워크스테이션

아래에는 필요한 컴퓨터 및 이 연습에서 사용된 구성이 나와 있습니다.  이러한 컴퓨터는 모두 Windows 10 Hyper-V에서 게스트 가상 컴퓨터(VM)로 준비됩니다.  아래 구성을 따르는 경우(권장) VM을 동일한 가상 스위치에 배치해야 합니다.

| FQDN | OS | IP | 용도 |
| --- | --- | --- | --- |
| DC1.contoso.local | Windows Server 2012 R2 | 192.168.10.10 | ATA LWGW(Lightweight Gateway)가 설치된 도메인 컨트롤러 |
| ATACenter.contoso.local | Windows Server 2012 R2 | 192.168.10.20 | ATA Center |
| Admin-PC.contoso.local | Windows 7 Enterprise | 192.168.10.30 | 관리자 PC |
| Victim-PC.contoso.local | Windows 7 Enterprise | 192.168.10.31 | 공격 대상자 PC |

이 랩의 도메인 이름은 "CONTOSO.LOCAL"입니다. 도메인을 만든 다음 이 컴퓨터를 도메인에 가입시킵니다. 네 대의 컴퓨터가 모두 가동되고 도메인에 가입되면 다음 섹션으로 이동하여 가상의 사용자를 환경에 추가합니다.


### <a name="users-configuration"></a>사용자 구성

이제 Helpdesk 및 Domain Administrators에 대해 다양한 역할을 만듭니다.  이러한 역할을 만드는 의도는 직무를 분리하기 위해서지만 환경 간 이 두 그룹을 초월하는 보안 종속성을 이해하는 것이 까다롭기 때문에 자격 증명 도용, 측면 확대 또는 도메인 권한 상승을 방지하기에는 이 방법이 충분하지 않다는 것을 이 가이드의 뒷부분에서 확인하게 됩니다. 

먼저 도메인에서 다음 사용자를 만듭니다. 

| Name | 멤버 | 용도 |
| --- | --- | --- |
| 지원 센터 | RonHD | Contoso.local의 클라이언트를 관리합니다. |

이제 한 특정 구성원으로 다음 보안 그룹을 만듭니다.

| 전체 이름 | SAMAccount | 용도 |
| --- | --- | --- |
| Jeff Victim | JeffV | 또 다른 매우 실질적인 스피어피싱 공격의 대상자 |
| Ron HD | RonHD | Ron은 Contoso의 IT 상점에서 무엇이든 해결해 주는 사람으로,  RonHD는 "Helpdesk" 보안 그룹의 구성원입니다. |
| Nuck Chorris | NuckC | 지금까지는 존재하지 않는다고 생각했지만  Contoso에서 *도메인 관리자*입니다. |

> [!IMPORTANT]
> 계속 진행하기 전에 *RonHD*이 *Helpdesk* 보안 그룹에 구성원으로 추가되었는지 확인합니다.


Contoso의 도메인 관리자인 Nuck Chorris는 *Admin-PC* 워크스테이션을 사용합니다. 또한 *Helpdesk* 보안 그룹(*RonHD*이 구성원인 그룹)에서 *NuckC* 컴퓨터를 관리합니다.  이 구성은 [제한된 그룹](https://support.microsoft.com/kb/279301)을 통해 지정할 수 있습니다. 관리자의 그룹 속성 화면은 다음과 비슷합니다.

![관리자 속성](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig1.png)

또한 *JeffV*는 대부분의 IT 상점에서와 마찬가지로 자신의 장치(*Victim-PC*)에서 관리자로 추가되었습니다.  이 작업은 의도적으로 수행되었으며 이 문서의 뒷부분에서 설명합니다. 로컬 관리자의 그룹 속성 화면은 다음과 비슷합니다.

![관리자 속성 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig2.png)


### <a name="security-research-tools"></a>보안 연구 도구

이 랩을 구성하려면 도구를 *Victim-PC* 컴퓨터에 다운로드한 후 *C:\tools*에 설치해야 합니다.

- [Mimikatz](https://github.com/gentilkiwi/mimikatz)
- [PowerSploit](https://github.com/PowerShellMafia/PowerSploit)
- [PsExec](https://technet.microsoft.com/en-us/pxexec) 
- [NetSess.exe](http://www.joeware.net/freetools)

도구 폴더 화면은 다음과 비슷합니다.

![관리자 속성](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig3.png)


> [!IMPORTANT]
> 이러한 도구는 연구용으로만 사용됩니다.  Microsoft에서는 이러한 도구를 소유하지 않으며 해당 도구의 동작을 보장하지도 않습니다.  따라서 이러한 도구는 테스트 랩 환경에서만 실행해야 합니다.

이 랩의 목적에 따라 *Victim-PC* 컴퓨터에서 모든 바이러스 백신 프로그램을 종료합니다. 바이러스 백신 프로그램을 종료하는 것이 결과를 왜곡하는 것처럼 보일 수 있지만 이러한 도구의 소스 코드는 무료로 사용할 수 있으므로 공격자가 바이러스 백신 프로그램 서명 기반 감지를 피하기 위해 소스 코드를 수정할 수 있습니다. 또한 악의적 사용자는 컴퓨터에서 로컬 관리자 권한을 얻자마자 바이러스 백신 프로그램을 보다 쉽게 우회할 수 있습니다.  이 시점의 목표는 나머지 조직을 보호하는 것입니다. 손상된 하나의 컴퓨터로 인해 도메인 권한 상승 및 도메인 손상이 야기되면 안 됩니다.

### <a name="environment-topology"></a>환경 토폴로지

이 시점에서 랩 화면은 다음과 비슷합니다.

![토폴로지](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig4.png)

이 가이드의 앞 부분에서 언급했듯이 *Domain Admins* 및 *Helpdesk*의 역할은 서로 다르지만 데모 동안 악의적 사용자가 쉽게 이용할 수 있는 연구 도구로 전체 환경을 악용하는 데 필요한 것은 단지 하나의 보안 종속성 연결고리라는 것을 알게 될 것입니다(이 경우 사용자 *RonHD*).

### <a name="helpdesk-simulation"></a>지원 센터 시뮬레이션

지원 센터 직원이 다른 컴퓨터에 로그인하는 일반적인 지원 센터 시나리오를 시뮬레이트하려면 *RonHD*로 *Victim-PC*에 로그인한 다음 *JeffV*로 다시 로그인하십시오.  이 워크스테이션에서 권한 있는 자격 증명 관리를 시뮬레이트하려면 "사용자 전환" 메커니즘을 사용하십시오.

![사용자 전환](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig5.png)


이 랩에서 다른 방법으로도 이 관리 워크플로를 시뮬레이트할 수 있습니다(예: 명령줄에서 배치 스크립트 서비스 계정, 예약된 작업, RDP 세션 또는 'runas' 만들기).  보안 작업에서는 누군가 또는 어떠한 대상이 이러한 리소스를 관리해야 하며, 관리란 로컬 관리자 권한을 의미합니다. 이 랩의 목적을 고려하면서 시간을 최적화하기 위해 이 워크플로를 시뮬레이트하는 가장 빠른 방법이 선택되었습니다.

> [!IMPORTANT]
> 이 시점에서 *Victim-PC*를 로그아웃하거나 다시 시작하지 마십시오. 그럴 경우 메모리에서 *RonHD*의 자격 증명이 지워지고 *지원 센터* 시나리오를 다시 재현해야 합니다. 

아래 표에는 각 컴퓨터에 저장된 자격 증명이 요약되어 있습니다.

| 컴퓨터 | 컴퓨터에 저장된 자격 증명 |
| --- | --- |
| Admin-PC | - NuckC |
| Victim-PC | - JeffV 및 RonHD(지원 센터 시나리오를 통해 만들어짐) |

이 시점에서 랩 환경이 준비되어 있습니다. 현재 랩 상태는 도메인 손상으로부터&1;-exploit-away(#&1;ea)인 위치에 있습니다.  다음으로, 단일 손상이 일반적으로 멈출 줄 모르는 의욕을 가진 악의적 사용자에 의해 인터넷에서 액세스할 수 있는 응용 프로그램을 대상으로 사용자 환경 내 가장 낮은 권한 수준의 자산에서 발생한다는 것을 알 수 있습니다.  이 시점에서 [침입 가정](https://blogs.msdn.microsoft.com/azuresecurity/2015/10/19/an-insiders-look-at-the-security-of-microsoft-azure-assume-the-breach/) 방법론이 대두되는 것입니다.

## <a name="executing-the-attack"></a>공격 실행

이 가이드의 이 섹션에서는 실제 도구를 사용하고 악의적 사용자의 침입 후 활동을 시뮬레이트합니다.

### <a name="beachhead-via-spearphish"></a>스피어피싱을 통한 Beachhead

이 공격 시뮬레이션의 경우, 악의적 사용자가 환경의 특정 컴퓨터에서 로컬 관리자 권한을 획득했다고 가정됩니다.  이 동작은 다른 방법을 사용하여 수행될 수도 있지만, 조직에 대한 스피어피싱 캠페인을 통해 수행되는 경우가 많습니다. 

[Microsoft Security Intelligence Report Volume 21](https://www.microsoft.com/security/sir/default.aspx)에서는 PROMETHIUM 및 NEODYNIUM이라는 두 개의 다른 행위자 그룹에 대해 논의했습니다. 두 활동 그룹 모두 대상 환경에서 발판을 마련하기 위해 스피어피싱에 참여합니다.  그 이유는 무엇일까요?  전자 메일은 공격자의 관점에서 조직의 네트워크 방어를 우회하는 빠른 방법입니다. 아래 이미지에 Microsoft의 Threat Intelligence Center에 보고된, 해킹 및 응답된 실제 스피어피싱 전자 메일의 예가 나와 있습니다.

![스피어피싱 전자 메일](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig6.png)


보안 환경에서는 단일 호스트가 손실되어도 전체 도메인이나 포리스트 손상으로 이어지지 않습니다.  악의적 사용자의 다음 단계를 감지하는 것은 "침입 후" 영역에서 필수적입니다.

### <a name="reconnaissance"></a>정찰

악의적인 사용자가 환경에 들어오면 정찰을 시작합니다.  이 단계에서 악의적 사용자는 설정 및 관심 있는 컴퓨터를 검색하고, 보안 그룹 및 관심 있는 기타 활성 디렉터리 개체를 열거하는 등 환경을 연구하는 데 시간을 할애하여 자신의 목적에 따라 사용자 환경을 구축합니다.

#### <a name="dns-reconnaissance"></a>DNS 정찰

대부분의 악의적 사용자가 수행할 첫 번째 작업 중 하나는 DNS에서 모든 내용을 수신하려고 시도하는 것이며 Microsoft ATA는 이 작업을 감지할 수 있습니다.

Victim-PC에서 악의적 사용자가 방금 손상한 PC와 사용자인 JeffV 자격 증명을 사용하여 로그인하여 DNS 정찰을 시작하고 다음 명령을 실행합니다. 
    
    nslookup
    ls -d contoso.local

결과 화면은 다음과 비슷합니다.

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig7.png)

이 랩에서 도메인에 대해 이 DNS 덤프 작업을 차단하도록 DNS가 구성됩니다. 하지만 불행하게도 이 이벤트는 네트워크 노이즈에서 무시되거나 손실되는 경우가 많아 네트워크 방어자는 악의적 사용자가 자신의 환경에서 일정 수준의 액세스 수준에 도달했음을 깨닫지 못하게 되고 더욱 공격적인 공격이 시작되는 상태에 놓이게 됩니다.

Microsoft ATA는 아래와 같이 의심스러운 DNS 활동에 대해 플래그를 지정하여 이러한 유형의 공격을 감지합니다.

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig8.png)

ATA는 DNS 트래픽의 구문을 계속 분석하므로 성공 여부에 관계없이 덤프 요청을 확인할 수 있습니다.  의심스러운 활동이 합법적이고 이 활동의 출처가 승인된 DNS 검사 장치인 경우, 향후 이 이벤트를 통해 교훈을 얻을 수도 있습니다.

이 경우 악의적 사용자로서는 DNS 덤프 수행 후 다른 정찰 기법으로 이동하는, 공격의 기회를 차단당한 셈입니다.

> [!IMPORTANT]
> 실패를 감지하는 것은 환경에 대한 성공적인 공격을 감지하는 것만큼이나 통찰력을 제공합니다.
 
위에 표시된 ATA 경고 메시지의 의심스러운 활동에 파란색 물방울 모양이 표시될 수 있습니다. 이는 소비된 데이터와 분석가의 피드백 둘 다를 바탕으로 ATA가 지속적으로 학습하고 있음을 의미합니다.  분석가 피드백은 ATA 및 의심스러운 활동 감지를 사용자 환경에 맞게 사용자 정의하여 시간이 지남에 따라 양성으로 확인되는 활동을 제거하고 노이즈를 줄이는 데 도움이 됩니다.

#### <a name="directory-services-enumeration"></a>디렉터리 서비스 열거

[SAMR(Security Account Manager Remote Protocol)](https://msdn.microsoft.com/library/cc245477.aspx)은 도메인의 사용자 및 그룹에 관리 기능을 제공합니다.  사용자, 그룹 및 권한 간의 관계를 파악하고 있는 것은 악의적 사용자에게 매우 중요할 수 있습니다.  인증된 모든 사용자는 이러한 명령을 실행할 수 있습니다. SAMR 설정 및 해당 정찰을 Local Administrators 그룹의 구성원인 사용자에게만 제한하는 방법에 대한 자세한 내용은 [이 백서](https://gallery.technet.microsoft.com/SAMRi10-Hardening-Remote-48d94b5b#content)를 참조하십시오.

#### <a name="enumerate-all-users-and-groups"></a>모든 사용자 및 그룹 열거

사용자와 그룹을 열거하는 것은 악의적 사용자에게 매우 유용합니다.  사용자 이름과 그룹 이름을 아는 것도 유용할 수 있습니다.  공격자는 정찰 단계에서 가능한 한 많은 정보를 얻고자 합니다.

사용자 및 그룹의 열거를 시뮬레이트하려면 손상된 *JeffV* 계정을 사용하여 *Victim-PC*에 로그인해야 합니다. 로그인하면 다음 명령을 사용하여 모든 도메인 사용자 및 그룹을 가져오려고 시도합니다.

    net user /domain
    net group /domain

첫 번째 명령의 결과 예가 아래 이미지에 나와 있습니다.

![Net 사용자](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig9.png)

두 번째 명령의 결과 예가 아래 이미지에 나와 있습니다.

![Net 그룹](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig10.png)

이러한 작업이 문제없이 성공하는 이유는 합법적인 자격 증명을 사용하여 수행되었기 때문입니다. 문제는 이제 공격자가 환경의 모든 사용자와 그룹을 알고 있다는 것입니다. Microsoft ATA와 같은 도구가 없었다면 이러한 상황을 아무도 인식하지 못하고 넘어갈 수 있습니다.

이 작업에서 Microsoft ATA는 공격을 나타내는 경고에 대해 플래그를 지정하고 공격자가 얻을 수 있는 데이터도 표시합니다

![정찰](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig11.png)

#### <a name="enumerate-high-privileged-accounts"></a>권한 수준이 높은 계정 열거

이 시점에서 공격자는 사용자 목록과 그룹 목록을 모두 보유합니다.  그러나 누가 어느 그룹에 속하는지 파악하는 것도 중요합니다. 특히 *Enterprise Admins* 및 *Domain Admins*와 같이 권한 수준이 높은 그룹의 경우 중요합니다. 랩 환경에서 이 정보를 얻으려면 *Victim-PC*에서 *JeffV*로 로그인하고 아래 명령을 실행합니다.

    net group “domain admins” /domain

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![Net 그룹 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig12.png)

공격자는 이제 모든 사용자와 그룹을 보유하며 어느 사용자가 권한 수준이 높은 *Domain Admins* 그룹에 속해 있는지 알고 있습니다. 실제 시나리오에서는 *Enterprise Admins*와 *Domain Admins* 간에 보안 경계가 없기 때문에 공격이 계속 확대되고 Enterprise Admins에 속한 사용자를 얻으려고 할 가능성이 매우 높습니다.

> [!IMPORTANT]
> 포리스트와 도메인 간 보안 경계, Enterprise Admins와 Domain Admins 간 보안 경계 및 기타 "계층-0" 수준 권한에 대한 자세한 내용은 [권한 있는 액세스 보안 참조 자료](http://www.aka.ms/tier0)를 참조하십시오.

랩에서 *Enterprise Admins* 그룹의 구성원 목록을 가져오려면 *Victim-PC*에서 다음 명령을 실행합니다.

    net group “enterprise admins” /domain

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![Net 그룹 3](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig13.png)

위에 표시된 예에서 *Enterprise Admins* 그룹에는 하나의 계정이 있습니다. 이 경우 이는 기본값이기 때문에 매우 유용한 정보는 아닐 수 있지만 공격자는 계정에 대해 훨씬 많은 지식을 보유하게 되고 자격 증명을 손상시키려는 사용자를 식별하게 됩니다.

### <a name="smb-session-enumeration"></a>SMB 세션 열거

이 시점에서 공격자는 자격 증명을 손상시키고자 하는 사람을 알고 있지만 현재 정보를 통해 자격 증명을 손상시키는 방법을 정확하게 알지 못합니다. SMB 열거를 사용하면 이러한 계정이 노출된 정확한 위치를 얻을 수 있습니다.

인증된 모든 사용자가 도메인 컨트롤러에 연결하여 SMB 열거를 공격자에게 유용한 도구로 만들어주는 SYSVOL에 대한 그룹 정책을 처리해야 합니다. 이렇게 하면 DC(Domain Controllers) 주요 대상이 SMB 열거를 수행할 수 있습니다.

랩의 이 부분에서는 인터넷에서 다운로드한 첫 번째 연구 도구인 *NetSess*를 사용합니다.  *NetSess*는 지정된 로컬 또는 원격 컴퓨터에서 NetBIOS 세션을 열거하는 명령줄 도구입니다.  

특정 컴퓨터(이 경우에는 *Victim-PC*의 DC)에 연결된 사용자를 열거하려면 NetSess가 로컬에 저장된 위치로 이동하여 다음 명령을 실행합니다.

    NetSess.exe dc1.contoso.local

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![NetSess](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig14.png)

이러한 종류의 정찰은 방화벽과 같은 전통적인 보안 컨트롤로는 찾아내기가 어렵습니다. 이 공격의 성공 가능성을 높이기 위해 SMB 프로토콜이 IT 상점에서 널리 사용되고 있으며, 이 프로토콜은 Active Directory가 많은 작업에 사용하는 프로토콜입니다. Microsoft ATA는 SMB 세션 열거 활동을 감지하고 노출된 계정을 알리는 경고를 트리거할 수 있습니다.

Microsoft ATA를 사용하면 공격자와 동일한 관련 데이터를 가져올 수 있습니다. 원본 계정, 원본 컴퓨터, 노출된 계정 및 악의적 사용자 열거 당시의 IP 주소 등을 확인할 수 있습니다. 다음 화면에서 예를 확인할 수 있습니다.

![SMB](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig15.png)

Microsoft ATA가 제공하는 데이터는 보안 인식을 향상시키는 데 중요하며 공격에 보다 신속하게 대응할 수 있도록 도와줍니다.

### <a name="lateral-movement"></a>측면 확대

이 단계의 목표는 *NuckC*의 컴퓨터 자격 증명이 노출된, 이전에 검색된 IP 주소(192.168.10.30)에 액세스하는 것입니다. 이 작업을 수행하려면 *Victim-PC*에 있는 메모리 내 자격 증명을 열거합니다. *Victim-PC*가 *JeffV*의 자격 증명에만 노출된 것은 아닙니다. 공격자가 검색하는 데 유용할 수 있는 여러 다른 계정이 있습니다. 


*Victim-PC*에서 자격 증명을 추출하려면 인터넷에서 다운로드한 또 다른 연구 도구인 mimikatz를 사용합니다. *Victim-PC*의 상승된 명령 프롬프트에서 *Mimikatz*가 저장된 도구 폴더로 이동한 후 다음 명령을 실행합니다.

    mimikatz.exe “privilege::debug” “sekurlsa::logonpasswords” “exit” >> c:\temp\victim-pc.txt

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig16.png)

위의 명령은 mimikatz를 실행합니다. 그러면 mimikatz는 메모리에서 자격 증명을 수집합니다.  이 도구는 이 자격 증명을 "victim-pc.txt"라는 텍스트 파일에 기록합니다. “victim-pc.txt” 파일을 열어 검색할 수 있는 내용을 확인합니다.

다음 단계는 *mimikatz*의 자격 증명 덤프 출력의 구문을 분석하는 것입니다. 이를 수행하기 위해 "victim-pc.txt" 파일을 메모장에서 열어야 합니다.  다른 암호가 사용되었거나 기본 설정이 켜져 있거나 꺼져 있는 잠재적으로 다른 운영 체제를 사용할 수 있으므로 파일 내용이 아래 예와 다르게 표시될 수 있습니다.

![출력](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig17.png)

이 샘플 출력에 따라 공격자는 JeffV의 자격 증명을 검색하여 JeffV로 가장할 수 있습니다. 공격자는 또한 사용자 계정과 마찬가지로 다른 컴퓨터의 *Local Admin* 그룹 및 기타 높은 권한 수준의 보안 그룹에 추가할 수 있는 컴퓨터 계정을 발견했습니다.  이 시나리오에서는 해당하지 않지만 *컴퓨터 계정*은 다른 곳에서도 권한에 매핑될 수 있다는 점을 항상 염두에 두어야 합니다.

아래 예에서 공격자가 잠재적으로 관심 있어 하는 계정인 *RonHD*도 검색했음을 알 수 있습니다. *RonHD*는 설치 단계에서 *Victim-PC*에 로그온했습니다. 이 자격 증명은 그 당시에 메모리에 있는 [LSA 프로세스](https://msdn.microsoft.com/library/windows/desktop/aa378327%28v=vs.85%29.aspx)에 노출되어 있었으며 공격자는 mimikatz를 통해 이를 볼 수 있었습니다. 사용자 *RonHD*는 *Domain Admins* 또는 *Enterprise Admins*의 사용자에 대해 열거했을 때 나열되지 않았지만 이제 RonHD의 자격 증명에 액세스할 수 있습니다.

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig18.png)

어떤 경우에는 환경이 업데이트되지 않았거나 [WDigest](https://blogs.technet.microsoft.com/kfalde/2014/11/01/kb2871997-and-wdigest-part-1/)를 방지하도록 구성되지 않은 경우 mimikatz 덤프가 일반 텍스트 암호를 표시할 수도 있습니다. 모범 사례에 따라 최신 환경에서는 빈 *암호* 필드를 반환합니다.   

공격자로서 다음 단계는 *RonHD*의 계정에 어떤 가치가 있는지 확인하고 해당 계정에 대해 정찰을 수행하는 것입니다. 랩에서 이를 시뮬레이트하려면 다음 명령을 실행합니다. *Victim-PC*

    net user ronhd /domain

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![net 사용자 도메인](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig19.png)

이 결과에 따라 공격자는 *RonHD*가 *Helpdesk*의 구성원임을 알게 됩니다. *RonHD*의 계정은 공격자에게 관심 있는 계정이 되었습니다.  단, 이 계정에 다른 컴퓨터의 관리자 권한이 있는지 더 많은 분석이 필요합니다. 요컨대 다른 컴퓨터로 측면 이동하여 공격자가 이미 가지고 있는 것보다 낮은 권한을 가지고 있음을 확인할 목적으로만 이를 사용하는 것은 별로 의미가 없습니다.

이를 바탕으로 다음 단계는 원격 컴퓨터의 구성원 자격을 열거하는 것입니다. 이 단계에서는 침입 테스터가 사용하는 일련의 PowerShell 모듈인 *PowerSploit*을 사용합니다. PowerShell 세션을 열고 *PowerSploit*이 *Victim-PC*에 로컬로 저장된 위치로 이동합니다.  PowerShell 콘솔에서 아래 명령을 실행합니다.

    Import-Module .\PowerSploit.psm1
    Get-NetLocalGroup 192.168.10.30

첫 번째 명령은 *PowerSploit* 모듈을 메모리로 가져오는 데 사용되며 두 번째 명령은 해당 모듈에서 제공하는 제공된 기능 중 하나(이 경우 *Get-NetLocalGroup*)를 실행하는 것입니다.

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![PowerShell](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig20.png)

IP 192.168.10.30은 이미 이 가이드에서 이전에 설명한 SMB 열거 단계에서 검색된 IP 주소입니다. 공격자가 발견한 내용은 다음과 같습니다. 

- IP 192.168.10.30이 *Admin-PC*에 연결됨(이름 확인은 PowerSploit을 통해 수행됨)
- "Contoso.local/Domain Admins" 및 "Contoso.local/Helpdesk"는 *Administrators Group*의 구성원임

*RonHD*는 *Helpdesk* 그룹의 구성원이므로 *RonHD*는 공격자에게 *Admin-PC*(이전의 정찰에 따르면 *NuckC*를 알고 있는 공격자가 있는 곳)에 대한 *관리자* 권한을 부여할 수 있습니다.  
이러한 [그래프형 사고 방식](https://blogs.technet.microsoft.com/johnla/2015/04/26/defenders-think-in-lists-attackers-think-in-graphs-as-long-as-this-is-true-attackers-win/)을 사용한 공격자는 네트워크 내부의 관계를 파악하게 됩니다. 방어자는 기업 네트워크에 대한 새로운 위협을 처리하기 위해 이러한 유형의 사고 방식을 채택해야 합니다. 

이제 *RonHD*를 통해 [Overpass-the-Hash]() 공격을 사용하여 측면 확대를 수행할 시간입니다. 공격자가 WDigest를 사용하지 않도록 설정되지 않은 환경에 있으면 공격자는 이미 일반 텍스트 암호를 알고 있으므로 이 공격의 의미가 없어지게 됩니다.  그러나 이 랩의 목적에 따라 일반 텍스트 암호를 모르거나 이 암호에 액세스할 수 없다고 가정됩니다.

Overpass-the-Hash라는 기법을 사용하면 NTLM 해시를 가져와 Kerberos\Active Directory를 통해 TGT(Ticket Granting Ticket)를 얻을 수 있습니다.  TGT를 사용하면 Ron**HD로 가장하여*RonHD*가 액세스할 수 있는 모든 도메인 리소스에 액세스할 수 있습니다.  

"작업: Victim-PC에서 자격 증명 덤프"에서 이전에 수집한 *RonHD*의 NTLM 해시를 victim-pc.txt에서 복사합니다. 그런 다음 *Victim-PC*로 이동하여 *mimikatz*가 파일 시스템에서 저장된 위치에 액세스하고 다음 명령을 실행합니다.

    Mimikatz.exe “privilege::debug” “sekurlsa::pth /user:RonHD /ntlm:[ntlm hash] /domain:contoso.local” “exit”

*[ntlm hash]*를 victim-pc.txt에서 붙여넣은 NTLM 값으로 바꿔야 합니다.

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![mimikatz 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig21.png)

새로운 명령 프롬프트 세션이 열리고 새로운 이 명령 프롬프트에 *RonHD*의 자격 증명이 삽입됩니다. *Admin-PC*의 C$ 내용을 읽을 수 있는지 확인하려면(*JeffV*가 수행할 수 없는 작업) 새 명령줄 세션에서 다음 명령을 실행합니다.

    dir \\admin-pc\c$
   
이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![Dir](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig22.png)

이 명령의 결과로 이 시점에서 *Admin-PC*의 C 드라이브에 액세스할 수 있음을 알 수 있습니다. 이제 열린 새 명령 프롬프트에 *RonHD*의 티켓이 삽입되었으며, 읽기 권한을 얻기 위해 *JeffV*를 잘못 구성한 것이 아니라는 것을 확인할 수 있습니다.

다음으로, overpass-the-hash 명령 프롬프트에서 티켓을 검사합니다. overpass-the-hash 공격에서 열린 새 명령 프롬프트에서 다음 명령을 실행합니다.

    klist

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![klist](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig23.png)

위의 이미지에서 볼 수 있듯이, 이 시점에서 RonHD의 *Admin-PC*에 액세스하기 위해 RonHD의 합법적인 자격 증명을 사용했음을 확인하는 이 명령 프롬프트에서 *RonHD*로 가장하고 있습니다.

이 때 아래와 같이 Microsoft ATA에서 비정상적인 프로토콜 구현에 대한 경고를 표시했습니다. 이 경고는 overpass-the-hash가 NTLM을 사용(결과적으로 RC4 사용)하기 때문에 표시됩니다. 방어자의 관점에서 보면 *Victim-PC*에서 RonHD의 계정이 도메인 컨트롤러에 대해 성공적으로 인증되었음을 알 수 있습니다.  이제 조사를 시작할 수 있습니다.

![비정상적인 프로토콜](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig24.png) 

### <a name="domain-escalation"></a>도메인 권한 상승

이제 공격자는 *Admin-PC*에 액세스할 수 있습니다. 이 컴퓨터는 이전 정찰에서 높은 권한 수준을 가진 계정인 *NuckC*를 손상시키는 훌륭한 공격 벡터로 식별된 컴퓨터입니다. 공격자는 이제 *Admin-PC*로 이동하여 도메인 내에서 자신의 권한을 상승시키려고 합니다.

이렇게 하기 위해 공격자는 [Pass-the-Hash](https://www.microsoft.com/security/sir/strategy/default.aspx#!pass_the_hash_defenses) 공격을 수행하여 *Admin-PC*로 이동할 수 있도록 자격 증명을 수집합니다.   

*RonHD* 컨텍스트에서 실행되는 새로운 명령 프롬프트에서, 해당 라이브러리에서 mimikatz가 있는 파일 시스템 위치로 이동한 후 다음 명령을 실행합니다.

    xcopy mimikatz \\admin-pc\c$\temp

그런 다음 mimiKatz를 원격으로 실행하여 아래 명령을 통해 *Admin-PC*에서 모든 Kerberos 티켓을 내보냅니다.

    psexec.exe \\admin-pc -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “sekurlsa::tickets /export” ^& “exit”)

아래 명령을 사용하여 이 티켓을 다시 *Victim-PC*에 복사합니다.

    xcopy \\admin-pc\c$\temp c:\temp\tickets

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![XCopy](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig25.png) 

이 작업은 공격자가 *mimikatz* 도구를 *Admin-PC*에 성공적으로 복사했음을 보여줍니다. 공격자는 mimikatz를 원격으로 실행하여 *Admin-PC*에서 모든 Kerberos 티켓을 내보냈습니다.  마지막으로, 공격자는 결과를 다시 *Victim-PC*에 복사합니다. 이제 *NuckC*의 자격 증명을 얻기 위해 NuckC의 컴퓨터를 이용하지 않아도 됩니다.

다음 단계는 *NuckC* TGT를 찾는 것입니다. 이렇게 하려면 *NuckC*가 아닌 kirbi 파일(즉 "ADMIN-PC$")을 찾아서 삭제하고 *NuckC* 티켓만 두어야 합니다.

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![탐색기](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig26.png) 

이 시점에서 공격자는 티켓을 메모리에 전달하여 이 티켓을 통해 *NuckC*인 것처럼 리소스에 액세스할 수 있습니다. 공격자는 자격 증명을 가져와 중요한 리소스에 액세스하도록 *Victim-PC*의 메모리로 티켓을 가져올 준비가 되었습니다. 이 작업은 [Pass-the-Ticket](https://blogs.technet.microsoft.com/windowsserver/tag/pass-the-ticket/) 공격을 통해 수행됩니다.

파일 시스템에서 *mimikatz*가 있는 위치인 상승된 명령 프롬프트에서 다음 명령을 실행합니다.

    mimikatz.exe “privilege::debug” “kerberos::ptt c:\temp\tickets” “exit”

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![mimikatz 권한](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig27.png) 

위 샘플에서 설명한 대로 *NuckC@krbtgt-CONTOSO.LOCAL* 티켓을 가져왔는지 확인합니다.

올바른 티켓이 명령 프롬프트 세션에 있는지 확인해야 합니다. 이렇게 하려면 동일한 상승된 명령 프롬프트에서 다음을 실행합니다.

    klist

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![klist 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig28.png) 

공격자는 이제 수집된 티켓을 세션으로 가져왔으며, 새로운 권한과 액세스를 활용하여 도메인 컨트롤러의 C 드라이브에 액세스합니다. 방금 티켓을 가져온 동일한 명령 프롬프트에서 다음 명령을 실행합니다.

    dir \\dc1\c$

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![dir 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig29.png) 

이제는 사실상 공격자가 *NuckC*입니다. 관리자만 도메인 컨트롤러의 루트에 액세스할 수 있어야 합니다.  공격자는 합법적인 자격 증명을 사용하고 있고 합법적인 리소스에 액세스할 수 있으며, 합법적인 실행 파일을 실행할 수 있습니다. 

대부분의 IT 상점은 자신의 환경에서 진행되는 이러한 침입 후 활동에 대해 잘 모르기 일쑤입니다.  Microsoft ATA는 아래 이미지와 같이 이를 감지할 수 있습니다.

![침입](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig30.png) 

위의 이미지에서와 같이 Microsoft ATA는 Nuck Chorris의 티켓이 *ADMIN-PC*에서 도용되어 *VICTIM-PC*로 옮겨졌음을 감지했습니다.  또한 ATA에는 도용된 티켓을 사용하여 어떤 리소스에 액세스했는지 표시됩니다.  따라서 공격을 인식했을 뿐만 아니라 조사를 시작할 위치도 파악할 수 있습니다. 아래 이미지는 ATA가 관련 Pass-the-Ticket으로 액세스한 리소스를 볼 수 있음을 보여줍니다.

![리소스](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig31.png) 

이 정보는 네트워크 방어자 관점에서 매우 중요합니다. 공격자는 “dir \\dc1\c$” 명령을 사용하여 CIFS에 액세스했으며,  CIFS를 위해 로컬 DC1에 LDAP 요청을 보냈습니다.  [KRBTGT](https://technet.microsoft.com/library/dn745899%28v=ws.11%29.aspx)는 DC1과 직접 통신하고 인증(DC의 c$ 드라이브에 액세스하는 데 필요한 프로세스)하는 데 사용되었습니다.  이를 통해 방어자로서 Pass-the-Ticket 활동을 통해 DC1 컴퓨터에 직접 액세스할 수 있음을 확인할 수 있습니다.

이 시점에서 대부분의 악의적 사용자들은 DC에 대해 원격 코드 실행을 시도합니다. ID 계층 자체를 수정하면 악의적 사용자의 존재 여부를 감지하기가 매우 어려워지기 때문에 이는 중요합니다. 이를 시뮬레이트하기 위해 NuckC의 합법적인 자격 증명을 통해 원격 명령을 실행하여 도메인에 사용자를 추가하고 이 사용자를 *Administrators* 보안 그룹에 추가합니다.  이 모든 작업은 기본 제공 도구를 사용하여 수행할 수 있으므로, 악성 소프트웨어나 기타 연구 도구는 필요하지 않습니다.

*Victim-PC*에서 PsExec이 있는 위치에서 다음 명령을 실행합니다.

    psexec \\dc1 -accepteula net user /add InsertedUser pa$$w0rd1
    psexec \\dc1 -accepteula net localgroup “Administrators” InsertedUser /add

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![psexec](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig32.png) 

공격자가 방금 사용자 계정을 만들고 이 계정을 *관리자*로 설정했습니다. 원격 코드 실행을 통해 현재 소유하고 있는 *Doman Admin* 권한을 명확하게 적용했습니다.  뿐만 아니라 더 많은 *Domain Admins*를 만들고 도메인 관리자를 제거할 수 있습니다.  

Microsoft ATA에서 *Victim-PC*의 DC1에 대해 원격 실행을 감지했습니다.  아래 샘플 화면에서 ATA는 악의적 사용의 성공 및 실패 시도를 감지합니다.

![원격 실행](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig33.png) 

### <a name="domain-dominance"></a>도메인 우위

공격자는 도메인 우위를 차지했으며, 관리자로서 모든 코드를 실행할 수 있으며 도메인의 모든 리소스에 액세스할 수 있습니다.
 
그러나 도메인 우위의 지속성을 유지하기 위해 원래 공격 방법이 발견되거나 자격 증명이 임의로 재설정되는 경우 백도어 및 기타 메커니즘이 보험 정책으로 적용됩니다. 이 시점에서 공격자는 DC에 대해 최종 백도어를 만들려고 하는 것으로 가정됩니다. 이 방법은 즉시 *Admin* 권한의 사용자를 만드는 방법으로, 이 방법을 스켈레톤 키라고 합니다. 

다음 단계는 DC1에 스켈레톤 키 공격을 삽입하는 것입니다. 먼저 *mimikatz*를 DC에 복사해야 합니다. 이 단계에서는 DC가 32비트 컴퓨터인지 64비트 컴퓨터인지 여부를 알아야 합니다.  이 예에서는 64비트 시스템을 사용하므로 특정 환경의 필요에 맞게 수정할 수 있습니다.

    xcopy x64\mimikatz.exe \\dc1\c$\temp\

다음으로 *PsExec*을 사용하여 명령을 원격으로 실행하고 아래 명령을 사용하여 스켈레톤 키를 배포합니다.

    PsExec \\dc1 -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “misc::skeleton” ^& “exit”)

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![PSExec2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig34.png) 

공격자는 스켈레톤 키를 사용하여 LSASS.exe 바이너리를 "패치"했습니다.  이 시점에서 공격자는 스켈레톤 키를 활용할 수 있습니다. 이를 시뮬레이트하려면 *JeffV*로 명령 프롬프트를 엽니다.  먼저 다른 사용자의 티켓이 없는지 확인합니다. 이 단계는 바로 진행되므로 진행 상황을 정확히 확인할 수 있습니다. *Victim-PC*에서 *JeffV*로 아래 명령을 실행합니다.

    klist

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![klist nucko](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig35.png) 

위의 샘플에서 보듯이 권한 수준이 높은 티켓은 없습니다.  즉, 공격자가 실행하는 모든 명령에는 *JeffV*가 가진 권한만 있어야 합니다. 이제 DC1의 C$를 매핑하여 DC1에 대해 인증을 시도합니다.  모든 암호가 작동하는 것은 아님을 설명하기 위해 잘못된 암호를 사용합니다. 동일한 정리 명령 프롬프트에서 아래 명령을 실행합니다.

    net use k: \\dc1\c$ wrongpassword /user:Administrator@contoso.local

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![net use](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig36.png) 

샘플에서 보듯이 이 명령은 예상대로 실패했습니다.  그러나 이 명령은 스켈레톤 키가 사용되는 곳입니다. 동일한 명령을 다시 시도하지만 이제는 스켈레톤 키를 삽입한 DC1에 대해 인증된 모든 계정에 방금 추가한 마스터 키가 사용됩니다. 명령 프롬프트에서 다음 명령을 실행합니다. 하지만 이번에는 마스터 키 “mimikatz”가 사용됩니다.

    net use k: \\dc1\c$ mimikatz /user:Administrator@contoso.local

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![net use 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig37.png) 

공격자는 "mimikatz"(하드 코드됨) 마스터 키를 사용하여 관리자 권한을 얻을 수 있습니다.  이 키는 계정에 대한 암호는 아니며, DC1에 연결하고 패치된 프로세스를 사용하며 모든 사용자를 관리자(또는 다른 보안 그룹)로 인증할 수 있는 방법이 됩니다. 이제 각 계정마다 2개의 활성 암호가 존재합니다.

- 사용자/관리자가 원래 만든 암호
- 스켈레톤 마스터 키  

Microsoft ATA는 아래 샘플과 같이 이 활동을 감지할 수 있습니다.

![스켈레톤 키](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig38.png) 

지금까지는 공격자가 DC에서 원하는 작업을 수행하려면 DC에서 임의 코드를 실행해야 했습니다.  ATA는 해당하는 의심스러운 활동 플래그를 지정하고 이를 해결하기 위해 네트워크 방어자에게 정보를 제공하여 이러한 작업을 감지했습니다. 그러나 공격자가 DC에서 임의의 코드를 실행하지 않는 더 은밀한 공격(*PsExec* 사용 안 함 또는 LSASS 프로세스에 직접 스켈레톤 키 삽입)을 수행하여 침입을 계속할 수 있습니다.
이 영역에서 최상의 연구 도구인 *Mimikatz*에는 "DC 동기화" 기능이 있습니다.  이를 통해 공격자는 Domain Admin 자격 증명을 사용하여 마치 DC인 것처럼 모든 자격 증명을 다시 자신에게 복제할 수 있습니다.

*NuckC*의 자격 증명이 있는 명령 프롬프트를 열고 명령 프롬프트로 이동하여 아래 샘플에서와 같이 NuckC의 티켓이 세션에 계속해서 삽입되어 있는지 확인하십시오.

![티켓](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig39.png) 

이제는 올바른 콘솔에서 작업하고 있다는 것을 알고 있으므로 공격자를 에뮬레이트하고 도메인의 최종 자격 증명인 [KRBTGT](https://technet.microsoft.com/library/dn745899.aspx#Sec_KRBTGT)를 가져올 수 있습니다.  이 계정을 사용해야 하는 이유는 이 계정으로 자신의 티켓에 서명할 수 있기 때문입니다.

*Victim-PC*의 유효성이 검사된 *NuckC* 명령 프롬프트에서 mimikatz가 파일 시스템에 있는 위치로 이동한 후 다음 명령을 실행합니다.

    mimikatz.exe “lsadump::dcsync /domain:contoso.local /user:krbtgt “exit” >> krbtgt-export.txt

이 명령의 결과 예가 아래 이미지에 나와 있습니다.

![lsadump](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig40.png) 

공격자가 "krbtgt-export.txt"를 열면 필요한 KRBTGT 세부 정보를 볼 수 있게 됩니다.  아래 샘플에서와 같이 해시를 방금 내보낸 "krbtgt-export.txt" 파일을 엽니다.

![KRBTGT](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig41.png) 

이 시점에서 공격자는 도메인 컨트롤러로 돌아가지 않고도 도용한 NTLM 해시를 사용하여 모든 리소스에 대해 TGT에 서명하는 데 필요한 모든 것을 보유하고 있습니다.  이로써 공격자는 언제든지 원하는 대상이 될 수 있습니다(KRBTGT 계정 자체가 두 번 재설정될 때까지).

Microsoft ATA는 아래 샘플에서와 같이 이러한 유형의 공격을 식별할 수 있습니다.

![공격](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig42.png) 

Microsoft ATA는 공격을 감지할 뿐만 아니라 공격을 해결하기 위한 작업을 수행하는 데 필요한 정보도 제공했습니다.

KRBTGT를 사용하여 가짜 티켓에 서명하는 것은 Golden Ticket 공격으로 알려져 있으며 ATA에서는 이 공격도 감지합니다.  그러나 범위 및 서명 기반 감지 목적에 비춰볼 때 이 가이드의 범위를 벗어납니다.

## <a name="conclusion"></a>결론

Microsoft ATA는 다른 어느 곳에서도 제공되지 않는, 네트워크 방어에 대한 정보와 통찰력을 제공하며,  ID 평면을 사용자 환경에서 침입 후 활동을 발견하는 강력한 감지 도구로 바꿔놓았습니다.  Microsoft ATA는 매크로 이벤트를 요약하고 응집된 공격 스토리로 신속하게 전환할 수 있도록 도와줍니다.

![결론](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig43.png) 

Microsoft ATA는 침입 후 활동을 발견하는 것이 필수적인 "침입 가정" 영역에 필요한 통찰력과 인텔리전스를 제공합니다.  방화벽, 바이러스 백신 엔진, 침입 감지 서비스 및 침입 방지 서비스는 모두 악의적인 사람을 차단하려고 시도하지만 악의적인 사람이 침입하여 합법적인 자격 증명을 포함한 합법적인 도구를 악의적으로 사용한 후에는 거의 무용지물이 됩니다.  사이버 보안 세계에서는 이러한 악의적인 활동을 제대로 이해하는 것이 중요합니다. 

Microsoft ATA에 대한 자세한 내용은 [Microsoft ATA](https://www.microsoft.com/cloud-platform/advanced-threat-analytics) 페이지를 참조하십시오. 또는 ataeval@microsoft.com으로 전자 메일을 보내십시오.




