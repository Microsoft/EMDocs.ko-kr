---
title: "등록 및 마이그레이션 단계"
description: "FastTrack 센터 혜택의 단계"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 0c404c758f66fba9ded4672fad904ba3987958b5
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="onboarding-and-migration-phases"></a>등록 및 마이그레이션 단계
[FastTrack 센터 혜택 적격 서비스 및 플랜](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)을 통해 사용할 Microsoft Azure Active Directory Premium 및/또는 Microsoft Intune을 가져올 때는 프로세스와 관련한 몇 가지 단계가 있습니다. 다음 섹션에서는 등록 프로세스의 각 단계를 설명합니다.

등록은 다음과 같이 크게 네 가지 단계로 구성됩니다.

![FastTrack 온보딩 프로세스의 네 단계](./media/ft-onboarding-benefit.png)


## <a name="initiate-phase"></a>시작 단계

적절한 수량의 라이선스를 구매한 후 구매 확인 메일의 지침에 따라 라이선스를 기존 테넌트나 새 테넌트에 연결하세요. Microsoft에서 FastTrack 센터 혜택의 적용 자격 여부를 확인하며 시작 지원을 위한 연락을 시도합니다. 조직이 이러한 서비스를 배포할 준비가 되어 있는 경우 [FastTrack 센터](http://fasttrack.microsoft.com/) 에서 지원을 요청할 수도 있습니다.

지원을 요청하려면에 회사 또는 학교 계정으로 [FastTrack 센터](http://fasttrack.microsoft.com/)에 로그인한 후 대시보드로 이동하여 화면 왼쪽에 있는 **도움 필요**를 확장하고 메시지에 따라 요청을 완료합니다. 등록 지원이 시작되면 Microsoft는 온라인 모임 일정을 설정합니다.

이 단계에서 Microsoft는 등록 프로세스를 논의하고, 데이터를 확인하고, 준비 모임 일정을 정합니다.

![온보딩 시작 단계](./media/ft-initiate-phase.png)

## <a name="assess-phase"></a>평가 단계

등록 프로세스가 시작되면 Microsoft는 사용자와 협업하여 원본 환경 및 요구 사항을 평가합니다. 환경을 평가하기 위한 도구가 실행되고 Microsoft는 사용자가 온-프레미스 Active Directory, 인터넷 브라우저, 클라이언트 장치의 운영 체제, DNS(Domain Name System), 네트워크, 인프라 및 ID 시스템을 평가하여 등록을 위해 변경해야 하는 내용이 있는지 확인하는 과정을 안내합니다.

또한 Microsoft가 적격 서비스의 성공적인 도입에 도움이 되는 방법에 대한 안내로 사용자를 연결합니다.

Microsoft는 사용자의 현재 설정을 기준으로 하여 EMS 또는 개별 클라우드 서비스에 등록하기 위한 최소 요구 사항에 부합하도록 원본 환경을 업그레이드하는 수정 플랜을 제공합니다. 또한 수정 단계를 위한 검사점 호출도 적절히 설정합니다.

![온보딩 평가 단계](./media/ft-assess-phase.png)

## <a name="remediate-phase"></a>수정 단계
각 서비스를 등록 및 도입하기 위한 요구 사항을 충족하도록 원본 환경에서 수정 플랜의 작업을 수행합니다.

![온보딩 문제 해결 단계](./media/ft-remediate-phase.png)

활성화 단계를 시작하기 전에 Microsoft는 수정 작업의 결과를 공동으로 확인하여 다음 단계를 진행할 준비가 되었는지 확인합니다.

## <a name="enable-phase"></a>활성화 단계
수정 작업이 모두 완료되면 프로젝트는 서비스 사용을 위한 핵심 인프라 구성 및 각각의 적격 EMS 클라우드 서비스 프로비저닝으로 전환됩니다.

**활성화 단계 - 핵심 기능**

코어 등록에는 서비스 프로비저닝과 테넌트 및 ID 통합이 포함됩니다. 또한 Azure AD Premium 및 Intune과 같은 온라인 서비스 등록을 위한 기초 정보를 제공하는 단계도 포함됩니다.

![온보딩 활성화 단계 - 핵심 기능](./media/ft-enable-phase-core-01.png)

![온보딩 활성화 단계 - 핵심 기능](./media/ft-enable-phase-core-02.png)

### <a name="enable-phase---azure-ad-premium"></a>활성화 단계 - Azure AD Premium

Azure AD Premium 환경은 필요에 따라 Azure Active Directory Connect 도구 디렉터리 동기화 및 AD FS(Active Directory Federation Services)를 사용하여 설정할 수 있습니다.

온-프레미스 ID를 클라우드에 동기화하는 작업이 포함된 Azure AD Premium 시나리오에서는 구독에 IT 관리자와 사용자 추가, 관리 사전 요구 사항 구성, Azure AD Premium 설정, Azure AD Connect 도구를 사용하는 디렉터리 동기화 및 AD FS 설정, 테스트 사용자 구성, 해당 서비스에 대한 핵심 사용 사례 확인 기능을 제공하여 사용자를 지원합니다.

Azure AD Premium 설치에는 다음과 같은 기능을 사용하도록 설정하는 것이 포함됩니다.

-   SSPR(셀프 서비스 암호 재설정)

-   Azure MFA(Azure Multi-Factor Authentication)

-   [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/)에서 SaaS(Software as a Service) 앱 하나와 SSO(Single Sign On)의 통합

-   사용자 지정된 로그온 화면(로고, 텍스트 및 이미지 포함)

-   셀프 서비스 및 동적 그룹.

-   Azure Active Directory 응용 프로그램 프록시

-   Azure Active Directory Connect Health

-   ID 보호

-   Privileged Identity Management

-   관리자를 위한 사용량 및 보안 보고서.

-   관리 알림 및 경고

![등록 활성화 단계 - Azure AD Premium](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### <a name="enable-phase---intune"></a>활성화 단계 - Intune

Intune의 경우 Microsoft는 Microsoft Intune을 사용하여 장치를 관리할 수 있도록 준비하는 과정을 안내합니다. 정확한 단계는 원본 환경에 따라 다르며 모바일 장치 및 모바일 앱 관리 요구를 기반으로 합니다. 단계에는 다음이 포함될 수 있습니다.

-   최종 사용자 라이선싱. 필요한 경우 Microsoft 클라우드 서비스 테넌트에 대한 볼륨 라이선스를 활성화하는 방법의 지원도 제공합니다.

-   온-프레미스 Active Directory 또는 클라우드 ID를 활용하여 Microsoft Intune에서 사용할 ID 구성.

-   Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   관리 요구 사항에 따라 다음과 같이 모바일 장치 관리(MDM) 기관 구성.

    -   Intune이 유일한 MDM 솔루션이거나 Office 365용 모바일 장치 관리와 함께 사용되는 경우 Intune을 MDM 기관으로 설정합니다.

    -   System Center Configuration Manager의 기존 구현이 있고 Intune으로 관리 기능을 확장하려는 경우 Configuration Manager를 MDM 기관으로 설정합니다.

        > [!NOTE]
        > 최종 사용자가 소유한 장치, 공유 장치 또는 키오스크 유형 장치에서만 MDM을 활용하려는 경우에는 MDM 기관을 설정할 필요가 없습니다.

-   다음에 대한 MDM 지침을 제공합니다.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   다음과 같은 MDM 관리 정책 및 서비스 구성:

        -   지원되는 각 플랫폼에 대해 웹 링크 또는 딥 링크를 통한 응용 프로그램 배포.

        -   조건부 액세스 정책.

        -   조직에 기존 인증 기관, Wi-Fi 또는 VPN(가상 사설망) 인프라가 있는 경우 메일, 무선 네트워크 및 VPN 프로필 배포.

        -   해당되는 경우 Microsoft Intune Exchange Connector 설정.

    -   각각의 [지원되는 각 플랫폼](https://technet.microsoft.com/library/dn600287.aspx) 장치를 Intune 또는 Configuration Manager with Microsoft Intune 서비스에 등록.

-   다음에 대한 모바일 응용 프로그램 관리(MAM) 지침을 제공합니다.

    -   지원되는 각 플랫폼에 대한 MAM 정책 구성.

    -   관리되는 앱에 대한 조건부 액세스 정책 구성.

    -   위의 MAM 정책에서 적절한 사용자 그룹을 대상으로 지정.

    -   관리되는 응용 프로그램 사용 현황 보고서 사용.

-   다음에 대한 PC 관리 지침을 제공합니다.

    -   필요한 경우 Intune 클라이언트 소프트웨어 설치

    -   Intune에서 사용할 수 있는 소프트웨어 및 하드웨어 보고서 사용.

또한 Microsoft가 적격 서비스의 성공적인 도입에 도움이 되는 방법에 대한 안내로 사용자를 연결합니다.

![온보딩 활성화 단계 - Intune](./media/ft-enable-phase_intune_mam.png)

![온보딩 활성화 단계 - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![온보딩 활성화 단계 - Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

**더 자세한 내용을 원하세요?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
