---
title: "3계층 보호 사이트 배포 | Microsoft Docs"
description: "다양한 정보 보호 수준에 맞게 SharePoint Online 팀 사이트를 만들고 구성합니다."
services: active-directory
keywords: Office 365, Windows 10, Enterprise Mobility + Security, Microsoft 365 Enterprise
documentationcenter: 
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: 
ms.prod: microsoft-365-enterprise
ms.service: 
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: josephd
ms.openlocfilehash: 6d19a8b2fa39806e2a03ca8e3eb9ffae15605cc4
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="deploy-sites-for-three-tiers-of-protection"></a>3계층 보호 사이트 배포

## <a name="introduction"></a>소개

이 문서의 단계를 사용하여 초기, 중요 및 극비 SharePoint Online 팀 사이트를 디자인하고 배포합니다. 이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](secure-sharepoint-online-sites-and-files.md)를 참조하세요.

## <a name="baseline-sharepoint-online-team-sites"></a>초기 SharePoint Online 팀 사이트
초기 보호에는 공용 및 개인 팀 사이트가 모두 포함됩니다. 공용 팀 사이트는 조직의 모든 사용자가 검색하고 액세스할 수 있습니다. 개인 사이트는 팀 사이트와 연결된 Office 365 그룹의 구성원만 검색하고 액세스할 수 있습니다. 이러한 유형의 팀 사이트 모두에서는 구성원이 다른 사용자와 사이트를 공유할 수 있습니다.

### <a name="public"></a>Public
공용 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.

1. SharePoint Online 팀 사이트(SharePoint Online 관리자)를 관리하는 데에도 사용할 계정으로 **Office 365 포털**에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.
2. 타일 목록에서 **SharePoint**를 클릭합니다.
3. 브라우저의 새 **SharePoint** 탭에서 + **사이트 만들기**를 클릭합니다.
4. **사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.
5. **사이트 이름**에서 공용 팀 사이트의 이름을 입력합니다. 
6. **팀 사이트 설명**에서 사이트의 목적에 대한 설명을 입력합니다.
7. **개인 정보 설정**에서 **Public – anyone in the organization can access this site(공용 - 조직의 모든 사용자가 이 사이트에 액세스할 수 있음)**을 선택하고 **다음**을 클릭합니다.
8. **Who do you want to add?(누구를 추가하시겠습니까?)** 창에서 **마침**을 클릭합니다.

결과적으로 구성은 다음과 같습니다.

 ![공용 초기 SharePoint](./media/deploy-sites-for-three-tiers-of-protection/pub_site.png)

### <a name="private"></a>개인
개인 액세스 및 권한이 있는 초기 SharePoint Online 팀 사이트를 만들려면 다음을 수행합니다.

1. SharePoint Online 팀 사이트(SharePoint Online 관리자)를 관리하는 데에도 사용할 계정으로 **Office 365 포털**에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.
2. 타일 목록에서 **SharePoint**를 클릭합니다.
3. 브라우저의 새 **SharePoint** 탭에서 + **사이트 만들기**를 클릭합니다.
4. **사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.
5. **사이트 이름**에서 개인 팀 사이트의 이름을 입력합니다. 
6. **팀 사이트 설명**에서 사이트의 목적에 대한 설명을 입력합니다.
7. **개인 정보 설정**에서 **Private – only members can access this site(개인 - 구성원만 이 사이트에 액세스할 수 있음)**를 선택하고 **다음**을 클릭합니다.
8. **누구를 추가하시겠습니까?** 창의 **구성원 추가**에서 이 개인 팀 사이트에 액세스할 수 있는 사용자 계정의 이름을 입력합니다.
9. 초기 구성원 집합을 사이트에 추가했으면 **마침**을 클릭합니다.

결과적으로 구성은 다음과 같습니다.

 ![개인 초기 SharePoint](./media/deploy-sites-for-three-tiers-of-protection/priv_site.png)

## <a name="sensitive-sharepoint-online-team-sites"></a>중요 SharePoint Online 팀 사이트
중요 SharePoint Online 팀 사이트는 격리된 팀 사이트이며, 팀 사이트와 연결된 Office 365 그룹의 구성원 자격 대신 SharePoint 그룹의 구성원 자격을 통해 권한이 제어됩니다.

격리된 팀 사이트를 만들려면 다음 두 가지 주요 단계를 수행합니다.

### <a name="step-1-design-your-isolated-site"></a>1단계: 고립된 사이트 디자인
격리된 팀 사이트를 디자인하려면 다음을 결정해야 합니다.

* SharePoint 그룹 및 권한 수준
* SharePoint 그룹의 구성원이 될 액세스 그룹 집합 -
 권장되는 액세스 그룹 집합은 사이트 구성원, 사이트 뷰어 및 사이트 관리자에 대해 하나씩 구성된 액세스 그룹 집합입니다.
* 액세스 그룹 내에서 중첩된 그룹을 사용할지 여부

예를 들어 권장되는 그룹 구조와 권한 수준은 다음과 같습니다.

