---
title: "Microsoft의 책임"
description: "고객이 FastTrack 센터 혜택을 사용할 때의 Microsoft 책임"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 102ff22c60aa58cddbc07ddd485a57e9e7340a92
ms.sourcegitcommit: 024fad70d2c4976f039e3e572c7334927375b17e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="microsoft-responsibilities"></a>Microsoft의 책임

등록 시 Microsoft에서 이행해야 하는 의무는 다음과 같습니다.

## <a name="general"></a>일반

-   자세한 단계 설명에 나와 있는 필수 구성 작업에 대한 원격 지원을 제공합니다.

-   사용 가능한 설명서와 소프트웨어 도구, 관리 콘솔 및 스크립트를 제공하여 구성 작업을 줄이거나 없앨 수 있도록 도와줍니다.

## <a name="initiate-phase"></a>시작 단계

-   새 테넌트에 대한 적격 라이선스 구매일로부터 30일 이내에 사용자에게 연락합니다.

-   등록을 시작할 수 있도록 협업합니다.

-   등록할 적격 서비스를 정의합니다.

## <a name="assess-phase"></a>평가 단계

-   관리 개요를 제공합니다.

-   다음에 대한 지침을 제공합니다.

    -   DNS, 네트워크 및 인프라 요구 사항.

    -   클라이언트 요구 사항(인터넷 브라우저, 클라이언트 운영 체제 및 서비스 요구 사항).

    -   사용자 ID 및 프로비저닝.

    -   이미 구매되었으며 등록의 일부로 정의된 적격 서비스 활성화.

-   수정 작업에 대한 타임라인을 설정합니다.

-   수정 검사 목록을 제공합니다.

## <a name="remediate-phase"></a>수정 단계

-   합의된 일정에 따라 전화 회의를 열어 수정 작업의 진행률을 검토합니다.

-   도구를 실행하여 문제를 식별 및 해결하고 결과를 해석하는 과정을 지원합니다.

## <a name="enable-phase"></a>활성화 단계
다음에 대한 지침을 제공합니다.

-   Microsoft 온라인 서비스 테넌트 활성화.

-   TCP/IP 프로토콜 및 방화벽 포트 구성.

-   적격 서비스에 대한 DNS 구성.

-   Microsoft 온라인 서비스에 대한 연결의 유효성 검사.

-   단일 포리스트 환경의 경우:

    -   필요한 경우 AD DS(Active Directory Domain Services)와 적격 Microsoft 온라인 서비스 간의 디렉터리 동기화 서버 설치.

    -   Microsoft Intune(Azure Active Directory)과 Azure Active Directory Connect 도구의 암호 동기화(암호 해시) 구성.

        > [!NOTE]
        > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

-   대상이 페더레이션 ID인 경우 단일 포리스트: 필요한 경우 단일 사이트 내결함성 구성에서 Intune을 사용한 로컬 도메인 인증을 위해 AD FS(Active Directory Federation Services)설치 및 구성.

    > [!NOTE]
    > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

-   배포한 경우 SSO(Single Sign-On) 기능 테스트.

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>사용 설정 단계 - Microsoft Azure Active Directory Premium

다음에 대한 지침을 제공합니다.

-   Azure AD Premium 테넌트 활성화.

-   방화벽 포트 구성.

-   적격 서비스에 대한 DNS 구성.

-   Azure AD Premium 서비스에 대한 연결의 유효성 검사.

-   단일 포리스트 환경의 경우:

    -   필요한 경우 AD DS(Active Directory Domain Services) 및 Azure AD Connect 간의 디렉터리 동기화 설치.

    -   Azure AD Connect 도구를 사용하여 인증 방법(암호 해시 동기화 또는 통과 인증) 구성

-   다중 포리스트 환경의 경우:

    -   Azure AD Connect 동기화를 설치하고, 다중 포리스트 시나리오를 설정합니다.
