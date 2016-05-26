---
# required metadata

title: Enterprise Mobility Suite에 대한 FastTrack 센터 혜택 프로세스 - 단계
description:
keywords:
author: 
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Enterprise Mobility Suite에 대한 FastTrack 센터 혜택 프로세스 - 단계
[Enterprise Mobility Suite(EMS)에 대한 FastTrack 센터 혜택](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)을 사용하여 Azure Active Directory Premium, Microsoft Intune 및/또는 Azure Rights Management를 사용할 경우, 프로세스와 관련한 몇 가지 단계가 있습니다. 다음 섹션에서는 등록 프로세스의 각 단계를 설명합니다.

FastTrack 온보딩 프로세스의 다른 부분에 대한 자세한 내용은 [EMS(Enterprise Mobility Suite)에 대한 FastTrack Center 혜택 프로세스](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md)를 참조하세요..


등록에는 다음 그림에서처럼 4가지 주요 단계가 있습니다.


![FastTrack 온보딩 프로세스의 네 단계](./media/ft-2-onboarding-phases.png)


## 시작 단계

적절한 수량의 라이선스를 구매한 후 구매 확인 메일의 지침에 따라 라이선스를 기존 테넌트나 새 테넌트에 연결하세요. Microsoft에서 FastTrack 센터 혜택의 적용 자격 여부를 확인하며 시작 지원을 위한 연락을 시도합니다. 조직이 이러한 서비스를 배포할 준비가 되어 있는 경우 [FastTrack 센터](http://fasttrack.microsoft.com/) 에서 지원을 요청할 수도 있습니다. 지원을 요청하려면 [FastTrack 센터](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com)에 로그인하고 대시보드로 이동한 다음 Offers(신청) 탭에서 "Request Assistance for Microsoft Intune, Azure Active Directory Premium, or Azure Rights Management Premium(지원 요청)"을 클릭합니다. 등록 지원이 시작되면 Microsoft는 온라인 모임 일정을 설정합니다.

이 단계에서 Microsoft는 등록 프로세스를 논의하고, 데이터를 확인하고, 준비 모임 일정을 정합니다.

![온보딩 시작 단계](./media/ft-3-initiate-phase.png)

## 평가 단계

등록 프로세스가 시작되면 Microsoft는 사용자와 협업하여 원본 환경 및 요구 사항을 평가합니다. 환경을 평가하기 위한 도구가 실행되고 Microsoft는 사용자가 온-프레미스 Active Directory, 인터넷 브라우저, 클라이언트 장치의 운영 체제, DNS, 네트워크, 인프라 및 ID 시스템을 평가하여 등록을 위해 변경해야 하는 내용이 있는지 확인하는 과정을 안내합니다.

또한 Microsoft가 적격 서비스의 성공적인 도입에 도움이 되는 방법에 대한 안내로 사용자를 연결합니다.

Microsoft는 사용자의 현재 설정을 기준으로 하여 EMS 또는 개별 클라우드 서비스에 등록하기 위한 최소 요구 사항에 부합하도록 원본 환경을 업그레이드하는 수정 플랜을 제공합니다. 또한 수정 단계를 위한 검사점 호출도 적절히 설정합니다.

![온보딩 평가 단계](./media/ft-4-assess-phase.png)

## 수정 단계
필요한 경우 각 서비스를 등록 및 도입하기 위한 요구 사항을 충족하도록 원본 환경에서 수정 플랜의 작업을 수행합니다.

![온보딩 문제 해결 단계](./media/ft-5-remediate-phase.png)

활성화 단계를 시작하기 전에 Microsoft는 수정 작업의 결과를 공동으로 확인하여 다음 단계를 진행할 준비가 되었는지 확인합니다.

## 활성화 단계
수정 작업이 모두 완료되면 프로젝트는 서비스 사용을 위한 핵심 인프라 구성 및 각각의 적격 EMS 클라우드 서비스 프로비저닝으로 전환됩니다.

**활성화 단계 - 핵심 기능**

코어 등록에는 서비스 프로비저닝과 테넌트 및 ID 통합이 포함됩니다. 또한 Azure Active Directory Premium, Microsoft Intune 및 Azure Rights Management Premium 등과 같은 온라인 서비스 등록을 위한 기초 정보를 제공하는 단계가 포함되어 있습니다.

![온보딩 활성화 단계 - 핵심 기능](./media/ft-6-enable-phase-core.png)

###활성화 단계 - Azure Active Directory Premium

Azure Active Directory Premium 환경은 필요에 따라 Azure Active Directory Connect 도구 디렉터리 동기화 및 AD FS(Active Directory Federation Services)로 설정할 수 있습니다.

온-프레미스 ID를 클라우드에 동기화를 포함하는 Azure Active Directory Premium 시나리오의 경우 IT 관리자와 사용자 추가, 관리 사전 요구 사항 구성, Azure Active Directory Premium 설정, Azure Active Directory Connect도구를 사용하는 디렉터리 동기화 및 Azure Active Directory Connect 도구를 사용하는 AD FS(Active Directory Federation Services) 설정, 테스트 사용자 구성 및 해당 서비스에 대한 핵심 사용 케이스를 확인을 제공하여 사용자를 돕습니다.

Azure Active Directory Premium 설치에는 다음과 같은 기능을 사용하도록 설정하는 것이 포함됩니다.

-   SSPR(셀프 서비스 암호 재설정)

-   MFA(Multi-Factor Authentication)

-   SaaS(Software as a Service) 응용 프로그램 - [Azure Active Directory 마켓플레이스](https://azure.microsoft.com/marketplace/active-directory/)에서 단일 SaaS 응용 프로그램 설정.

-   SSGM(셀프 서비스 그룹 관리)

-   관리 보고서

![온보딩 활성화 단계 - AADP](./media/ft-7-enable-phase-aadp.png)

###활성화 단계 – Microsoft Intune

Microsoft Intune의 경우 Microsoft는 사용자의 모바일 장치 및 모바일 응용 프로그램 관리 요구 사항에 따라 Microsoft Intune을 사용하여 장치를 관리할 수 있도록 준비하는 과정을 안내합니다. 정확한 단계는 원본 환경에 따라 다르며 다음 작업이 포함될 수 있습니다.

-   최종 사용자 라이선싱. 필요한 경우 Microsoft 클라우드 서비스 테넌트에 대한 볼륨 라이선스를 활성화하는 방법의 지원도 제공합니다.

-   온-프레미스 Active Directory 또는 클라우드 ID를 활용하여 Microsoft Intune에서 사용할 ID 구성.

-   Microsoft Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   관리 요구 사항에 따라 다음과 같이 모바일 장치 관리 기관 구성.

    -   Microsoft Intune이 유일한 MDM 솔루션이거나 Office 365용 모바일 장치 관리와 함께 사용되는 경우 Microsoft Intune을 MDM 기관으로 설정합니다.

    -   System Center Configuration Manager의 기존 구현이 있고 Microsoft Intune으로 관리 기능을 확장하려는 경우 Configuration Manager를 MDM 기관으로 설정합니다.

        > [!NOTE]
        > 최종 사용자 소유 장치, 공유 장치 또는 키오스크 유형 장치에서만 모바일 응용 프로그램 관리를 활용하려는 경우 MDM 기관을 설정할 필요가 없습니다.

-   모바일 장치 관리가 범위에 포함되는 경우 다음과 관련된 지침을 제공합니다.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   다음과 같은 MDM 관리 정책 및 서비스 구성.

        -   지원되는 각 플랫폼에 대해 웹 링크 또는 딥 링크를 통한 응용 프로그램 배포.

        -   조건부 액세스 정책.

        -   메일 프로필 배포.

        -   해당되는 경우 Microsoft Intune Exchange Connector 설정.

    -   각각의 [지원되는 각 플랫폼](https://technet.microsoft.com/library/dn600287.aspx) 장치를 Microsoft Intune 또는 Configuration Manager with Microsoft Intune 서비스에 등록.

-   MAM(모바일 응용 프로그램 관리)이 범위에 포함된 경우나 기존 Microsoft 또는 타사 MDM 솔루션을 MAM 정책으로 보완하려는 경우 Microsoft는 다음과 관련된 지침을 제공합니다.

    -   지원되는 각 플랫폼에 대한 MAM 정책 구성.

    -   관리되는 앱에 대한 조건부 액세스 정책 구성.

    -   위의 MAM 정책에서 적절한 사용자 그룹을 대상으로 지정.

    -   관리되는 응용 프로그램 사용 현황 보고서 사용.

-   PC 관리가 범위에 포함되는 경우 다음과 관련된 지침을 제공합니다.

    -   필요한 경우 Intune 클라이언트 소프트웨어 설치.

    -   Intune에서 사용할 수 있는 소프트웨어 및 하드웨어 보고서 사용.

또한 Microsoft가 적격 서비스의 성공적인 도입에 도움이 되는 방법에 대한 안내로 사용자를 연결합니다.

![온보딩 활성화 단계 - Intune](./media/ft-8-enable-phase-intune.png)

###활성화 단계 - Azure Right Management Premium

Azure Right Management Premium 환경은 필요에 따라 Azure Active Directory Connect 디렉터리 동기화 및 AD FS(Active Directory Federation Services)로 설정할 수 있습니다.

클라우드에 대한 온-프레미스 ID 동기화를 포함하는 AzRMS 시나리오의 경우 IT 관리자와 사용자 추가, 관리 사전 요구 사항 구성, Azure Right Management Premium 설정, Azure Active Directory Connect 도구를 사용하는 디렉터리 동기화 및 Azure Active Directory Connect를 사용하는 AD FS(Active Directory Federation Services) 설정, 테스트 사용자 구성 및 해당 서비스에 대한 핵심 사용 케이스를 확인을 제공하여 사용자를 돕습니다.

AzRMS 설치에는 다음 기능을 사용하도록 지정하는 것이 포함됩니다.

-   RMS 서비스 사용

-   Exchange Online 및 Sharepoint Online용 IRM 구성

-   Exchange 온-프레미스 및 Sharepoint 온-프레미스를 사용하는 권한 관리 커넥터

-   Windows 장치 및 Windows 이외 장치를 위한 RMS 공유 응용 프로그램

![온보딩 활성화 단계 - Azure RMS](./media/ft-7-enable-phase-aadp.png)

FastTrack 온보딩 프로세스의 다음 부분인 [Microsoft 책임](fasttrack-center-benefit-process-for-ems-microsoft-responsibilities.md)에 대해 읽어 보세요.

### 더 자세한 내용을 원하세요?
[Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 참조하세요..



<!--HONumber=Apr16_HO5-->