|**SharePoint 그룹**|**권한 수준**|**액세스 그룹(예제)**|
|:-----|:-----|:-----|
|[사이트 이름] 구성원|편집|[사이트 이름] 구성원|
|[사이트 이름] 방문자|읽기|[사이트 이름] 뷰어|
|[사이트 이름] 소유자|모든 권한|[사이트 이름] 관리자|

SharePoint 그룹 및 권한 수준은 기본적으로 팀 사이트에 대해 만들어집니다. 액세스 그룹의 이름을 결정해야 합니다.

디자인 프로세스에 대한 자세한 내용은 [격리된 SharePoint Online 팀 사이트 디자인](https://technet.microsoft.com/library/mt784687.aspx)을 참조하세요.

### <a name="step-2-deploy-your-isolated-site"></a>2단계: 격리된 사이트 배포
격리된 사이트를 배포하려면 먼저 다음을 수행해야 합니다.

* 각 액세스 그룹에 추가할 사용자 계정 및 그룹을 결정합니다.
* 액세스 그룹을 만들고 사용자 및 그룹 구성원을 추가합니다.

자세한 단계는 [격리된 SharePoint Online 팀 사이트 배포](https://technet.microsoft.com/library/mt784693.aspx)의 **1단계**를 참조하세요.

그리고 나서 다음 단계를 사용하여 SharePoint Online 팀 사이트를 만듭니다.

1. SharePoint Online 팀 사이트(SharePoint Online 관리자)를 관리하는 데에도 사용할 계정으로 **Office 365 포털**에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.
2. 타일 목록에서 **SharePoint**를 클릭합니다.
3. 브라우저의 새 **SharePoint 탭**에서 + **사이트 만들기**를 클릭합니다.
4. **사이트 만들기** 페이지에서 **팀 사이트**를 클릭합니다.
5. **사이트 이름**에서 개인 팀 사이트의 이름을 입력합니다.
6. **팀 사이트** 설명에서 선택적 설명을 입력합니다.
7. **개인 정보 설정**에서 **Private – only members can access this site(개인 - 구성원만 이 사이트에 액세스할 수 있음)**를 선택하고 **다음**을 클릭합니다.
8. **Who do you want to add?(누구를 추가하시겠습니까?)** 창에서 **마침**을 클릭합니다.

그리고 나서 새 SharePoint Online 팀 사이트에서 다음 단계를 사용하여 권한을 구성합니다.

1. IT 관리자 또는 사이트에 대한 액세스 요청에 응답하고 처리할 책임이 있는 다른 사용자(_belindan@contoso.com_ - UPN의 한 가지 예)의 UPN(사용자 계정 이름)을 결정합니다. 해당 UPN을 아래에 작성합니다.
2. 도구 모음에서 설정 아이콘을 클릭한 다음 **사이트 권한**을 클릭합니다.
3. **사이트 권한** 창에서 **고급 권한 설정**을 클릭합니다.
4. 브라우저의 새 **권한** 탭에서 **액세스 요청 설정**을 클릭합니다.
5. **액세스 요청 설정** 대화 상자에서 다음을 수행합니다.
  1. **구성원이 사이트와 개별 파일 및 폴더를 공유할 수 있도록 허용합니다.** 및 **구성원이 다른 사용자들을 사이트 구성원 그룹에 초대할 수 있도록 허용합니다.** 확인란의 선택을 취소합니다.
  2. **모든 액세스 요청 보내기**의 1단계에서 IT 관리자의 UPN을 입력합니다.
  3. **확인**을 클릭합니다.
6. 브라우저의 **권한** 탭에서 목록의 **[사이트 이름] 구성원**을 클릭합니다.
7. **사용자 및 그룹**에서 **새로 만들기**를 클릭합니다. **공유** 대화 상자에서 이 사이트에 대한 사이트 구성원 액세스 그룹 이름을 입력하고, 이 이름을 선택한 다음, **공유**를 클릭합니다.
8. 브라우저에서 [뒤로] 단추를 클릭하고 목록에서 **[사이트 이름] 소유자**를 클릭합니다.
9. **사용자 및 그룹**에서 **새로 만들기**를 클릭합니다. **공유** 대화 상자에서 이 사이트에 대한 사이트 관리자 액세스 그룹 이름을 입력하고, 이 이름을 선택한 다음, **공유**를 클릭합니다.
10. 브라우저에서 [뒤로] 단추를 클릭하고 목록에서 **[사이트 이름] 방문자**를 클릭합니다.
11. **사용자 및 그룹**에서 **새로 만들기**를 클릭합니다. **공유** 대화 상자에서 이 사이트에 대한 사이트 뷰어 액세스 그룹 이름을 입력하고, 이 이름을 선택한 다음, **공유**를 클릭합니다.
12. 브라우저의 **권한** 탭을 닫습니다.

이러한 권한 설정의 결과는 다음과 같습니다.

* **[사이트 이름] 소유자** SharePoint 그룹에는 모든 구성원이 **모든 권한** 권한 수준을 갖는 사이트 관리자 액세스 그룹이 포함되어 있습니다.
* **[사이트 이름] 구성원** SharePoint 그룹에는 모든 구성원이 **편집** 권한 수준을 갖는 사이트 구성원 액세스 그룹이 포함되어 있습니다.
* **[사이트 이름] 방문자** SharePoint 그룹에는 모든 구성원이 **읽기** 권한 수준을 갖는 사이트 뷰어 액세스 그룹이 포함되어 있습니다.
* 구성원이 다른 구성원을 초대하는 기능은 사용할 수 없습니다. 
* 구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 있습니다. 

결과적으로 구성은 다음과 같습니다.

 ![중요 보호](./media/deploy-sites-for-three-tiers-of-protection/sens_site.png)

사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다.

## <a name="highly-confidential-sharepoint-online-team-sites"></a>극비 SharePoint Online 팀 사이트
극비 SharePoint Online 팀 사이트는 격리된 팀 사이트이며, 팀 사이트와 연결된 Office 365 그룹의 구성원 자격 대신 SharePoint 그룹의 구성원 자격을 통해 권한이 제어됩니다.

매우 중요한 기밀에 속하는 정보와 공동 작업을 위해 격리된 팀 사이트를 만들려면 다음 두 가지 주요 단계가 있습니다.

### <a name="step-1-design-your-isolated-site"></a>1단계: 고립된 사이트 디자인
격리된 팀 사이트를 디자인하려면 다음을 결정해야 합니다.

* SharePoint 그룹 및 권한 수준
* SharePoint 그룹의 구성원이 될 액세스 그룹 집합 -
 권장되는 액세스 그룹 집합은 사이트 구성원, 사이트 뷰어 및 사이트 관리자에 대해 하나씩 구성된 액세스 그룹 집합입니다.
* 액세스 그룹 내에서 중첩된 그룹을 사용할지 여부

예를 들어 권장되는 그룹 구조와 권한 수준은 다음과 같습니다.
 
|**SharePoint 그룹**|**권한 수준**|**액세스 그룹(예제)**|
|:-----|:-----|:-----|
|[사이트 이름] 구성원|편집|[사이트 이름] 구성원|
|[사이트 이름] 방문자|읽기|[사이트 이름] 뷰어|
|[사이트 이름] 소유자|모든 권한|[사이트 이름] 관리자|

SharePoint 그룹 및 권한 수준은 기본적으로 팀 사이트에 대해 만들어집니다. 액세스 그룹의 이름을 결정해야 합니다.

디자인 프로세스에 대한 자세한 내용은 [격리된 SharePoint Online 팀 사이트 디자인](https://technet.microsoft.com/library/mt784687.aspx)을 참조하세요.

### <a name="step-2-deploy-your-isolated-site"></a>2단계: 격리된 사이트 배포
격리된 사이트를 배포하려면 먼저 다음을 수행해야 합니다.

* 각 액세스 그룹의 사용자 및 그룹 구성원을 확인합니다.
* 액세스 그룹을 만들고 사용자 및 그룹 구성원을 추가합니다.
* 액세스 그룹을 사용하는 격리된 팀 사이트를 만듭니다.

자세한 단계는 [격리된 SharePoint Online 팀 사이트 배포](https://technet.microsoft.com/library/mt784693.aspx)를 참조하세요.

권한 설정의 결과는 다음과 같습니다.

* **[사이트 이름] 소유자** SharePoint 그룹에는 모든 구성원이 **모든 권한** 권한 수준을 갖는 사이트 관리자 액세스 그룹이 포함되어 있습니다.
* **[사이트 이름] 구성원** SharePoint 그룹에는 모든 구성원이 **편집** 권한 수준을 갖는 사이트 구성원 액세스 그룹이 포함되어 있습니다.
* **[사이트 이름] 방문자** SharePoint 그룹에는 모든 구성원이 **읽기** 권한 수준을 갖는 사이트 뷰어 액세스 그룹이 포함되어 있습니다.
* 구성원이 다른 구성원을 초대하는 기능은 사용할 수 없습니다. 
* 구성원이 아닌 사용자가 액세스를 요청하는 기능은 사용할 수 없습니다. 

결과적으로 구성은 다음과 같습니다.

 ![극비 보호](./media/deploy-sites-for-three-tiers-of-protection/hc_site.png)

사이트 구성원은 이제 액세스 그룹 중 하나의 그룹 구성원 자격을 통해 사이트의 리소스에서 안전하게 공동 작업할 수 있습니다. 

자세한 내용은 [Office 365 레이블 및 DLP(데이터 손실 방지)를 사용하여 파일 보호](protect-files-with-o365-labels-dlp.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[정치적 캠페인, 비영리 조직, 및 기타 기밀 조직에 대 한 Microsoft 보안 지침](https://technet.microsoft.com/library/mt493213.aspx)

[SharePoint Online 사이트 및 파일 보호](secure-sharepoint-online-sites-and-files.md)

[개발/테스트 환경의 SharePoint Online 사이트 보호](secure-sharepoint-online-sites-dev-test.md)

[클라우드 채택 및 하이브리드 솔루션](https://technet.microsoft.com/library/dn262744.aspx)






