---
title: "Office 365 레이블 및 DLP(데이터 손실 방지)를 사용하여 파일 보호 | Microsoft 문서 도구"
description: "다양한 정보 보호 수준을 통해 SharePoint Online 팀 사이트에 Office 365 레이블 및 DLP(데이터 손실 방지) 정책을 적용합니다."
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
ms.openlocfilehash: e9138c2c563c8081f075ffa3e65ecf917456c23c
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="protect-files-with-office-365-labels-and-data-loss-prevention"></a>Office 365 레이블 및 DLP(데이터 손실 방지)를 사용하여 파일 보호

## <a name="introduction"></a>소개
이 문서의 단계를 사용하여 초기, 중요 및 극비 SharePoint Online 팀 사이트에 대한 Office 365 레이블 및 DLP(데이터 손실 방지) 정책을 디자인하고 배포합니다. 이러한 3계층 보호에 대한 자세한 내용은 [SharePoint Online 사이트 및 파일 보호](secure-sharepoint-online-sites-and-files.md)를 참조하세요.

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a>SharePoint Online 사이트에 대한 Office 365 레이블
SharePoint Online 팀 사이트에 Office 365 레이블을 만들고 할당하는 경우 다음 세 가지 단계를 수행해야 합니다.

### <a name="phase-1-determine-the-office-365-label-names"></a>1단계: Office 365 레이블 이름 결정

이 단계에서는 SharePoint Online 팀 사이트에 적용되는 네 가지 정보 보호 수준에 대한 Office 365 레이블의 이름을 결정합니다. 다음 표에는 각 수준에 권장되는 이름이 나와 있습니다.
 
|**SharePoint Online 팀 사이트 보호 수준**|**레이블 이름**|
|:-----|:-----|
|초기 공용|내부 공용|
|초기 개인|개인|
|중요|중요|
|극비|극비|

### <a name="phase-2-create-the-office-365-labels"></a>2단계: Office 365 레이블 만들기
이 단계에서는 서로 다른 수준의 정보 보호를 위해 결정한 레이블을 만들어 게시합니다.

레이블을 만들려면 Office 365 관리 센터 또는 Microsoft PowerShell을 사용하면 됩니다.

**Office 365 관리 센터를 사용하여 Office 365 레이블 만들기**

