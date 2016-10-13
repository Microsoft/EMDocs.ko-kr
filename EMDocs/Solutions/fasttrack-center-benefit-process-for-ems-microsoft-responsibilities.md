---
title: "Microsoft의 책임"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 323bdb56b3d81eb6a63e266899427672abf79da4
ms.openlocfilehash: 777236784c06eeea2e62bcb77b2ceabc5d31b14a


---

# Microsoft의 책임

등록 시 Microsoft에서 이행해야 하는 의무는 다음과 같습니다.

## 일반

-   자세한 단계 설명에 나와 있는 필수 구성 작업에 대한 원격 지원을 제공합니다.

-   사용 가능한 설명서와 소프트웨어 도구, 관리 콘솔 및 스크립트를 제공하여 구성 작업을 줄이거나 없앨 수 있도록 도와줍니다.

## 시작 단계

-   새 테넌트에 대한 적격 라이선스 구매일로부터 30일 이내에 사용자에게 연락합니다.

-   등록을 시작할 수 있도록 협업합니다.

-   등록할 적격 서비스를 정의합니다.

## 평가 단계

-   관리 개요를 제공합니다.

-   다음에 대한 지침을 제공합니다.

    -   DNS, 네트워크 및 인프라 요구 사항.

    -   클라이언트 요구 사항(인터넷 브라우저, 클라이언트 운영 체제 및 서비스 요구 사항).

    -   사용자 ID 및 프로비저닝.

    -   이미 구매되었으며 등록의 일부로 정의된 적격 서비스 활성화.

-   수정 작업에 대한 타임라인을 설정합니다.

-   수정 검사 목록을 제공합니다.

## 수정 단계

-   합의된 일정에 따라 전화 회의를 열어 수정 작업의 진행률을 검토합니다.

-   도구를 실행하여 문제를 식별 및 해결하고 결과를 해석하는 과정을 지원합니다.

## 활성화 단계
다음에 대한 지침을 제공합니다.

-   Microsoft 온라인 서비스 테넌트 활성화.

-   TCP/IP 프로토콜 및 방화벽 포트 구성.

-   적격 서비스에 대한 DNS 구성.

-   Microsoft 온라인 서비스에 대한 연결의 유효성 검사.

-   단일 포리스트 환경의 경우:

    -   필요한 경우 AD DS(Active Directory 도메인 서비스)와 적격 Microsoft 온라인 서비스 간의 디렉터리 동기화 서버 설치.

    -   Microsoft Intune(Azure Active Directory)과 Azure Active Directory Connect 도구의 암호 동기화(암호 해시) 구성.

        > [!NOTE]
        > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

-   대상이 페더레이션 ID인 경우 단일 포리스트: 필요한 경우 단일 사이트 내결함성 구성에서 Microsoft Intune을 사용한 로컬 도메인 인증을 위해 AD FS(Active Directory Federation Services)설치 및 구성.

    > [!NOTE]
    > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

-   배포한 경우 SSO(Single Sign-On) 기능 테스트.

### 활성화 단계 - Azure Active Directory Premium

다음에 대한 지침을 제공합니다.

-   Microsoft Azure AD Premium 테넌트 활성화.

-   방화벽 포트 구성.

-   적격 서비스에 대한 DNS 구성.

-   Microsoft Azure Active Directory Premium 서비스에 대한 연결의 유효성 검사.

-   단일 포리스트 환경의 경우:

    -   필요한 경우 AD DS(Active Directory 도메인 서비스) 및 Azure Active Directory Connect 간의 디렉터리 동기화 설치.

    -   Azure Active Directory Connect 도구를 사용하여 암호 동기화 구성.

-   다중 포리스트 환경의 경우:

    -   Azure Active Directory Connect 동기화를 설치하고, 다중 포리스트 시나리오에 대해 설정합니다. 암호 해시 동기화 및 비밀번호 쓰기 저장은 다중 포리스트를 지원합니다.  그러나 다른 쓰기 저장 시나리오는 지원되지 않습니다.

    -   온-프레미스 Active Directory 포리스트와 Microsoft Azure Active Directory Premium 디렉터리(Azure Active Directory) 간의 동기화 구성.

        > [!NOTE]
        > 사용자 지정 규칙 확장의 개발 및 구현은 범위에 속하지 않습니다.

