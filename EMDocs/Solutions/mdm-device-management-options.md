---
title: "장치 관리 옵션"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a25f7407-92a0-4588-b5f7-a7bad9cdd070
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 93e88e3b36f2f247978981d2af381d30c6d79f5b


---

# 장치 관리 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

Intune 및 ConfigMgr를 통한 모바일 장치 관리 작업은 관리 정책을 중심으로 진행됩니다. 정책은 모바일 장치에 대한 설정 그룹을 정의하며, 템플릿에서 생성하거나 특정 장치, 사용자 또는 그룹에 대해 사용자 지정할 수 있습니다. 최상의 관리 방법은 관리 솔루션에 모바일 장치를 등록하기 전에 관리 정책을 만드는 것입니다. 이렇게 하면 장치가 IT 전략에 정의된 정책 및 프로세스에 따라 즉시 관리됩니다. 이러한 솔루션 둘 다에서 다음 정책 유형의 구성할 수 있습니다.

- 구성 정책: 구성 정책은 등록된 각 모바일 장치에 대한 일반적인 조직 설정을 정의하는 데 사용됩니다. 여기에는 장치 암호, 응용 프로그램, 클라우드 정책 및 암호화 설정이 포함될 수 있지만 다른 관리 영역에 대한 **[여러 다른 장치 설정](https://technet.microsoft.com/library/dn743712.aspx)**도 포함될 수 있습니다. 또한 구성 정책은 장치 등록 프로필을 사용하여 다른 유형의 모바일 장치 운영 체제마다 다르게 적용되고 구성됩니다.

>[!TIP]
>유형이 다른 장치, 사용자 또는 그룹에 대해 다른 정책을 만들 경우 동일한 장치에 서로 충돌하는 정책 설정이 적용되기 쉽습니다. **[충돌하는 정책 설정이 적용되는 방식](https://technet.microsoft.com/library/dn743712.aspx)**을 이해해야 합니다.

- **규정 준수 정책:** 규정 준수 정책은 모바일 장치가 회사 리소스 또는 서비스에 액세스(또는 액세스 거부)하기 위한 조직의 요구 사항을 적용합니다. 여기에는 장치 암호 및 암호화 설정과 모바일 장치의 루팅("무단 해제") 여부를 확인하는 작업도 포함될 수 있습니다. 구성 정책의 경우와 마찬가지로 Intune 및 [ConfigMgr](https://technet.microsoft.com/library/dn376523.aspx) 규정 준수 정책 옵션 또한 모바일 장치 운영 체제 유형에 따라 다릅니다. ConfigMgr에서 규정 준수 정책을 만드는 경우 증가하는 세분성을 다중 부분 프로세스의 일부로 구성할 수 있다는 점에 유의해야 합니다.

 1. [구성 항목](https://technet.microsoft.com/library/gg712331.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) 만들기
 2. [구성 기준](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) 만들기
 3. ConfigMgr 사용자 또는 장치 컬렉션에 [구성 기준 배포](https://technet.microsoft.com/library/hh219289.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)

- **조건부 액세스 정책:** 조건부 액세스 정책은 메일에 대한 액세스가 관리되는 방법을 정의하고 규정 준수 정책과 함께 또는 별도로 사용될 수 있습니다. 조건부 액세스 정책을 배포하려면 먼저 온-프레미스 Exchange Server 또는 Exchange Online 서비스에 대한 연결을 [Intune](/Intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) 또는 [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx)에서 구성해야 합니다. Office 365, SharePoint Online 서비스에 대해 조건부 액세스를 구성할 수도 있습니다.

1단계의 질문에 대한 답변은 모바일 장치 관리 솔루션에 장치를 등록하는 방법을 결정하는 데 도움이 됩니다. 아래 목록은 각 관리 시나리오의 장단점을 이해하는 데 도움이 됩니다.

## Intune(독립 실행형)

**장점**

- 현재는 장치 플랫폼에 의해 분리되는 사용자 및 장치를 위한 간소화된 정책 제어를 지원합니다.
- Android, iOS, [Windows 10](https://technet.microsoft.com/library/mt147406.aspx), Windows 8.x, Windows Phone 플랫폼뿐 아니라 Exchange ActiveSync도 지원합니다.
- 어느 위치에서도 액세스할 수 있는 간단한 웹 기반 관리 콘솔 제공
- 그룹 기반 정책을 지원하여 많은 수의 다양 모바일 장치 유형을 보다 쉽게 관리
- 장치 루팅 및 무단 해제 감지를 비롯한 고급 모바일 장치 규정 준수 기능 지원
- 모든 모바일 장치에 대한 선택적 초기화 또는 전체 공장 기본 설정 허용
- 내부 및 타사 모바일 응용 프로그램의 관리되는 안전한 배포를 허용하는 사용자 지정 가능한 회사 포털 포함
- 모바일 장치에 인증서 배포
- 조직이 모바일 응용 프로그램에서 잘라내기/복사/붙여넣기 기능을 방지하도록 허용
- 관리되는 브라우저의 사용 적용 지원
- 장치 IMEI 번호를 사용하여 기업 소유의 장치를 식별하고 해당 장치에 태그를 지정하여 개인 소유 장치와 정책 할당을 분리합니다.

**단점**

- Intune 서비스에 장치를 등록하는 사용자 계정에 대한 라이선스 요구 사항 및 비용 증가

## Office 365용 MDM

**장점**

- Office 365 테넌트 내의 통합 웹 기반 관리 및 관리 콘솔
- 그룹 기반 정책을 지원하여 많은 수의 다양 모바일 장치 유형을 보다 쉽게 관리
- 장치 루팅 및 무단 해제 감지를 비롯한 고급 모바일 장치 규정 준수 기능 지원
- 모든 모바일 장치에 대한 선택적 초기화 또는 전체 공장 기본 설정 허용

**단점**

- 다음을 포함하는 고급 모바일 장치 관리 기능이 지원되지 않음
 - 인증서, 메일, VPN, 무선 프로필 프로비전 및 관리
 - 장치 컬렉션 등록 및 관리
- 다음을 포함하는 일부 모바일 응용 프로그램 관리 기능이 지원되지 않음
 - 모바일 장치에 기간 업무 애플리케이션 배포
 - Office 모바일 응용 프로그램에 대한 보안 데이터 액세스를 사용하도록 설정
 - 회사 데이터를 모바일 장치의 기간 업무 앱으로 안전하게 확장
 - 관리되는 브라우저 또는 기타 콘텐츠 보기 응용 프로그램

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점 및 다음 장점
 - 유연한 역할 기반 관리 및 스크립팅(PowerShell을 통한)을 포함하여 회사 자산을 관리하기 위한 단일 보기 창 제공

**단점**

- Intune을 온-프레미스 ConfigMgr 인프라와 연결하기 위한 추가적인 구성 필요
- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성 필요
- Android 장치용 VPN 및 메일 프로필이 현재 지원되지 않음
- 관리되는 브라우저 지원이 현재 지원되지 않음



<!--HONumber=Oct16_HO1-->


