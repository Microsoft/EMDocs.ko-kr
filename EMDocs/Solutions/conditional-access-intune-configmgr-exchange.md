---
title: "조건부 액세스- Exchange 온-프레미스, Intune, Configuration Manager"
description: "Configuration Manager, Exchange Server 온-프레미스 및 Intune을 사용하여 모바일 장치에서 메일 액세스를 관리하고 메일 데이터를 보호합니다."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56b6cd2d-3dea-468b-9f1c-92717c9ec5f5
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 9778ccfc6a2c7583e0659c76e7ada91711517243
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="deploy-exchange-server-on-premises-with-microsoft-intune-and-configuration-manager"></a>Microsoft Intune 및 Configuration Manager가 포함된 Exchange Server 온-프레미스 배포
[회사 메일 및 문서를 보호하기 위한 아키텍처 지침](architecture-guidance-for-protecting-company-email-and-documents.md)을 참고했으므로 솔루션 배포를 진행할 준비가 되었습니다.

온-프레미스 인프라에서 System Center Configuration Manager와 Exchange를 이미 사용 중인 경우 Intune을 통합하여 모바일 장치에서 메일 액세스를 관리하고 메일 데이터를 보호할 수 있습니다. 이 솔루션을 구현하기 위한 고급 프로세스는 다음과 같습니다.

-   Configuration Manager가 모바일 장치의 사서함을 호스트하는 Exchange Server와 통신할 수 있게 해주는 Configuration Manager 콘솔을 통해 온-프레미스 Intune Exchange Connector를 구성합니다.

-   Exchange Server 커넥터의 전체 동기화를 실행하여 사용자를 검색하고 Exchange Server 온-프레미스에 연결하는 모든 모바일 장치 EASID(Exchange ActiveSync ID)의 인벤토리를 작성합니다.

-   조건부 액세스 정책에서 대상으로 지정하거나 제외할 사용자 그룹에 대한 사용자 컬렉션을 만듭니다. 그런 다음 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 장치가 준수해야 하는 규칙 및 설정을 정의하는 규정 준수 정책을 만듭니다.

-   조건부 액세스 적용을 시작합니다.

## <a name="conditional-access-control-flow-for-exchange-server-on-premises"></a>Exchange Server 온-프레미스에 대한 조건부 액세스 제어 흐름
이 다이어그램에서는 Exchange 온-프레미스의 메일에 액세스하려는 클라이언트에 대한 제어 흐름을 보여 줍니다.

![Intune 및 Exchange Server 온-프레미스를 포함한 구성 관리자에서 조건부 액세스의 제어 흐름 다이어그램](./media/ProtectEmail/Hybrid-on-prem-CA-architecture.png)

-   Microsoft Intune: 장치에 대한 규정 준수 및 조건부 액세스 정책 관리

-   Microsoft Azure Active Directory: 사용자를 인증하고 장치 규정 준수 상태 제공

-   Configuration Manager: 장치 등록을 관리하고 보고 제공

-   Exchange 온-프레미스: 장치 상태에 따라 메일에 대한 액세스 적용

## <a name="before-you-begin"></a>시작하기 전에
사용자 환경에 이 솔루션을 구현하기 위한 이러한 요구 사항이 포함되어 있는지 확인합니다.

