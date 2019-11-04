---
title: 첫 번째 관문에서 보호 | Microsoft 문서
description: Enterprise Mobility + Security에서 Microsoft Azure Active Directory Identity Protection 및 Azure Active Directory Privileged Identity Management 기능을 활용하여 ID를 보호함으로써 회사 리소스에 대한 액세스 보안을 유지하는 방법을 설명하는 시나리오입니다.
author: yuridio
ms.author: yurid
manager: barbkess
ms.date: 05/18/2017
ms.topic: conceptual
ms.prod: ''
ms.service: active-directory
ms.assetid: c9aeabcf-db9b-4a35-b1bc-61331c464165
ms.reviewer: v-craic
ms.suite: ems
ms.custom: microsoft-identity-manager
ms.openlocfilehash: 897e5643013fddd2fd99de3ccf3d56069022297c
ms.sourcegitcommit: fd344763857d03303006b9da4f6931ed320d27ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462570"
---
# <a name="protect-at-the-front-door"></a>첫 번째 관문에서 보호

과거에는 전형적인 보안 솔루션으로 회사를 충분히 보호할 수 있었습니다. 그렇지만 모바일 산업이 증가하면서 공격 가능 범위가 커지고, 클라우드로 전환하면서 다른 사용자, 디바이스, 앱 및 데이터와의 직원 상호 작용이 훨씬 더 복잡해졌습니다. 이제 회사를 진정으로 보호하기 위해서는 온-프레미스 및 클라우드에서 발생하는 모든 종류의 위협으로부터 보호하고, 이러한 위협을 감지하고 대처할 수 있는 전체적이고 혁신적인 보안 접근 방법을 적용해야 합니다.

데이터 위반 사례의 63% 이상에서 공격자는 약하거나 기본 설정 상태이거나 도난 당한 사용자 자격 증명을 통해 회사 네트워크에 액세스합니다.  Microsoft ID 기반 보안은 사용자 자격 증명에 중점을 두면서, 권한 있는 및 권한 없는 ID를 포함하는 모든 사용자 ID를 관리하고 보호하여 자격 증명이 도난 당했을 때 보호 기능을 보다 강력하게 강화합니다.


## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?

EMS(Enterprise Mobility + Security) 보안 접근 방식은 위험 기반의 [조건부 액세스](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/)를 통해 온-프레미스 및 클라우드의 모든 회사 리소스에 안전하게 액세스하기 위한 보호되는 단일 ID를 사용합니다. 이 접근 방식을 사용하여 IT 부서에서는 혁신적이고 수준 높은 위험 기반 조건부 액세스를 사용하여 첫 번째 관문에서 회사 리소스를 보호할 수 있습니다. EMS는 수천 개의 앱에 액세스하기 위한 보호되는 단일 ID를 제공하여 IT 부서에서 권한 있는 ID를 쉽게 관리하고 보호할 수 있도록 합니다.

## <a name="recommended-solution"></a>권장 솔루션

이 시나리오의 요구를 해결하기 위해 EMS는 [Azure AD ID 보호](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/) 및 [Azure AD Privileged Identity Management](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-configure/)를 사용합니다. 이러한 기술에 구현하여 조직은 다음을 수행할 수 있게 됩니다.

- Machine Learning 기반의 위협 요소 탐지 결과에 대한 통합된 보기를 통해 통찰력 얻기
- 권장 사항 수정
- 위험 심각도 계산 수행
- 위험 기반 조건부 액세스를 자동으로 수행하여 의심스러운 로그인 및 손상된 자격 증명 방지
- 필요할 때 요청 시, Just-In-Time 관리 액세스 적용
- 경고, 감사 보고서 및 액세스 검토 사용

다음 다이어그램에서는 이 시나리오와 관련된 기능과 리소스 보호를 위해 이러한 기능이 사용되는 방식을 요약해서 보여 줍니다.

![리소스 보호](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig1.png)

## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

다음 단계에 따라 Azure AD ID 보호 및 Azure AD Privileged Identity Management를 구현합니다.

- 1단계: Azure AD ID 보호를 사용하도록 설정
- 2단계: Azure AD ID 보호 구성
- 3단계: 리소스에 대한 액세스 모니터링
- 4단계: Azure AD Privileged Identity Management를 사용하도록 설정
- 5단계: Azure AD Privileged Identity Management 구성
- 6단계: Privileged Identity Management 작업


## <a name="how-to-protect-your-resources-at-the-front-door"></a>프런트 도어에서 리소스를 보호 하는 방법

