---
title: FastTrack 책임
description: 고객이 EMS용 FastTrack Center 혜택을 사용할 때의 FastTrack 책임
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: dc86c1a3cba21476c6f5275dfd589bdb5443466a
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196796"
---
# <a name="fasttrack-responsibilities"></a>FastTrack 책임

등록 시 FastTrack의 책임은 다음과 같습니다.

## <a name="general"></a>일반

-   자세한 단계 설명에 나와 있는 필수 구성 작업에 대한 원격 지원을 제공합니다.

-   사용 가능한 설명서와 소프트웨어 도구 및 관리 콘솔을 제공하여 구성 작업을 줄이거나 없앨 수 있도록 도와줍니다.

## <a name="initiate-phase"></a>시작 단계

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

-   Intune 및 Azure AD Premium 모두에 대한 수정 점검 목록을 제공합니다.

## <a name="remediate-phase"></a>수정 단계

-   합의된 일정에 따라 전화 회의를 개최하여 수정 활동의 진행 상황을 검토합니다. 예를 들어 Microsoft 클라우드 서비스를 온보딩하기 전에 설치 전제 조건을 안내합니다.

## <a name="enable-phase"></a>활성화 단계
다음에 대한 지침을 제공합니다.

-   Microsoft 온라인 서비스 테넌트 또는 구독 활성화.

-   TCP/IP 프로토콜 및 방화벽 포트 구성.

-   적격 서비스에 대한 DNS 구성.

-   Microsoft 온라인 서비스에 대한 연결의 유효성 검사.

-   단일 포리스트 환경의 경우:

    -   AD DS(Active Directory Domain Services)와 적격 Microsoft 온라인 서비스 간의 디렉터리 동기화 서버 설치(필요한 경우에만 안내).

    -   Azure Active Directory Connect 도구를 사용하여 관리 인증(암호 해시 동기화 또는 통과 인증) 구성 (필요한 경우에만 안내).

        > [!NOTE]
        > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

-   대상이 페더레이션 ID인 경우 단일 포리스트: 필요한 경우 단일 사이트 내결함성 구성에서 Intune을 사용한 로컬 도메인 인증을 위해 AD FS(Active Directory Federation Services)설치 및 구성.

    > [!NOTE]
    > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

-   배포한 경우 SSO(Single Sign-On) 기능 테스트.

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>사용 설정 단계 - Microsoft Azure Active Directory Premium

다음에 대한 지침을 제공합니다.

- Azure AD Premium 테넌트 활성화.

- 방화벽 포트 구성.

- 적격 서비스에 대한 DNS 구성.

- Azure AD Premium 서비스에 대한 연결의 유효성 검사.

- 단일 포리스트 환경의 경우:

  -   필요한 경우 AD DS(Active Directory Domain Services) 및 Azure AD Connect 간의 디렉터리 동기화 설치.

  -   Azure AD Connect 도구를 사용하여 인증 방법(암호 해시 동기화 또는 통과 인증) 구성

- 다중 포리스트 환경의 경우:

  -   Azure AD Connect 동기화를 설치하고, 다중 포리스트 시나리오를 설정합니다.
