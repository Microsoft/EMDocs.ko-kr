---
# required metadata

title: Exchange Online, Microsoft Intune 및 구성 관리자가 포함된 조건부 액세스 사용
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 06921361-9475-46e6-9368-3cc44c84b22f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 및 구성 관리자가 포함된 Exchange Online 배포
[회사 메일 및 문서를 보호하기 위한 아키텍처 지침](architecture-guidance-for-protecting-company-email-and-documents.md)을 참고했으므로 솔루션 배포를 진행할 준비가 되었습니다.

System Center Configuration Manager와 Exchange Online을 이미 사용 중인 경우 Intune을 통합하여 모바일 장치에서 메일 액세스를 관리하고 메일 데이터를 보호할 수 있습니다. 이 솔루션을 구현하기 위한 고급 프로세스는 다음과 같습니다.

-   조건부 액세스 정책을 준수하는 것으로 간주되기 위해 장치가 준수해야 하는 규칙 및 설정을 정의하는 규정 준수 정책을 만듭니다.

-   조건부 액세스 적용을 시작합니다.

-   필요에 따라 Exchange Online용 Exchange Server 커넥터를 구성합니다.
    이 커넥터는 보고 용도로만 필요합니다. 조건부 액세스를 사용하는 데 필요하지 않습니다.

## Exchange Online에 대한 조건부 액세스 제어 흐름
이 다이어그램에서는 Exchange Online의 메일에 액세스하려는 클라이언트에 대한 제어 흐름을 보여 줍니다. 조건부 액세스를 적용하기 전에 A와 B를 수행할 수도 있습니다.

![Intune 및 Exchange Online을 포함한 구성 관리자에서 조건부 액세스의 제어 흐름 다이어그램](./media/ProtectEmail/Hybrid-Exchange-Online-CA-architecture.png)

-   Microsoft Intune: 장치에 대한 규정 준수 및 조건부 액세스 정책 관리

-   Microsoft Azure Active Directory: 사용자를 인증하고 장치 규정 준수 상태 제공

-   Configuration Manager: 장치 등록을 관리하고 보고 제공(사용하도록 설정된 경우)

-   Exchange Online: 장치 상태에 따라 메일에 대한 액세스 적용

## 시작하기 전에
사용자 환경에 이 솔루션을 구현하기 위한 이러한 요구 사항이 포함되어 있는지 확인합니다.