1. 보안 관리자 또는 회사 관리자 역할이 있는 계정으로 **Office 365 포털**에 로그인합니다. 도움을 받으려면 [Office 365에 로그인하는 위치](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하세요.
2. **Microsoft Office 홈** 탭에서 **관리 타일**을 클릭합니다.
3. 브라우저의 새 **Office 관리 센터** 탭에서 **관리 센터 > 보안 및 준수**를 차례로 클릭합니다.
4. 브라우저의 새 **홈 - 보안 및 준수** 탭에서 **분류 > 레이블**을 차례로 클릭합니다.
5. **홈 > 레이블** 창에서 **레이블 만들기**를 클릭합니다.
6. **레이블** 창에서 레이블 이름을 입력하고 **다음**을 클릭합니다.
7. **레이블 설정** 창에서 **다음**을 클릭합니다.
8. **설정 검토** 창에서 **이 레이블 만들기**, **닫기**를 차례로 클릭합니다.
9. 레이블을 추가하려면 5-8단계를 반복합니다.

**PowerShell을 사용하여 Office 365 레이블 만들기**

1. [원격 PowerShell을 사용하여 Office 365 보안 및 준수 센터에 연결](http://go.microsoft.com/fwlink/?LinkID=799771&clcid=0x409)하고 보안 관리자 또는 회사 관리자 역할이 있는 계정의 자격 증명을 지정합니다.
2. 레이블 이름 목록을 작성한 다음 PowerShell 명령 프롬프트에서 다음 명령을 실행합니다.

```
$labelNames=@([list of label names, each enclosed in quotes and separated by commas])
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
```

그리고 나서 다음 단계를 사용하여 새 Office 365 레이블을 게시합니다.

1. [보안 및 준수 센터]의 **홈 > 레이블** 창에서 **레이블 게시**를 클릭합니다.
2. **게시할 레이블 선택** 창에서 **게시할 레이블 선택**을 클릭합니다.
3. **레이블 선택** 창에서 **추가**를 클릭하고 네 개의 레이블을 모두 선택합니다.
4. **완료**를 클릭합니다.
5. **게시할 레이블 선택 창**에서 **다음**을 클릭합니다.
6. **위치 선택** 창에서 **다음**을 클릭합니다.
7. **정책 이름 지정** 창의 **이름**에서 레이블 집합 이름을 입력하고 **다음**을 클릭합니다.
8. **설정 검토** 창에서 **레이블 게시**, **닫기**를 차례로 클릭합니다.

### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a>3단계: SharePoint Online 사이트에 Office 365 레이블 적용
다음 단계에 따라 Office 365 레이블을 SharePoint Online 팀 사이트의 문서 폴더에 적용합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 **SharePoint** 타일을 클릭합니다.
2. 브라우저의 새 **SharePoint** 탭에서 할당된 Office 365 레이블이 필요한 사이트를 클릭합니다.
3. 브라우저의 새 SharePoint 사이트 탭에서 **문서**를 클릭합니다.
4. 설정 아이콘을 클릭한 다음 **라이브러리 설정**을 클릭합니다.
5. **권한 및 관리** 아래에서 **Apply label to items in this library(이 라이브러리의 항목에 레이블 적용)**을 클릭합니다.
6. **설정 - 레이블 적용**에서 적절한 레이블을 선택하고 **저장**을 클릭합니다.
7. SharePoint Online 사이트의 탭을 닫습니다.
8. 위의 단계를 반복하여 추가 SharePoint Online 사이트에 Office 365 레이블을 할당합니다.

결과적으로 구성은 다음과 같습니다.

 ![초기 보호](./media/protect-files-with-o365-labels-dlp/site_labels.png)

### <a name="dlp-policies-for-your-sharepoint-online-sites"></a>SharePoint Online 사이트에 대한 DLP 정책
다음 단계를 사용하여 사용자가 조직 외부의 중요 SharePoint Online 팀 사이트에서 문서를 공유할 때 다른 사용자에게 알려주는 DLP 정책을 구성합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 **보안 및 준수 센터** 타일을 클릭합니다.
2. 브라우저의 새 **보안 및 준수** 탭에서 **데이터 손실 방지 > 정책**을 차례로 클릭합니다.
3. **데이터 손실 방지** 창에서 **+ 정책 만들기**를 클릭합니다.
4. **Start with a template or create a custom policy(템플릿으로 시작하거나 사용자 지정 정책 만들기)** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.
5. **정책 이름 지정** 창의 [이름]에서 중요 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.
6. **위치 선택** 창에서 **Let me choose specific locations(특정 위치 직접 선택)**를 선택하고 **다음**을 클릭합니다.
7. 위치 목록에서 **Exchange 전자 메일** 및 **OneDrive 계정** 위치를 사용하지 않도록 설정하고 **다음**을 클릭합니다.
8. **Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **편집**을 클릭합니다.
9. **Choose the types of content to protect(보호할 콘텐츠 형식 선택)** 창의 드롭다운 상자에서 **추가**, **레이블**을 차례로 클릭합니다.
10. **레이블** 창에서 **+ 추가**를 클릭하고, **중요** 레이블을 선택하고, **추가**를 클릭한 다음 **완료**를 클릭합니다.
11. **Choose the types of content to protect(보호할 콘텐츠 형식 선택)** 창에서 **저장**을 클릭합니다.
12. **Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음**을 클릭합니다.
13. **What do you want to do if we detect sensitive info?(중요 정보를 검색하는 경우 어떤 작업을 수행하시겠습니까?)** 창에서 **Customize the tip and email(팁 및 전자 메일 사용자 지정)**을 클릭합니다.
14. **Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)**를 클릭합니다.
15. 텍스트 상자에서 다음과 같이 입력하거나 붙여넣은 다음 **확인**을 클릭합니다.
 * 조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. **파일**, **문서 보호**, **암호 설정**을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.
 * 또는 조직 외부의 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.
16. **What do you want to do if we detect sensitive info?(중요 정보를 검색하는 경우 어떤 작업을 수행하시겠습니까?)** 창에서 **Block people from sharing and restrict access to shared content(공유된 콘텐츠 차단 및 액세스 제한)** 확인란의 선택을 취소하고 **다음**을 클릭합니다.
17. **Do you want to turn on the policy or test things out first?(먼저 정책을 사용하도록 설정하거나 테스트하시겠습니까?)** 창에서 **예**를 클릭하는 대로 사용하도록 설정하고 **다음**을 클릭합니다.
18. **설정 검토** 창에서 **만들기**, **닫기**를 차례로 클릭합니다.

결과적으로 중요 SharePoint Online 팀 사이트에 대한 구성은 다음과 같습니다.

 ![중요 보호](./media/protect-files-with-o365-labels-dlp/sensitive_w_dlp.png)

그리고 나서 다음 단계를 사용하여 사용자가 조직 외부의 극비 SharePoint Online 팀 사이트에서 문서를 공유할 때 다른 사용자를 차단하는 DLP 정책을 구성합니다.

1. 브라우저의 **Microsoft Office 홈** 탭에서 **보안 및 준수 센터** 타일을 클릭합니다.
2. 브라우저의 새 **보안 및 준수** 탭에서 **데이터 손실 방지 > 정책**을 차례로 클릭합니다.
3. **데이터 손실 방지** 창에서 **+ 정책 만들기**를 클릭합니다.
4. **Start with a template or create a custom policy(템플릿으로 시작하거나 사용자 지정 정책 만들기)** 창에서 **사용자 지정**, **다음**을 차례로 클릭합니다.
5. **정책 이름 지정** 창의 **이름**에서 이름에 극비 수준 DLP 정책의 이름을 입력하고 **다음**을 클릭합니다.
6. **위치 선택** 창에서 **Let me choose specific locations(특정 위치 직접 선택)**를 선택하고 **다음**을 클릭합니다.
7. 위치 목록에서 **Exchange 전자 메일** 및 **OneDrive 계정** 위치를 사용하지 않도록 설정하고 **다음**을 클릭합니다.
8. **Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **편집**을 클릭한 다음, **Choose the types of content to protect(보호할 콘텐츠 형식 선택)** 창의 드롭다운 상자에서 **추가**, **레이블**을 차례로 클릭합니다.
9.  **레이블** 창에서 **+ 추가**를 클릭하고, **극비** 레이블을 선택하고, **추가**를 클릭한 다음 **완료**를 클릭합니다.
10. **Choose the types of content to protect(보호할 콘텐츠 형식 선택)** 창에서 **저장**을 클릭하고, **Customize the types of sensitive info you want to protect(보호할 중요 정보 유형 사용자 지정)** 창에서 **다음**을 클릭합니다.
11. **중요한 정보를 발견하면 ** 창에서 **팁 및 전자 메일 사용자 지정**을 클릭합니다.
12. **Customize policy tips and email notifications(정책 팁 및 전자 메일 알림 사용자 지정)** 창에서 **Customize the policy tip text(정책 팁 텍스트 사용자 지정)**를 클릭합니다.
13. 텍스트 상자에서 다음과 같이 입력하거나 붙여넣은 다음 [확인]을 클릭합니다.
 * 조직 외부의 사용자와 공유하려면 파일을 다운로드한 다음 파일을 엽니다. **파일**, **문서 보호**, **암호 설정**을 차례로 클릭한 다음 강력한 암호를 지정합니다. 암호를 별도의 전자 메일 또는 다른 통신 수단으로 보냅니다.
 * 또는 조직 외부의 파일을 공유하는 방법을 사용자에게 지시하는 사용자 고유의 정책 팁을 입력하거나 붙여넣습니다.
14. **What do you want to do if we detect sensitive info?(중요 정보를 검색하는 경우 어떤 작업을 수행하시겠습니까?)** 창에서 **Require a business justification to override(재정의하는 비즈니스 사유 필요)**를 선택하고 **다음**을 클릭합니다.
15. **Do you want to turn on the policy or test things out first?(먼저 정책을 사용하도록 설정하거나 테스트하시겠습니까?)** 창에서 **예**를 클릭하는 대로 사용하도록 설정하고 **다음**을 클릭합니다.
16. **설정 검토** 창에서 **만들기**, **닫기**를 차례로 클릭합니다.

결과적으로 극비 SharePoint Online 팀 사이트에 대한 구성은 다음과 같습니다.

 ![극비 보호](./media/protect-files-with-o365-labels-dlp/hc_w_dlp.png)

자세한 정보는 [AIP를 사용하여 파일 보호](protect-files-with-aip.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계
[정치적 캠페인, 비영리 조직, 및 기타 기밀 조직에 대 한 Microsoft 보안 지침](https://technet.microsoft.com/library/mt493213.aspx)

[SharePoint Online 사이트 및 파일 보호](secure-sharepoint-online-sites-and-files.md)

[개발/테스트 환경의 SharePoint Online 사이트 보호](secure-sharepoint-online-sites-dev-test.md)

[클라우드 채택 및 하이브리드 솔루션](https://technet.microsoft.com/library/dn262744.aspx)





