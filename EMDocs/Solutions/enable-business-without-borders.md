---
title: "경계 없는 비즈니스 지원"
description: "이 문서에서는 Enterprise Mobility + Security를 통해 클라우드 및 온-프레미스 자산에 걸쳐 작동하고 Azure Active Directory 내의 도구를 활용하여 사용자의 생산성을 유지하는 단일 ID를 제공할 수 있는 방법을 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 38e9802b-d8c0-4f5c-b89d-8ce1e04f7387
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 8f79e391813c7a15e522f07ff27a2f6abd8536cc
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="enable-business-without-borders"></a>경계 없는 비즈니스 지원
ID는 있으면 좋은 것이 아니라 효율적인 작업의 핵심입니다. 조직에서는 모든 장치 및 모든 위치에서 조직의 모든 데이터 및 응용 프로그램에 액세스할 수 있는 직원의 역량을 강화해야 합니다. 사용자는 서로 협력하고 파트너와 공동 작업을 수행해야 하며 고객과 연결해야 합니다. 이들이 사용하는 도구는 더 이상 보호되고 제어되는 환경에 있는 것이 아니라 공용 클라우드에서 찾을 수 있습니다.

이 새로운 세계에는 기존 도구로 완화할 수 없는 문제 및 고급 위협이 도사립니다. 새로운 경계가 사용자일 때는 네트워크만 보호하는 것은 소용 없습니다. 이 환경에서 보호되고 생산성을 유지하는 열쇠는 강력한 ID 솔루션입니다.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?
EMS(Enterprise Mobility + Security)는 ID, 장치, 앱, 데이터 등의 4단계 보호 기능으로 장치뿐 아니라 그 이상에서 기업 데이터를 기본적으로 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS는 모바일 우선, 클라우드 우선 세계의 핵심 과제 중 하나인, 클라우드 및 온-프레미스 자산에 걸쳐 작동하고 사용자의 생산성을 유지하는 단일 ID를 제공할 수 있는 방법을 해결하도록 도와줍니다.

### <a name="access-to-single-sign-on-applications"></a>Single Sign-On 응용 프로그램 액세스
ID 페더레이션과 Single Sign-On을 사용하는 경우 사용자는 단일 로그인 자격 증명 및 암호 집합을 사용할 수 있으므로 IT 부서에서 사용자 ID를 보다 효율적으로 관리할 수 있습니다.
### <a name="multi-factor-authentication"></a>다단계 인증
또한 사용자가 새 장치를 회사로 가져올 수 있으며, 이 경우 IT 부서에서는 네트워크에 연결된 장치가 적절한 자격 증명을 가진 개인이 소유하고 제어하는지에 대한 유효성을 검사할 수 있습니다. MFA(다단계 인증)는 보호 계층을 제공하는 데 도움이 됩니다.
### <a name="self-service-group-management"></a>셀프 서비스 그룹 관리
사용자가 암호를 잊어버린 경우 고유한 암호를 다시 설정할 수 있으므로 IT 부서의 부담이 줄어들며 신속한 문제 해결을 통해 사용자의 효율성이 증가합니다.
### <a name="cross-organization-collaboration"></a>조직 간 공동 작업
기업 간 공동 작업은 파트너와의 협력을 주요 요구 사항으로 고려하는 97%의 Microsoft 고객에게 중요한 요소입니다. Azure Active Directory B2B 공동 작업은 파트너가 자체 관리 ID를 사용하여 회사 앱 및 데이터에 선택적으로 액세스하도록 지원함으로써 회사 간의 관계를 지원합니다.

## <a name="recommended-solution"></a>권장 솔루션
[Azure Active Directory B2B 공동 작업](https://azure.microsoft.com/documentation/articles/active-directory-b2b-what-is-azure-ad-b2b/)은 조직이 기존 도구에 대한 기존 투자를 바탕으로 안전하고 생산적인 방식으로 어디에서든 필요한 모든 것에 액세스할 수 있도록 하는 권장 솔루션입니다.
- 파트너 조직 및 공동 작업자에게 조직의 데이터 및 응용 프로그램에 대한 액세스를 제공하는 IT 전문가
- 조직을 "대신"하거나 조직의 담당자 또는 직원 역할을 하는 파트너 사용자
- 액세스 검토, 전자 메일 확인, 허용 목록, 거부 목록 등이 호스트 응용 프로그램 및 리소스에 대한 액세스를 관리합니다.
- 파트너 사용자는 검색 가능하며 정책에 따라 자신의 조직에서 다른 사용자를 볼 수 있습니다.

### <a name="how-azure-ad-b2b-collaboration-works"></a>Azure AD B2B 공동 작업의 작동 원리

Azure AD B2B 공동 작업은 협력할 파트너의 메일 주소와 사용할 개별 앱을 활용하는 초대 및 사용 모델을 기반으로 합니다.

1. 관리자가 Azure 포털에 로그인하여 파트너의 사용자 정보가 포함된 CSV 파일을 가져와 파트너 사용자를 초대합니다.
2. Azure 포털에서 파트너에게 전자 메일을 보냅니다.
3. 파트너가 Azure 포털에서 자신이 받은 전자 메일의 링크를 클릭합니다. 파트너 사용자가 이미 Azure AD에 있는 경우 회사 자격 증명을 입력하라는 메시지가 나타나지만, 그렇지 않은 경우에는 Azure AD B2B 공동 작업 사용자로 등록해야 합니다.
4. 파트너 사용자가 공동 작업을 위해 초대된 응용 프로그램으로 자동으로 리디렉션됩니다.

![Azure AD B2B를 통해 파트너 사용자가 공동 작업을 위해 초대되는 프로세스를 보여 주는 그래픽](./media/enable-business-without-borders/enable-business-without-borders-fig1.png)

## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
다음 단계에서는 앞에서 설명한 각 Azure AD B2B 공동 작업을 구현하는 방법을 설명합니다. 각 링크는 조직에서 구현할 여러 지침/단계 집합이 포함된 다양한 문서 집합을 나타냅니다.
- [Azure AD B2B 공동 작업을 사용하는 방법](https://azure.microsoft.com/documentation/articles/active-directory-b2b-detailed-walkthrough/)에 대해 알아봅니다.
- [CSV 파일을 사용하여 파트너 사용자 정보를 지정하는 방법](https://azure.microsoft.com/en-us/documentation/articles/active-directory-b2b-references-csv-file-format/)에 대해 알아봅니다.