-   대상이 페더레이션 ID일 때 단일 포리스트 환경의 경우: 필요에 따라 단일 사이트 내결함성 구성에서 Microsoft Azure Active Directory Premium으로 로컬 도메인을 인증하도록 AD FS(Active Directory Federation Services)를 설치 및 구성합니다.

    > [!NOTE]
    > 모든 다중 포리스트 구성의 경우, AD FS 배포는 범위에 속하지 않습니다.

-   배포한 경우 SSO(Single Sign-On) 기능 테스트.

### 활성화 단계 - Azure Active Directory Premium(Azure Active Directory Connect 및 AD FS(Active Directory Federation Services) 포함)

설정에 대한 지침을 제공 합니다.

-   라이선스를 포함한 사용자 프로비저닝.

-   Azure Active Directory Connect 디렉터리 동기화(비밀번호 쓰기 저장 및 암호 해시 동기화).

  - SSPR(셀프 서비스 암호 재설정)

  - Azure MFA(Multi-Factor Authentication).

  - [Azure Active Directory Marketplace](https://azure.microsoft.com/marketplace/active-directory/)에서 SaaS(Software as a Service) 응용 프로그램 하나와 SSO(Single Sign On)의 통합

  - 사용자 지정된 로그온 화면(로고, 텍스트 및 이미지 포함)

  - 셀프 서비스 및 동적 그룹(그룹)

  - Azure Active Directory 응용 프로그램 프록시

  - Azure Active Directory Connect Health

  - ID 보호

  - Privileged Identity Management

  - 관리자를 위한 사용량 및 보안 보고서.

  - 관리 알림 및 경고

### 활성화 단계 – Microsoft Intune
다음에 대한 지침을 제공합니다.

-   최종 사용자 라이선싱. 필요한 경우 Microsoft 클라우드 서비스 테넌트에 대한 볼륨 라이선스를 활성화하는 방법의 지원도 제공합니다.

-   온-프레미스 Active Directory 또는 클라우드 ID를 활용하여 Microsoft Intune에서 사용할 ID 구성.

-   Microsoft Intune 구독에 사용자 추가, IT 관리자 역할 정의 및 사용자와 장치 그룹 만들기.

-   관리 요구 사항에 따라 다음과 같이 MDM(모바일 장치 관리) 기관 구성.

    -   Microsoft Intune이 유일한 MDM 솔루션이거나 Office 365용 모바일 장치 관리와 함께 사용되는 경우 Microsoft Intune을 MDM 기관으로 설정합니다.

    -   System Center Configuration Manager의 기존 구현이 있고 Microsoft Intune으로 관리 기능을 확장하려는 경우 Configuration Manager를 MDM 기관으로 설정합니다.

        > [!NOTE]
        > 최종 사용자가 소유한 장치, 공유 장치 또는 키오스크 유형 장치에서만 MDM을 활용하려는 경우에는 MDM 기관을 설정할 필요가 없습니다.

-   모바일 장치 관리가 범위에 포함되는 경우 다음과 관련된 지침을 제공합니다.

    -   MDM 관리 정책의 유효성을 검사하는 데 사용할 테스트 그룹 구성.

    -   다음과 같은 MDM 관리 정책 및 서비스 구성.

        -   지원되는 각 플랫폼에 대해 웹 링크 또는 딥 링크를 통한 응용 프로그램 배포.

        -   조건부 액세스 정책.

        -   메일 프로필 배포.

        -   해당되는 경우 Microsoft Intune Exchange Connector 설정.

    -   Microsoft Intune 서비스로 지원되는 플랫폼 각각의 장치를 Microsoft Intune 또는 Configuration Manager에 등록

    -   하드웨어 및 소프트웨어 인벤토리 보고서 사용.

-   조직 내에 MAM(모바일 응용 프로그램 관리)이 있거나 기존 타사 MDM 솔루션을 MAM 정책으로 보완하려는 경우 제공되는 관련 지침은 다음과 같습니다.

    -   지원되는 각 플랫폼에 대한 MAM 정책 구성.

    -   관리되는 앱에 대한 조건부 액세스 정책 구성.

    -   위의 MAM 정책에서 적절한 사용자 그룹을 대상으로 지정.

    -   관리되는 응용 프로그램 사용 현황 보고서 사용.

-   PC 관리가 범위에 포함되는 경우 다음과 관련된 지침을 제공합니다.

    -   필요한 경우 Intune 클라이언트 소프트웨어 설치

    -   Intune에서 사용할 수 있는 소프트웨어 및 하드웨어 보고서 사용.

**더 자세한 내용을 원하세요?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO1-->