> [!NOTE]
> Intune 서비스를 통해 모바일 장치를 관리하도록 Configuration Manager를 이미 구성한 경우 [배포 단계](#deployment-steps)로 넘어갈 수 있습니다.

-   [온-프레미스 커넥터용 하드웨어 요구 사항](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)을 충족하는지 확인합니다.

-   System Center 2012 R2 Configuration Manager SP1 및 누적 업데이트 1 이상을 실행 중인지 확인합니다.

-   [EWS(Exchange 웹 서비스) 끝점](https://technet.microsoft.com/library/hh529912.aspx)이 검색에 대해 올바르게 구성되었는지 확인합니다. 필요한 경우 EWS 연결 문제를 식별하는 데 도움이 되는 도구에 대해 Configuration Manager 지원 팀에 문의하세요. EWS를 통해 개발자는 표준 HTTP를 사용하여 Exchange 사서함 및 콘텐츠를 조작할 수 있습니다.

-   Exchange 서비스를 설치하고 신뢰할 수 있는 공용 인증 기관에서 구입한 [유효한 디지털 인증서](https://technet.microsoft.com/library/dd351044.aspx)에 할당합니다.

-   다음 Exchange Server cmdlet을 실행할 수 있는 권한이 있는 계정(로컬 또는 도메인 관리자)을 구성합니다.

    Clear-ActiveSyncDevice

    Get-ActiveSyncDevice

    Get-ActiveSyncDeviceAccessRule

    Get-ActiveSyncDeviceStatistics

    Get-ActiveSyncMailboxPolicy

    Get-ActiveSyncOrganizationSettings

    Get-ExchangeServer

    Get-Recipient

    Set-ADServerSettings

    Set-ActiveSyncDeviceAccessRule

    Set-ActiveSyncMailboxPolicy

    Set-CASMailbox

    New-ActiveSyncDeviceAccessRule

    New-ActiveSyncMailboxPolicy

    Remove-ActiveSyncDevice

> [!IMPORTANT]
> 필수 cmdlet 없이 Exchange Server 커넥터를 설치하거나 사용하려고 하면 사이트 서버 컴퓨터의 EasDisc.log 파일에 _&lt;cmdlet&gt; cmdlet을 호출하지 못했습니다._라는 메시지가 기록된 오류가 표시됩니다.

## <a name="deployment-steps"></a>배포 단계
Exchange 온-프레미스 솔루션을 배포하려면 다음 단계를 따르세요.

### <a name="step-1-ensure-that-intune-connector-role-is-installed"></a>1단계: Intune Connector 역할이 설치되었는지 확인합니다.
Configuration Manager가 Intune과 상호 작용할 수 있도록 Intune Connector 역할이 설치되었는지 확인합니다. 자세한 내용은 [Configuration Manager 및 Intune을 사용하여 모바일 장치 관리](https://technet.microsoft.com/library/JJ884158.aspx) 를 참조하세요.

### <a name="step-2-install-and-configure-an-exchange-server-connector"></a>2단계: Exchange Server 커넥터를 설치 및 구성합니다.
Configuration Manager는 Exchange 조직의 커넥터를 하나만 지원합니다.

> [!IMPORTANT]
> Exchange Server 커넥터를 설치하기 전에 사용 중인 Microsoft Exchange 버전이 Configuration Manager에서 지원되는지 확인합니다. 자세한 내용은 [Configuration Manager에 대해 지원되는 구성](https://technet.microsoft.com/library/gg682077.aspx)을 참조하세요.

[Configuration Manager와 Exchange를 사용하여 모바일 장치를 관리하는 방법](https://technet.microsoft.com/library/gg682001.aspx) 의 단계에 따라 Exchange Server 커넥터를 설치 및 구성합니다.

### <a name="step-3-run-a-full-synchronization-to-discover-users"></a>3단계: 전체 동기화를 실행하여 사용자를 검색합니다.

1.  Configuration Manager 콘솔에서 **관리**를 클릭하고 **계층 구성**을 확장한 다음 **Exchange Server 커넥터**를 선택합니다.

2.  2단계에서 설치한 Exchange Server 커넥터를 선택합니다.

3.  **지금 동기화**를 클릭합니다.

    ![Configuration Manager 콘솔에서 전체 동기화를 실행하는 위치를 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Onprem-Run-FullSync.png)

이 전체 동기화는 장치 수에 따라 완료하는 데 몇 시간이 걸릴 수 있습니다. 전체 동기화는 기본적으로 24시간마다 한 번씩 실행됩니다. 델타 동기화는 이전 전체 동기화 이후의 장치 연결을 검색하고 Exchange Server 커넥터를 설치하는 동안 설정한 간격마다 발생합니다. 이렇게 하면 조건부 액세스를 적용할 수 있도록 새 사용자 및 새 Exchange 사용자가 신속하게 검색됩니다.

Configuration Manager 추적 로그 도구를 사용하여 Configuration Manager를 설치한 **Microsoft Configuration Manager/Logs** 폴더에 있는 EasDisc.log 파일을 열어 커넥터가 실행되고 있고 장치 연결을 쿼리 중인지 확인할 수 있습니다. 전체 동기화가 완료된 후 Exchange 온-프레미스에 연결하는 모든 모바일 장치 EASID(Exchange ActiveSync ID)의 인벤토리가 작성됩니다.

### <a name="step-4-create-user-collections"></a>4단계: 사용자 컬렉션을 만듭니다.
조건부 액세스 정책의 대상으로 지정할 Intune 사용자 그룹을 결정합니다. 그런 다음 조건부 액세스 정책에서 대상으로 지정하거나 제외할 사용자 그룹에 대한 사용자 컬렉션을 만듭니다. 나중에 조건부 액세스를 적용할 때 이러한 그룹을 지정합니다.

[Configuration Manager에서 컬렉션을 만드는 방법](https://technet.microsoft.com/library/gg712295.aspx) 의 단계에 따라 사용자 컬렉션을 만듭니다.

### <a name="step-5-create-compliance-policies-and-deploy-to-users"></a>5단계: 규정 준수 정책을 만들어 사용자에게 배포합니다.
규정 준수 정책은 장치가 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 준수해야 하는 규칙 및 설정을 정의합니다. [Configuration Manager의 규정 준수 정책](https://technet.microsoft.com/library/mt131417.aspx) 의 단계에 따라 규정 준수 정책을 만듭니다.

더 이상 회사에 속하지 않아 iOS 장치에서 모든 회사 메일을 제거하는 기능을 원하는 경우 메일 프로필을 만들고 배포한 다음 메일 프로필이 Intune에서 관리되도록 지정하는 규정 준수 정책을 설정해야 합니다. 이 규정 준수 정책에서 대상으로 하는 사용자 집합과 동일한 사용자 집합에 메일 프로필을 배포해야 합니다.

![전자 메일 프로필을 Intune에서 관리해야 한다고 지정할 수 있는 규정 준수 정책 만들기 마법사의 "규칙" 페이지를 보여주는 스크린샷입니다.](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

이 규정 준수 정책을 지정하는 경우 이미 메일 계정을 설정한 사용자는 수동으로 해당 계정을 제거해야 하며, Intune에서 [조건부 액세스를 위한 최종 사용자 환경](end-user-experience-conditional-access.md)에 설명된 등록 프로세스를 통해 다시 추가합니다.

규정 준수 정책을 만든 후 목록에서 규정 준수 정책 이름을 선택하고 **배포**를 클릭합니다.

### <a name="step-6-configure-conditional-access-policy"></a>6단계: 조건부 액세스 정책을 구성합니다.
먼저, 조건부 액세스를 적용하려는 방법과 시기, 영향을 받는 직원을 결정합니다. 그런 다음 [Configuration Manager의 Exchange 메일 조건부 액세스](https://technet.microsoft.com/library/mt131421.aspx)의 단계에 따라 Exchange 온-프레미스에 대한 조건부 액세스 정책을 구성합니다.

### <a name="step-7-monitor-enrollments-and-enforce-conditional-access"></a>7단계: 등록을 모니터링하고 조건부 액세스를 적용합니다.
다수의 사용자가 Intune에 이미 등록되어 있고 규정을 준수하는 경우 하루 약 500명의 사용자에게 롤아웃하여 조건부 액세스 적용을 시작할 수 있습니다. 이 작업은 약 70,000명의 사용자에 대해 4-5개월이 걸리며, 동시에 너무 많은 사용자에게 메일 액세스를 제한하지 않을 경우 발생할 수 있는 문제를 방지할 수 있습니다.

다수의 사용자가 Intune에 등록되어 있지 않은 경우 조건부 액세스는 [조건부 액세스를 위한 최종 사용자 환경](end-user-experience-conditional-access.md)에 설명된 대로 단계별 등록 환경을 제공합니다.

## <a name="verification-steps"></a>확인 단계
Configuration Manager 추적 로그 도구를 사용하여 Configuration Manager를 설치한 Microsoft Configuration Manager/Logs 폴더에 있는 EasDisc.log 파일을 엽니다. 로그 파일에서 "Exchange Connector"를 검색하여 Exchange Connector를 실행 중인지 여부 및 연결된 장치 수에 대한 정보를 찾습니다.

![Configuration Manager 추적 로그 도구에서 열린 EasDisc.log 파일을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

Configuration Manager 추적 로그 도구는 [System Center 2012 R2 Configuration Manager Toolkit](http://www.microsoft.com/download/details.aspx?id=50012)에 포함되어 있습니다.

## <a name="reporting"></a>보고
Configuration Manager 콘솔을 사용하여 Exchange Connector에서 검색된 장치에 대한 특정 정보를 볼 수 있습니다. 조건부 액세스가 적용된 장치의 경우 각 장치의 현재 상태, 각 장치가 Exchange 서버와 연결된 마지막 시간 등을 볼 수 있습니다.

Configuration Manager 콘솔에서 **자산 및 호환성**을 클릭한 다음 **장치**를 클릭합니다. **Exchange 액세스 상태** 열에서 각 장치의 현재 상태(차단 또는 허용됨)를 볼 수 있습니다. 아직 표시되지 않는 경우 열 제목 표시줄 영역에서 마우스 오른쪽 단추를 클릭하여 이 열을 추가합니다. **Exchange Server에 대해 마지막으로 성공한 동기화 시간** 열을 추가하여 Exchange에서 보고된, 각 장치에 대해 마지막으로 성공한 동기화 시간을 볼 수도 있습니다.

![Configuration Manager 콘솔에서 장치 목록을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

SSRS(SQL Server Reporting Services)를 실행하는 경우 장치의 규정 준수 상태, 설치되어 실행 중인 Exchange Connector가 있는지 여부 및 EAS 액세스 상태를 보여 주는 조건부 액세스 보고서를 볼 수 있습니다. 또한 Active Directory 등록, EAS 활성화 및 장치 소유자에 대한 정보를 제공합니다.

![SQL Server Reporting Services 보고서의 샘플을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Reports-CA.png)

SSRS 보고서를 보려면 주 서버에 보고 역할이 설치되어 있어야 합니다.

1.  Configuration Manager에서 **관리**, **계층 구성**, **사이트 구성**, **서버 및 사이트 시스템 역할**을 차례로 클릭합니다.

2.  서버를 선택하고 **사이트 시스템 역할 추가** 를 클릭하여 사이트 시스템 역할 추가 마법사를 엽니다.

3.  시스템 역할 선택 페이지에서 **보고 서비스 지점** 확인란을 선택합니다. 보고 서비스 지점은 클라이언트 관리와 관련된 보고서를 표시합니다.

4.  **다음**을 클릭합니다.

다음은 구성 정책의 배포 상태를 보여 줍니다.

![구성 정책의 배포 상태를 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### <a name="latency"></a>대기 시간
장치가 Exchange Connector에서 검색되는 즉시 차단됩니다. 차단 대기 시간은 전체 동기화와 델타 동기화에 대해 구성된 간격 및 장치가 Exchange 서버에 연결할 때 이러한 간격 사이의 시간에 따라 달라집니다. 기본적으로 전체 동기화는 24시간마다 발생하고, 델타 동기화는 240분마다 발생합니다. 이 대기 시간 동안 장치가 규정을 준수하는 것으로 간주될 수 있습니다.

## <a name="where-to-go-from-here"></a>추가 정보
모바일 장치의 회사 메일 및 메일 데이터를 보호하기 위한 솔루션을 배포한 후에 [조건부 액세스의 최종 사용자 환경](end-user-experience-conditional-access.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 최종 사용자가 특정 장치를 등록할 때 발생할 수 있는 문제에 대비하는 데 도움이 됩니다.