조직마다 다른 인시던트 우선 순위 개념을 갖습니다. 한 LOB(기간 업무)에 중요한 인시던트가 다른 LOB에는 중요하지 않을 수도 있습니다. 이러한 이유로 먼저 Azure AD ID 보호에서 [위험 수준](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#detection-and-risk)을 분류하는 방식을 알아야 합니다. 이 위험 수준은 위험 이벤트의 심각도(높음, 중간 또는 낮음)를 나타내는 지표입니다. Azure AD ID 보호는 사용자의 ID가 손상될 가능성을 평가하고 [사용자 위험 수준](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#what-is-a-user-risk-level)이라는 자체 위험 수준을 할당합니다. Azure AD ID 보호는 [취약성](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-vulnerabilities/)을 파악하고 위험 수준을 할당합니다. 다양한 [위험 유형](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/)이 있으며 각 유형은 중요도에 따라 순위가 지정됩니다. 1~3단계에 따라 Azure AD ID 보호를 사용하여 리소스를 사용하도록 설정, 구현 및 모니터링하세요.

이 솔루션의 두 번째 단계(4-6단계)에서는 권한 있는 ID를 검색, 제한 및 모니터링하도록 Azure AD(Active Directory) Privileged Identity Management를 구현합니다. Azure를 사용하는 조직은 [Azure AD에서 역할을 할당](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/)할 수 있으며 Azure AD Privileged Identity Management에서 [이러한 역할 중 일부](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/)를 관리할 수 있습니다.

### <a name="step-1-enable-azure-ad-identity-protection"></a>1단계: Azure AD ID 보호를 사용하도록 설정

이 솔루션을 구현하기 전에 [Azure AD Premium 라이선스가](https://azure.microsoft.com/documentation/articles/active-directory-get-started-premium/)가 최종 사용자에게 할당되어 있는지 확인합니다. 페더레이션된 도메인을 사용하며 클라우드의 암호 변경이 온-프레미스에 다시 기록되도록 하려는 경우 [암호 쓰기 저장](https://azure.microsoft.com/documentation/articles/active-directory-passwords-getting-started/)을 사용하도록 설정해야 합니다. 이러한 요구 사항의 검토를 마친 후 Marketplace에서 설치하여 [Azure AD ID 보호를 사용하도록 설정](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-enable/)합니다. 이 설치가 끝나면 다음 그림에 나와 있는 것처럼 빈 상태일 수 있는 Azure AD ID 보호 대시보드에 액세스할 수 있습니다.

![Azure AD ID 보호](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig2.png)

### <a name="step-2-configure-azure-ad-identity-protection"></a>2단계: Azure AD ID 보호 구성

Azure AD ID 보호를 구현하려는 경우 먼저 다음 정책을 정의해야 합니다.

- [다단계 인증 등록 정책](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#multi-factor-authentication-registration-policy): IT 부서에서 사용자를 위해 MFA(다단계 인증)를 적용할 수 있습니다.
- [사용자 위험 정책](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#user-risk-security-policy): IT 부서에서 위험 수준에 따라 로그인 시 사용자를 차단하는 사용자 위험 보안 정책을 설정할 수 있습니다.
- [로그인 위험 정책](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#sign-in-risk-security-policy): IT 부서에서 특정 로그인에 대한 위험도를 평가하고 그 결과에 따라 미리 정의된 조건 및 규칙을 사용하여 완화 조치를 적용할 수 있습니다.

이러한 정책은 다음 그림과 같이 Azure AD ID 보호 대시보드의 **구성** 섹션에 있습니다.

![정책](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig3.png)

또한 보안 정책을 구성하는 것 경고를 받는 사용자를 사용자 지정할 수도 있습니다. 다음 그림과 같이 Azure AD ID 보호 대시보드의 설정 섹션에서 **경고** 옵션을 사용해야 합니다.

![경고](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig4.png)

이 구성에서 이러한 사용자는 사용자 위험 수준이 **높은**일 때만 경고를 받습니다.

### <a name="step-3-monitor-and-remediation"></a>3단계: 모니터 및 수정

지속적인 모니터링은 모든 보안 작업의 필수적인 부분입니다. Azure AD ID 보호의 [조사](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#investigation) 기능을 활용하여 IT 부서에서는 알림 및 수정 권장 지침을 포함하는 유용한 Machine Learning 기반 위협 요소 탐지 결과를 얻을 수 있습니다. Azure AD ID 보호 대시보드를 사용하여 현재 환경을 신속하게 평가하고 그 중요성에 따라 해결해야 하는 문제를 쉽게 식별할 수 있습니다. 또는 Azure AD ID 보호 대시보드의 조사 섹션 아래에 있는 다음 영역에서 조사 범위를 좁힐 수 있습니다.

![조사](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig5.png)

관리자가 각 영역의 조사에서 [사용자 위험](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-user-risk-events)을 완화하거나 [로그인 이벤트](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-sign-in-risk-events)를 완화하기 위한 작업을 수행할 수 있습니다. 예를 들어 [비정상적 위치로 이동 불가능](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/#impossible-travel-to-atypical-locations)과 같은 보안 이벤트(다음 화면의 두 번째 이벤트)를 식별하는 경우 암호를 강제로 재설정하도록 하는 것과 같이 이 위협을 [수정](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#remediating-user-risk-events)하기 위한 작업을 수행할 수 있습니다.

![위험 이벤트](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig6.png)

[Azure AD Premium 액세스 및 사용 현황 보고서](https://azure.microsoft.com/documentation/articles/active-directory-view-access-usage-reports/)를 활용하여 사용자의 동작 및 잠재적인 위협 요소에 대한 자세한 정보를 얻을 수 있습니다.

### <a name="step-4-enable-azure-ad-privileged-identity-management"></a>4단계: Azure AD Privileged Identity Management를 사용하도록 설정

Azure AD Privileged Identity Management에 액세스하려면 먼저 [Marketplace에서 설치](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-getting-started/)해야 합니다. Azure AD Privileged Identity Management 및 Azure MFA(Multi-Factor Authentication)는 함께 작동하여 IT 부서에서 보안 애플리케이션 및 서비스에 액세스할 수 있도록 지원합니다. Azure AD Privileged Identity Management를 설치한 후에는 MFA를 사용할 수 있는지 확인하게 위해 테스트가 수행됩니다. 계정을 확인하는 옵션을 클릭하면 자격 증명을 입력해야 하는 웹 페이지로 이동됩니다. 계정이 아직 MFA를 지원하지 않는 경우 다음 화면과 유사한 메시지가 나타납니다.

![로그온 화면](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig7.png)

**지금 설정**을 클릭하고 마법사를 따릅니다. 확인을 위해 휴대폰 또는 전화 번호를 입력해야 합니다. 이 마법사를 마치면 확인 완료 메시지가 나타납니다.

![확인](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig8.png)

### <a name="step-5-configure-azure-ad-privileged-identity-management"></a>5단계: Azure AD Privileged Identity Management 구성

초기 구성은 **조직 보호** 블레이드에 표시된 3개 단계로 진행되는 [보안 마법사](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-security-wizard/)를 사용하여 수행됩니다.

![보안 마법사](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig9.png)

첫 번째 단계에서는 Azure AD Privileged Identity Management에서 검색된 [권한 있는 역할](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/)을 검토합니다. 두 번째 단계는 영구 권한 있는 역할이 할당된 조직의 사용자 수를 줄여 보안 취약성을 직접적으로 최소화하기 위한 것입니다. 마지막 단계에서는 권한 있는 역할에 포함된 사용자에 대한 변경 내용을 검토할 수 있습니다.

이 프로세스 중에 다른 사용자에게 관리 역할을 부여한 경우 해당 사용자는 해당 역할에 대해 작업을 수행할 수 있게 됩니다. 즉, 해당 역할에 필요한 작업을 수행해야 하는 경우 [해당 역할을 활성화](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-activate-role/)할 수 있습니다.

### <a name="step-6-privileged-identity-management-operations"></a>6단계: Privileged Identity Management 작업

Azure AD Privileged Identity Management를 설치 및 구성했으므로 초기 평가를 수행하여 현재 역할 스키마 및 경고를 확인할 수 있습니다. **권한 ID 관리** 블레이드에서 **권한 있는 역할 관리**를 클릭하면 다음 그림과 유사한 대시보드가 표시됩니다.

![권한 있는 역할](https://github.com/MicrosoftDocs/EMDocs/blob/live/EMDocs/Solutions/media/protect-front-door/protect-front-door-fig10.png)

이 대시보드에서는 [보안 경고](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-configure-security-alerts/) 및 [액세스 검토](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-start-security-review/)와 같은 현재 활동을 볼 수 있습니다. 또한 이 대시보드에서 Azure AD Privileged Identity Management에 대한 하나 이상의 사용자 액세스 권한을 [추가](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/) 또는 [제거](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/#remove-another-users-access-rights-for-managing-pim)할 수 있습니다.