- 단일 및 다중 포리스트 환경의 경우:
  - 필요한 경우 Azure Active Directory 통과 인증을 구성합니다.
  - 필요한 경우 Azure Active Directory 원활한 SSO(Single Sign-On)를 구성합니다.
    > [!NOTE]
    > 다중 포리스트 환경에 대한 Azure Active Directory 통과 인증은 Active Directory 포리스트 간에 포리스트 트러스트가 있는 경우 및 이름 접미사 라우팅이 올바르게 구성된 경우에 지원됩니다. 추가 에이전트를 여러 온-프레미스 서버에 설치하여 로그인 요청에 고가용성을 제공할 수 있습니다.

  - 자세한 내용은 [Azure Active Directory 통과 인증: 빠른 시작](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-quick-start#step-1-check-prerequisites) 및 [Azure Active Directory Seamless Single Sign-On: 빠른 시작](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start#step-1-check-prerequisites)을 참조하세요.
  - 통과 인증 제한 사항에 대한 자세한 내용은 [Azure Active Directory 통과 인증: 현재 제한 사항](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-current-limitations)을 참조하세요.
  - Seamless SSO 문제에 대한 자세한 내용은 [Azure Active Directory Seamless Single Sign-On 문제 해결](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-troubleshoot-sso)을 참조하세요.

      > [!NOTE]
      > 암호 해시 동기화 및 비밀번호 쓰기 저장은 다중 포리스트를 지원합니다. 그러나 다른 쓰기 저장 시나리오는 지원되지 않습니다.

  - 온-프레미스 Active Directory 포리스트와 Microsoft Azure Active Directory Premium 디렉터리(Azure Active Directory) 간의 동기화 구성.

    > [!NOTE]
    > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

- 대상이 페더레이션 ID인 경우 단일 포리스트:

  -   필요한 경우 단일 사이트 내결함성 구성에서 Azure AD Premium을 사용한 로컬 도메인 인증을 위해 AD FS 설치 및 구성.

  > [!NOTE]
  > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

- 배포한 경우 SSO(Single Sign-On) 기능 테스트.

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>활성화 단계 - Azure AD Premium(Azure AD Connect 및 AD FS 포함)

설정에 대한 지침을 제공 합니다.

- 라이선스를 포함한 사용자 프로비저닝.

- Azure AD Connect 디렉터리 동기화(비밀번호 쓰기 저장 및 암호 해시 동기화).

  - SSPR(셀프 서비스 암호 재설정)

  - Azure Multi-Factor Authentication.

  - [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/)에서 최대 3개 이상의 SaaS(Software as a Service) 응용 프로그램과 SSO 통합

  - [앱 통합 자습서 목록](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/tutorial-list)에 나열된 대로 사전 통합된 SaaS 애플리케이션에 대한 자동 사용자 프로비전(아웃바운드 프로비전으로만 제한됨)

  - 사용자 지정된 로그온 화면(로고, 텍스트 및 이미지 포함)

  - 셀프 서비스 및 동적 그룹.

  - Azure Active Directory 응용 프로그램 프록시

  - Azure AD Connect Health.

  - ID 보호

  - Privileged Identity Management

  - Azure Active Directory 조건부 액세스(필요한 경우 사용 약관 포함)

### <a name="enable-phase---intune"></a>활성화 단계 - Intune

> [!IMPORTANT]
> FastTrack은 Intune을 사용한 Windows 10 클래식 PC 관리를 지원하지 않습니다. FastTrack은 Intune 모바일 장치 관리(MDM)를 통한 Windows 10 관리만 지원합니다.

다음에 대한 **지침**을 제공합니다.

-   온-프레미스 Active Directory 또는 클라우드 ID(Azure Active Directory)를 활용하여 Intune에서 사용할 ID 구성.

-   최종 사용자 라이선싱.

-   Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   관리 요구 사항에 따라 다음과 같이 모바일 장치 관리(MDM) 기관 구성.

    -   Intune을 MDM 기관으로 설정.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   Intune 관리 포털을 탐색하여 사용자 및 장치에 대한 정보 찾기.

    -   Intune 역할 설정(예: 지원 센터, 운영자, 관리자 등)

    -   다음과 같은 MDM 관리 정책 및 서비스 구성:

        -   지원되는 각 플랫폼에 대해 웹 링크, MSI 및/또는 딥 링크를 통한 앱 배포.

        -   Windows 10 장치에 Office ProPlus 배포.

        -   Apple VPP, Windows Store for Business 및 Google Play for Work Store 등 앱 배포를 위한 대량 구매 프로그램.

        -   조직에 기존 인증 기관, Wi-Fi 또는 VPN 인프라가 있는 경우 메일, 무선 네트워크 및 VPN 프로필 배포.

        -   해당되는 경우 Microsoft Intune Exchange Connector 설정.

        -   지원되는 장치 플랫폼에 대한 장치 구성 프로파일.

    -   조건부 액세스 정책 설정.

    -   지원되는 각 플랫폼에 대해 Intune 앱 보호 정책 구성 및 배포.

    -   사용 가능한 옵션에 대한 지침과 함께 Intune 앱 보호 정책을 위한 LOB(기간 업무) 앱 준비.

    -   각각의 지원되는 각 플랫폼 장치를 Intune 또는 Configuration Manager with Microsoft Intune 서비스에 등록.

    -   Intune 데이터 웨어하우스에 연결.

    -   Intune을 다음과 통합:
        -   원격 지원을 위한 Team Viewer(Team Viewer 구독 필요).

        -   Mobile Threat Defense 파트너 솔루션(Mobile Threat Defense 파트너 솔루션 구독 필요).

        -   Telecom Expense Management 솔루션(Telecom Expense Management 솔루션 구독 필요).

        -   Windows Defender Advanced Threat Protection(Windows E5 또는 Microsoft 365 E5 라이선스 필요).

    -   적용 가능한 지원되는 플랫폼을 위해 소프트웨어 업데이트 구성.

    -   사용자 채택 계획을 위한 리소스.

- Windows Autopilot 설정:

    - Windows Autopilot용 Microsoft Intune을 구성하고 설정합니다.

    - Azure AD 동적 그룹 구성

    - Azure AD에 회사 브랜딩을 추가합니다.

    - Windows Autopilot 프로필을 만들고 디바이스를 할당합니다(예: 로컬 관리자 계정 만들기를 제한하는 Windows Autopilot 프로필).

    - 조직의 요구 사항에 맞도록 OOBE(Out-Of-Box-Experience)를 사용자 지정합니다.

    - Azure AD 및 Intune에서 MDM 자동 등록을 구성합니다.

    > [!NOTE]
    > Intune 외부에서 Windows Autopilot 설정은 FastTrack 혜택의 범위를 벗어납니다.

### <a name="enable-phase---co-management"></a>활성화 단계 - 공동 관리

다음에 대한 지침을 제공합니다.

-   최종 사용자 라이선싱.

-   Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기(Intune이 설치되지 않은 경우).

-   MDM 자동 등록을 위한 Azure Active Directory 설정.

-   하이브리드 Azure Active Directory 조인 설정.

-   클라우드 관리 게이트웨이 설정.

-   Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   Intune 준비(Intune이 설치되지 않은 경우):

    -   관리 요구 사항에 따라 다음과 같이 모바일 장치 관리(MDM) 기관 구성.

    -   Intune을 MDM 기관으로 설정.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   Intune 관리 포털을 탐색하여 사용자 및 장치에 대한 정보 찾기.

    -   Intune 역할 설정(예: 지원 센터, 운영자, 관리자 등)

    -   지원되는 각 플랫폼에 대해 Intune 앱 보호 정책 구성 및 배포.

    -   Intune에 Windows 10 장치 등록.

- Configuration Manager 콘솔에서 공동 관리를 사용하도록 설정.

- 워크로드를 Intune으로 전환.

- 환경에서 공동 관리 활동 모니터링.

> [!NOTE]
> **자세히 알아보고 싶습니까?** [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility)를 참조하세요.

## <a name="next-steps"></a>다음 단계

[EMS용 FastTrack 혜택 - 사용자의 책임](fasttrack-center-benefit-process-for-ems-your-responsibilities.md)
