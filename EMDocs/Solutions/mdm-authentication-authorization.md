---
title: "인증 및 권한 부여"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 31b98333-5a3d-49ba-a25e-66447df68035
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: b1b40aa8b5044b90ab966b2ec050b39e392c1ffa


---

# 인증 및 권한 부여

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

회사 데이터를 제대로 보호하려면 먼저 사용자가 누구인지 식별한 다음 요청하는 리소스에 액세스할 수 있는 권한이 부여되었는지 확인할 수 있습니다. 온-프레미스 Active Directory 서비스가 이미 있는 조직에서는 이 서비스를 통해 모바일 사용자를 인증하고 권한을 부여합니다. 모든 Microsoft 모바일 장치 관리 솔루션은 기존 Active Directory 인프라를 사용하여 이 작업을 수행합니다. 

인증 및 권한 부여를 위해, 디렉터리 서비스의 위치도 결정해야 합니다. 대부분의 조직에서는 온-프레미스 Active Directory 서비스를 보유하게 되지만 일부 조직에서는 온-프레미스 디렉터리 서비스를 [Azure AD](http://azure.microsoft.com/documentation/articles/active-directory-whatis/)와 같은 클라우드 기반 디렉터리 서비스로 확장하는 것을 고려할 수 있습니다. 

ConfigMgr에서는 Active Directory 또는 Azure Active Directory 계정을 사용하여 Windows 10을 실행하는 장치에서 암호, 스마트 카드 또는 가상 스마트 카드를 대신하는 대체 로그인 방법인 [Microsoft Passport for Work](https://technet.microsoft.com/library/mt488797.aspx)과 통합할 수 있습니다. 하이브리드 시나리오의 경우 다음과 같이 Azure AD 기능을 활용하는 대신 두 디렉터리를 통합하는 것도 좋은 방법입니다.

- **셀프 서비스 그룹 관리**: 다른 사용자가 요청을 승인하고 그룹 구성원 자격을 유지할 수 있도록 하기 위해 그룹을 만들고, 다른 그룹에 대한 액세스를 요청하고, 그룹 소유권을 위임할 수 있습니다.
- **99.9% 엔터프라이즈 SLA**: Microsoft는 Azure Active Directory Premium 서비스에 대해 99.9% 이상의 가용성을  보장합니다.
- **다시 쓰기가 가능한 암호 재설정**: 셀프 서비스 암호 재설정은 온-프레미스 디렉터리에 다시 쓸 수 있습니다.

[Azure Active Directory](https://msdn.microsoft.com/library/azure/dn532272.aspx)에서 다양한 옵션 및 기능에 대해 자세히 읽어보세요.
모바일 장치 관리 솔루션을 계획하는 시기 등과 마찬가지로 두 가지 유형의 인증(MFA 또는 다단계 인증)을 요구할지 여부도 고려해야 합니다. [Intune은 디렉터리 서비스를 MFA(다단계 인증)에 통합](https://technet.microsoft.com/library/dn889751.aspx)하여 인증 프로세스에 대한 보안 계층을 추가합니다. 

조직에 AD FS(Active Directory Federation Services)가 구성된 Active Directory 도메인이 포함된 온-프레미스 IT 인프라가 있는 경우 페더레이션 서버에서 MFA를 구성한 다음 Intune에서 MFA 사용하도록 설정할 수 있습니다. 페더레이션 서버에서 MFA를 구성하지만 Intune에서 등록하는 데 MFA를 사용하지 않을 경우 사용자는 장치에서 회사 리소스에 액세스할 때마다 MFA를 사용해야 합니다. 

Azure AD MFA를 사용하여 사용자가 회사 리소스에 액세스할 때마다 MFA를 요구할 수도 있으며 사용자 기준으로 설정할 수 있습니다. Azure AD MFA는 온-프레미스 IT 인프라를 요구하지 않는 클라우드 서비스입니다.

아래 표를 참조하면 조직의 인증 및 권한 부여 요구 사항에 가장 잘 맞는 MDM 옵션을 선택하는 데 도움이 될 것입니다.

## Intune(독립 실행형)

**장점**

- 인증을 위해 Active Directory와 같은 온-프레미스 디렉터리 서비스를 사용할 수 있음
- 인증을 위해 Azure AD와 같은 클라우드 기반 디렉터리 서비스를 사용할 수 있음
- 다단계 인증과 통합할 수 있음

**단점**

- Intune 구독 구입 시 Azure AD 클라우드 서비스가 포함되지 않음

## Office 365용 MDM

**장점**

- 인증을 위해 Active Directory와 같은 온-프레미스 디렉터리를 사용할 수 있음
- 인증을 위해 Azure AD와 같은 클라우드 기반 디렉터리를 사용할 수 있음
- 다단계 인증과 통합할 수 있음
- 역할 기반 액세스 제어(RBAC) 사용 권한 모델을 통해 호환성 센터를 활용할 수 있음

**단점**

- Office 365 구독 구입 시 Azure AD 클라우드 서비스가 포함되지 않음

## 하이브리드(ConfigMgr와 Intune)

**장점**

- 인증을 위해 Active Directory와 같은 온-프레미스 디렉터리를 사용할 수 있음
- 인증을 위해 Azure AD와 같은 클라우드 기반 디렉터리를 사용할 수 있음

**단점**

- Intune 구독 구입 시 Azure AD 클라우드 서비스가 포함되지 않음

## Enterprise Mobility + Security

**장점**

- Azure AD Premium을 사용하여 액세스 제어 제공
- Azure AD Premium 라이선스가 EMS에 이미 포함되어 있음
- 온-프레미스 디렉터리 서비스가 필요하지 않음
- 온-프레미스 Active Directory 서비스와 동기화할 수 있음
- 기본적으로 MFA를 EMS에서 사용할 수 있음

**단점**

- 클라우드 기반 솔루션을 채택하지 않는 고객은 사용할 수 없음




<!--HONumber=Oct16_HO1-->