-   단일 및 다중 포리스트 환경의 경우:
    -   필요한 경우 Azure Active Directory 통과 인증을 구성합니다.
    -   필요한 경우 Azure Active Directory 원활한 SSO(Single Sign-On)를 구성합니다. 
        > [!NOTE]
        > 다중 포리스트 환경에 대한 Azure Active Directory 통과 인증은 Active Directory 포리스트 간에 포리스트 트러스트가 있는 경우 및 이름 접미사 라우팅이 올바르게 구성된 경우에 지원됩니다. 추가 에이전트를 여러 온-프레미스 서버에 설치하여 로그인 요청에 고가용성을 제공할 수 있습니다. 

    - 자세한 내용은 [Azure Active Directory 통과 인증: 빠른 시작](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-quick-start#step-1-check-prerequisites) 및 [Azure Active Directory 원활할 Single Sign-On: 빠른 시작](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start#step-1-check-prerequisites)을 참조하세요.
    - 통과 인증 제한에 대한 자세한 내용은 [Azure Active Directory 통과 인증: 현재 제한 사항](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-current-limitations)을 참조하세요.
    - 원활한 SSO 문제에 대한 자세한 내용은 [Azure Active Directory 원활한 Single Sign-On 문제 해결](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-troubleshoot-sso)을 참조하세요.
  
        > [!NOTE]
        > 암호 해시 동기화 및 비밀번호 쓰기 저장은 다중 포리스트를 지원합니다. 그러나 다른 쓰기 저장 시나리오는 지원되지 않습니다.

    -   온-프레미스 Active Directory 포리스트와 Microsoft Azure Active Directory Premium 디렉터리(Azure Active Directory) 간의 동기화 구성.

        > [!NOTE]
        > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

-   대상이 페더레이션 ID인 경우 단일 포리스트:

    -   필요한 경우 단일 사이트 내결함성 구성에서 Azure AD Premium을 사용한 로컬 도메인 인증을 위해 AD FS 설치 및 구성.

    > [!NOTE]
    > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

-   배포한 경우 SSO(Single Sign-On) 기능 테스트.

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>활성화 단계 - Azure AD Premium(Azure AD Connect 및 AD FS 포함)

설정에 대한 지침을 제공 합니다.

-   라이선스를 포함한 사용자 프로비저닝.

-   Azure AD Connect 디렉터리 동기화(비밀번호 쓰기 저장 및 암호 해시 동기화).

  - SSPR(셀프 서비스 암호 재설정)

  - Azure Multi-Factor Authentication.

  - [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/)에서 최대 3개 이상의 SaaS(Software as a Service) 응용 프로그램과 SSO 통합

  - 사용자 지정된 로그온 화면(로고, 텍스트 및 이미지 포함)

  - 셀프 서비스 및 동적 그룹.

  - Azure Active Directory 응용 프로그램 프록시

  - Azure AD Connect Health.

  - ID 보호

  - Privileged Identity Management
  
  - Azure Active Directory 조건부 액세스 

  - 관리자를 위한 사용량 및 보안 보고서.

  - 관리 알림 및 경고

### <a name="enable-phase---intune"></a>활성화 단계 - Intune
다음에 대한 지침을 제공합니다.

-   최종 사용자 라이선싱.

-   온-프레미스 Active Directory 또는 클라우드 ID를 활용하여 Intune에서 사용할 ID 구성.

-   Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   관리 요구 사항에 따라 다음과 같이 모바일 장치 관리(MDM) 기관 구성.

    -   Intune이 유일한 MDM 솔루션이거나 Office 365용 모바일 장치 관리와 함께 사용되는 경우 Intune을 MDM 기관으로 설정합니다.

    -   System Center Configuration Manager의 기존 구현이 있고 Intune으로 관리 기능을 확장하려는 경우 Configuration Manager를 MDM 기관으로 설정합니다.

        > [!NOTE]
        > 최종 사용자가 소유한 장치, 공유 장치 또는 키오스크 유형 장치에서만 MDM을 활용하려는 경우에는 MDM 기관을 설정할 필요가 없습니다.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   다음과 같은 MDM 관리 정책 및 서비스 구성:

        -   지원되는 각 플랫폼에 대해 웹 링크 또는 딥 링크를 통한 응용 프로그램 배포.

        -   조건부 액세스 정책.

        -   조직에 기존 인증 기관, Wi-Fi 또는 VPN 인프라가 있는 경우 메일, 무선 네트워크 및 VPN 프로필 배포.

        -   해당되는 경우 Microsoft Intune Exchange Connector 설정.

    -   각각의 지원되는 각 플랫폼 장치를 Intune 또는 Configuration Manager with Microsoft Intune 서비스에 등록.

    -   하드웨어 및 소프트웨어 인벤토리 보고서 사용.

    -   지원되는 각 플랫폼에 대한 MAM 정책 구성.

    -   관리되는 앱에 대한 조건부 액세스 정책 구성.

    -   위의 MAM 정책에서 적절한 사용자 그룹을 대상으로 지정.

    -   관리되는 응용 프로그램 사용 현황 보고서 사용.

    -   필요한 경우 Intune 클라이언트 소프트웨어 설치

    -   Intune에서 사용할 수 있는 소프트웨어 및 하드웨어 보고서 사용.

**더 자세한 내용을 원하세요?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