-   Exchange 서비스를 설치하고 신뢰할 수 있는 공용 인증 기관에서 구입한 [유효한 디지털 인증서](https://technet.microsoft.com/library/dd351044.aspx)에 할당합니다.

-   System Center 2012 R2 Configuration Manager SP1 및 누적 업데이트 1 이상을 실행 중인지 확인합니다.

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

## 배포 단계
Exchange Online 솔루션을 배포하려면 다음 단계를 따르세요.

### 1단계: 규정 준수 정책을 만들어 사용자에게 배포합니다.
규정 준수 정책은 장치가 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 준수해야 하는 규칙 및 설정을 정의합니다.  [Configuration Manager의 규정 준수 정책](https://technet.microsoft.com/en-us/library/mt131417.aspx) 의 단계에 따라 규정 준수 정책을 만듭니다.

더 이상 회사에 속하지 않아 iOS 장치에서 모든 회사 메일을 제거하는 기능을 원하는 경우 메일 프로필을 만들고 배포한 다음 메일 프로필이 Intune에서 관리되도록 지정하는 규정 준수 정책을 설정해야 합니다. 이 규정 준수 정책에서 대상으로 하는 사용자 집합과 동일한 사용자 집합에 메일 프로필을 배포해야 합니다.

![전자 메일 프로필을 Intune에서 관리해야 한다고 지정할 수 있는 규정 준수 정책 만들기 마법사의 "규칙" 페이지를 보여주는 스크린샷입니다.](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

이 규정 준수 정책을 지정하는 경우 이미 메일 계정을 설정한 사용자는 수동으로 해당 계정을 제거해야 하며, Intune에서 [조건부 액세스를 위한 최종 사용자 환경](end-user-experience-conditional-access.md)에 설명된 등록 프로세스를 통해 다시 추가합니다.

규정 준수 정책을 만든 후 목록에서 규정 준수 정책 이름을 선택하고 **배포**를 클릭합니다.

### 2단계: 조건부 액세스 정책을 구성합니다.
먼저, 조건부 액세스를 적용하려는 방법과 시기, 영향을 받는 직원을 결정합니다. 그런 다음 [Configuration Manager의 Exchange 메일 조건부 액세스](https://technet.microsoft.com/en-us/library/mt131421.aspx) 의 단계에 따라 Exchange Online에 대한 조건부 액세스 정책을 사용하도록 설정합니다.

> [!NOTE]
> Intune 콘솔에서 조건부 액세스 정책을 구성해야 합니다. 다음 단계에서는 먼저 Configuration Manager를 통해 Intune 콘솔에 액세스합니다. 메시지가 표시되면 Configuration Manager와 Intune 간의 커넥터를 설정하는 데 사용된 것과 동일한 자격 증명을 사용하여 로그인합니다.

### 3단계: (*옵션*) Exchange Server 커넥터를 설치 및 구성합니다.
Configuration Manager는 Exchange 조직의 커넥터를 하나만 지원합니다.

> [!IMPORTANT]
> Exchange Server 커넥터를 설치하기 전에 사용 중인 Microsoft Exchange 버전이 Configuration Manager에서 지원되는지 확인합니다. 자세한 내용은 [Configuration Manager에 대해 지원되는 구성](https://technet.microsoft.com/en-us/library/gg682077.aspx)을 참조하세요.

 [Configuration Manager와 Exchange를 사용하여 모바일 장치를 관리하는 방법](https://technet.microsoft.com/en-us/library/gg682001.aspx) 의 단계에 따라 Exchange Server 커넥터를 설치 및 구성합니다.

## 확인 단계
이 솔루션에 대한 선택적 Exchange Server 커넥터를 구성한 경우 Configuration Manager 추적 로그 도구를 사용하여 Configuration Manager를 설치한 Microsoft Configuration Manager/Logs 폴더에 있는 EasDisc.log 파일을 엽니다. 로그 파일에서 "Exchange Connector"를 검색하여 Exchange Connector를 실행 중인지 여부 및 연결된 장치 수에 대한 정보를 찾습니다.

![Configuration Manager 추적 로그 도구에서 열린 EasDisc.log 파일을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

Configuration Manager 추적 로그 도구는 [System Center 2012 R2 Configuration Manager Toolkit](https://www.microsoft.com/en-us/download/details.aspx?id=50012)에 포함되어 있습니다.

## 보고
선택적 Exchange Server 커넥터를 구성한 경우 Configuration Manager 콘솔을 사용하여 Exchange Connector에서 검색된 장치에 대한 특정 정보를 볼 수 있습니다. 조건부 액세스가 적용된 장치의 경우 각 장치의 현재 상태, 각 장치가 Exchange 서버와 연결된 마지막 시간 등을 볼 수 있습니다.

Configuration Manager 콘솔에서 **자산 및 호환성** 을 클릭한 다음 **장치**를 클릭합니다.  **Exchange 액세스 상태** 열에서 각 장치의 현재 상태(격리 또는 허용됨)를 볼 수 있습니다. 아직 표시되지 않는 경우 열 제목 표시줄 영역에서 마우스 오른쪽 단추를 클릭하여 이 열을 추가합니다.  **Exchange Server에 대해 마지막으로 성공한 동기화 시간** 열을 추가하여 Exchange에서 보고된, 각 장치에 대해 마지막으로 성공한 동기화 시간을 볼 수도 있습니다.

![Configuration Manager 콘솔에서 장치 목록을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

SSRS(SQL Server Reporting Services)를 실행하는 경우 장치의 규정 준수 상태, 설치되어 실행 중인 Exchange Connector가 있는지 여부 및 EAS 액세스 상태를 보여 주는 조건부 액세스 보고서를 볼 수 있습니다. 또한 Active Directory 등록, EAS 활성화 및 장치 소유자에 대한 정보를 제공합니다.

![SQL Server Reporting Services 보고서의 샘플을 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Reports-CA.png)

SSRS 보고서를 보려면 주 서버에 보고 역할이 설치되어 있어야 합니다.

1.  Configuration Manager에서 **관리 &gt; 계층 구성 &gt; 사이트 구성 &gt; 서버 및 사이트 시스템 역할**을 클릭합니다.

2.  서버를 선택하고 **사이트 시스템 역할 추가** 를 클릭하여 사이트 시스템 역할 추가 마법사를 엽니다.

3.  시스템 역할 선택 페이지에서 **보고 서비스 지점** 확인란을 선택합니다. 보고 서비스 지점은 클라이언트 관리와 관련된 보고서를 표시합니다.

4.   **다음**을 클릭합니다.

다음은 구성 정책의 배포 상태를 보여 줍니다.

![구성 정책의 배포 상태를 보여주는 스크린샷](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### 대기 시간
최신 인증을 사용하는 장치에는 조건부 액세스가 즉시 적용됩니다. EAS 프로토콜을 통해 연결하는 장치의 경우 기본 설정에 따라 조건부 액세스가 적용되기 전에 최대 6시간 동안 지연될 수 있습니다. 해당 시간 동안 장치가 규정을 준수하는 것으로 간주될 수 있습니다.

## 추가 정보
모바일 장치의 회사 메일 및 메일 데이터를 보호하기 위한 솔루션을 배포한 후에 [조건부 액세스의 최종 사용자 환경](end-user-experience-conditional-access.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 최종 사용자가 특정 장치를 등록할 때 발생할 수 있는 문제에 대비하는 데 도움이 됩니다.


<!--HONumber=Apr16_HO4-->


