<properties pageTitle="EMS에 대한 마크다운 작성" description="Enterprise Mobility Suite 리포지토리에 설정된 지침에 따라 마크다운으로 이미지를 만드는 방법을 설명합니다." services=""     solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# EMS에 대한 마크다운 작성

이렇게 하려면: 
- [ ] #23 이미지 /articles/<service-directory>/media에 대한 EMS 문서 레이아웃을 확인합니다.
- [ ] #24 /articles/<service-directory>/media에 대한 예제를 제공합니다.
- [ ] #25 3개의 단락에서 EMS doc 페이지 가운데 열의 이미지에 대한 최대 너비(580 또는 600픽셀)를 확인합니다.
- [ ] #26 EMS에 http://aka.ms/CnESymbols에서 제공하는 것과 다른 개념 아트에 대한 일련의 기호가 있는지를 확인합니다. 
- [ ] #27 참가자 가이드에 대한 URL을 확인합니다.
- [ ] #28 전체 연결 구성표를 확인합니다.
- [ ] #29 서비스 하위 디렉터리에서 구성된 문서인가요?
- [ ] #30 방법론을 연결하는 앵커를 확인해야 합니다.
- [ ] #31 연결 방법론 및 선택기의 사용을 확인합니다.
- [ ] #32 연결 체계가 올바르게 작동하는지 테스트합니다.

이 문서는 EMS 서비스 및 기술에 대한 기술 문서를 작성하는 방법에 대한 포인터를 포함합니다. 이러한 지침은 새 설명서를 작성하거나 기존 문서를 업데이트하는 경우 적용됩니다.

## EMS에 대해 작성하는 이유는 무엇인가요?

Microsoft EMS(Enterprise Mobility Suite)는 오늘날의 통합, 모바일, 클라우드 기반 서비스에 대한 방향을 제시하기 위해 특별히 만들어졌습니다. Microsoft Azure Active Directory Premium, Microsoft Intune 및 Microsoft Azure Rights Management 등 세 가지 주요 구성 요소는 처음부터 클라우드 서비스로 빌드되었습니다. 함께 작동하도록 디자인되고 시장에 있는 다른 프로그램과 달리 통합된 기술 제품군을 제공합니다. 또한 공격 온-프레미스를 감지하기 위해 EMS는 Microsoft Advanced Threat Analytics를 포함합니다. EMS를 사용하여 회사 자산을 보호하는 동안 회사 사용자는 선호하는 장치에서 생산성을 향상시킬 수 있습니다.

개별 제품에 대한 설명서를 만드는 작업은 항상 우선 순위에 있습니다. 하지만 EMS가 제품군이기 때문에 제품을 함께 사용하는 데 도움이 되는 문서 및 방법 문서를 찾고 있습니다. 제품 간 시나리오에 대한 설명서를 만들지만 자신의 회사 내에서 이러한 제품을 실제 사용하는 직원 및 사용자가 입력하는 내용도 환영합니다.

결과적으로 여러 가지 방법으로 기여할 수 있는 Github의 설명서를 개방했습니다.
- **텍스트 실수 수정** 고치고 싶지만 모두 잡아낼 수 없기 때문에 Github를 통해 연결하여 도와주세요.
- **새 항목 제안** 제공되는 프로시저 또는 주제에 어떤 문서 항목이 필요하지만 없는 경우 작성해주시면 살펴보겠습니다.
- **FAQ에 추가** 다루지 않은 항목에 대해 알고 싶지만 전체 항목이라기 보다 질문/응답 상황인 경우 FAQ에 추가하도록 제출해주시면 살펴보겠습니다. 

결론적으로 여러분이 훌륭한 제안 및 아이디어를 가지고 있다면 EMS 전체를 개선하는 데 참여할 수 있도록 하고자 합니다. 

## 문서 향상을 위한 팁

EMS를 작성할 때 다음 사항에 유의해야 합니다.

**EMS에 특정된 방법**
- 공식 제품 이름이 "Microsoft Enterprise Mobility Suite"이지만 "EMS 클라우드 ID 및 액세스 관리"와 같이 거의 항상 "EMS"라고 부릅니다.
- 서비스 또는 기능 이름 앞의 첫 번째 참조에서 "EMS"를 사용하고 삭제합니다(예: "EMS 클라우드 ID 및 액세스 관리"가 처음 사용한 후에 "클라우드 ID 및 액세스 관리"가 됨). 
- EMS는 모든 제목에 대/소문자인 문장을 사용합니다. 
- 혼란스럽기 때문에 일반적으로 머리 글자어를 피하도록 합니다.

**좋은 작성 방법**
- 다른 사용자에게 일대일로 대화하는 것처럼 일상적이고 친숙한 음성을 사용합니다. 자세한 내용은 [스타일 및 음성 항목](./style-and-voice.md)을 참조하세요.
- 작업을 수행하는 Word에 텍스트를 잘라내어 붙여 넣어는 경우라 하더라도 항목의 맞춤법 및 문법을 검사합니다.
- 간단한 문장을 사용합니다. 이해하기 쉽고 사람과 컴퓨터 번역기 모두가 보다 쉽게 번역할 수 있기 때문입니다.
- 설명 또는 보충을 사용하여 단계를 중단하지 마세요.
- 목록 또는 코드 조각 앞에 오는 모든 문장에 "다음" 또는 "다음과 같이"라는 단어를 포함합니다.
- 코드 조각을 포함하는 단계의 경우 단계에 대한 추가 정보를 주석으로 코드에 배치합니다. 
    - 사람이 읽어야 하는 텍스트의 양을 감소시킵니다. 
    - 주요 정보를 코드 프로젝트에 복사하여 나중에 참조할 때 코드가 수행하는 작업을 상기시킵니다.

## 마크다운이 있는 일반 도움말
- 일반 마크다운 팁은 Github 웹 사이트의 [Markdown 기본 사항](https://help.github.com/articles/markdown-basics/)을 참조하세요.
- 또한 [EMS 마크다운 치트시트](./media/ems-markdown-cheat-sheet.pdf?raw=true)를 다운로드할 수 있습니다. 
- 마크다운에 문서 교차 연결을 만들어야 하는 경우 아래 [연결 지침](#guidelines-for-linking-technical-articles)을 참조하세요.
- 웹 사이트 <span style="color:red;">URL 확인</span>(http://docs.microsoft.com/ems)은 [막힌 코드 블록](https://help.github.com/articles/creating-and-highlighting-code-blocks/#fenced-code-blocks)을 지원합니다. 코드 블록의 앞뒤 줄에 3개의 역따옴표 문자(''') 행을 삽입하여 막힌 코드 블록을 만듭니다. 텍스트의 나머지 부분에서 코드를 설정하는 편리한 방법입니다.   
- 또한 EMS는 코드 블록 내에서 [구문 강조](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting)를 지원합니다. 그러나 GitHub에서 선호하는 마크다운과 달리 여기에 코드의 첫 번째 줄에 [특정 언어를 지정](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting)하면 구문 색 구성표를 변경하고 EMS는 지정하는 프로그래밍 언어에 관계 없이 색 구성표를 강조 표시하는 **하나**의 구문만을 지원합니다.

## 마크다운으로 이미지 만들기
간단한 마크다운 구문에 따라 문서에 이미지를 포함할 수 있습니다. 

### 이미지 폴더 만들기 및 연결 구문

새 문서의 경우 다음 위치에 폴더를 만들어야 합니다.
<span style="color:red;">이미지에 대한 문서 리포지토리 레이아웃 확인</span>

    /articles/<service-directory>/media/

예를 들면 다음과 같습니다.
<span style="color:red;">예제 제공</span>

    /articles/identity-access/media/

폴더를 만들고 여기에 이미를 추가한 후에 문서에 이미지를 만들려면 다음 구문을 사용합니다.

```
![Alt image text](./media/your-image-filename.png)
```

## Enterprise Mobility Suite에 특정된 이미지 지침

스크린샷은 재현 단계를 포함할 수 없는 경우 현재 권장됩니다. 필요한 경우 콘텐츠가 스크린샷 없이 나타낼 수 있도록 콘텐츠를 작성합니다.

아트 파일을 만들고 포함하는 경우 다음 지침을 사용합니다.
- 가능하면 문서 간에 아트 파일을 공유합니다. 필요한 파일에 URL을 복사하고 문서에 추가합니다. 
- .PNG(Portable Network Graphic) 파일은 다른 서식 보다 항상 우선됩니다.
- 그림판(5픽셀)에 제공된 기본 너비의 빨간색 사각형을 사용하여 스크린샷에서 특정 요소를 눈에 띄게 합니다.  

    예:

    ![빨간색 사각형이 콜아웃으로 사용된 예입니다.](./media/gs13noauth.png)

- 스크린샷의 가장자리에 공백을 사용하지 않습니다. 스크린샷은 스크린샷의 흰색 영역이 웹 페이지와 혼용되지 않도록 1픽셀 너비의 회색 테두리가 있어야 합니다.
    - 가장자리에 흰색 배경을 남기는 방식으로 스크린 샷을 자를 경우 이미지 주위에 단일 픽셀 회색 테두리를 추가합니다.  
    - 그림판을 사용하는 경우 기본 색상표(#C3C3C3)에 밝은 회색을 사용합니다.
![회색 테두리](./media/grey-border-in-paint.png)     
    - RGB 값을 필요로 하는 그래픽 앱을 사용하는 경우 색 번호는 R195, G195, B195입니다. 
- Visio에서 이미지 주위에 회색 테두리를 쉽게 추가할 수 있습니다. 이렇게 하려면 다음을 수행합니다. 
  - 이미지를 선택합니다. 
  - 선을 선택하고 올바른 색을 설정하도록 합니다. 
  - 선 두께는 11/2포인트로 변경합니다.  

    **예:**

    ![공백 주위에 있는 회색 테두리의 예입니다.](./media/agent-700w.png)

- 공백이 있는 개념 이미지는 회색 테두리를 필요로 하지 않습니다.  

    **예:**

    ![공백 및 회색 테두리가 있는 개념 이미지의 예입니다.](./media/ic727360.png)

- 이미지를 너무 넓게 만들지 않도록 합니다. 너무 넓은 경우 이미지는 자동으로 조정됩니다. 그러나 때로 이미지 크기를 조정하면 이미지가 흐릿해지므로 이미지의 너비를 제한하여 580픽셀로 <span style="color:red;">최대 이미지 너비를 확인</span>하고 필요한 경우 제출하기 전에 수동으로 이미지를 크기를 조정하는 것이 좋습니다.

- 스크린샷에 명령 출력을 표시합니다.  사용자가 셸 내에서 작업하는 단계를 문서에 포함하는 경우 스크린샷에 명령 출력을 표시하는 것이 유용합니다. 이 경우에 일반적으로 약 72자로 셸 너비를 제한하면 이미지가 <span style="color:red;">최대 이미지 너비 확인</span> 580픽셀 너비 지침 내로 유지될 것입니다. 출력의 스크린샷을 가져오기 전에 창 크기를 조정하여 관련 명령 및 출력이 표시되도록 합니다(필요에 따라 한쪽에 빈 줄과 함께).
- 가능하면 Windows의 전체 스크린샷을 가져옵니다. 브라우저 창의 스크린샷을 가져오는 경우 브라우저 창의 크기를 조정하여 580픽셀 이하로 <span style="color:red;">최대 이미지 너비를 확인</span>하고 응용 프로그램이 창에 맞게 가능한 한 브라우저 창의 높이를 짧게 유지합니다.

    예:

    ![브라우저 창 스크린샷의 예입니다.](./media/helloworldlocal.png)

- 스크린샷에 표시되는 정보에 주의합니다. 반드시 회사 내부 정보 또는 개인 정보를 표시하지 않도록 합니다.
- 개념 아트 또는 다이어그램에서는 클라우드 및 엔터프라이즈 기호와 아이콘 집합에서 공식 아이콘을 사용합니다. 공용 집합은 <span style="color:red;">이러한 아이콘을 사용하는지 확인</span>http://aka.ms/CnESymbols에서 사용할 수 있습니다.


## 기술 문서 연결에 대한 지침

| 연결 시나리오 | 대상 링크에 대한 지침  |
|---------------|-----------|
|EMS 기술 문서에서 다른 EMS 기술 문서에 연결합니다.|상대적 링크를 사용합니다.|
|설명서 디렉터리 외부의 EMS 페이지, MSDN 라이브러리 항목, TechNet 라이브러리 항목 또는 기술 자료 문서에 연결합니다.|​문서 또는 항목에 대한 실제 링크를 사용합니다. 링크에서 en-us 언어 로캘을 삭제합니다.|
|EMS 문서에서 다른 웹 페이지에 연결합니다.|직접 링크를 사용합니다.|

### 친숙한 링크 텍스트를 사용합니다.

링크에 포함하는 단어는 친근해야 합니다. 즉, 정상 영어 단어 또는 연결하는 페이지의 제목이어야 합니다. "여기를 클릭"을 사용하지 않습니다. SEO에 잘못되었으며 대상을 적절하게 설명하지 않습니다.

**정확한 경우:**
<span style="color:red;">참가자 가이드에 대한 URL을 확인합니다.</span> 
- `For more information, see the [contributor guide index](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**잘못된 경우:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

<span style="color:red;">참가자 가이드에 대한 URL을 확인합니다.</span> 
- `For more information, click [here](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

### EMS 상대 링크에 대한 마크다운 구문
<span style="color:red;">전체 연결 구성표를 확인합니다.</span> 

EMS 기술 문서에서 다른 EMS 기술 문서에 인라인 링크를 만들려면 이 링크 서식을 사용합니다. 디렉터리의 문서 간에 새 연결을 만드는 경우 새 연결 구문을 수행해야 합니다.

문서는 루트 디렉터리에 있는 하위 디렉터리에서 문서로 연결합니다.

    [link text](../article-name.md)

루트 디렉터리의 문서는 서비스 하위 디렉터리의 문서에 연결합니다. 
<span style="color:red;">서비스 하위 디렉터리에서 구성된 문서인가요?</span>

    [link text](service-directory/article-name.md)

서비스 하위 디렉터리의 문서는 다른 서비스 하위 디렉터리의 문서에 연결합니다.

    [link text](../service-directory/article-name.md)
 
디렉터리의 문서는 동일한 디렉터리의 다른 문서에 연결합니다.

    [link text](article-name.md)


앵커를 더 이상 만들 필요가 없습니다. H2 제목에 게시되는 시점에 자동으로 생성됩니다. 수행해야 하는 작업은 H2 섹션에 대한 링크를 만듭니다.
<span style="color:red;">방법론을 연결하는 앵커를 확인해야 합니다.</span>

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

동일한 하위 디렉터리의 다른 문서에서 앵커를 연결하려면:

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

다른 서비스 디렉터리서에서 앵커를 연결하려면:

    [link text](service-directory/article-name.md#anchor-name)
    [Configure your profile](service-directory/media-services-create-account.md#configure-your-profile)


## 사용자 지정 마크다운 링크 구문
<span style="color:red;">연결 방법론 및 선택기의 사용을 확인합니다.</span>

includes 파일이 다른 디렉터리에 있기 때문에 아래와 같이 상대 경로를 사용해야 합니다. includes 파일에서 단일 문서에 대한 링크의 경우 이 서식을 사용합니다.

    [link text](../articles/service-folder/article-name.md)
    
[사용자 지정 마크다운 확장 지침](custom-markdown-extensions.md#includes)에서 includes 파일을 사용하는 방법에 대해 자세히 알아봅니다.

includes 파일에 포함된 선택기가 있는 경우 이러한 종류의 링크를 사용합니다. 

    > [EMS.SELECTOR-LIST (Dropdown1 | Dropdown2)]
    - [(Text1 | Example1 )](../articles/service-folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/service-folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/service-folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/service-folder/article-name4.md)

EMS의 페이지에 연결하려면(예: 가격 책정 페이지, 서비스 수준 계약 페이지 또는 설명서 문서가 아닌 다른 페이지) 절대 URL을 사용하지만 *en-us* 로캘을 생략합니다. 여기에서 목표는 링크가 GitHub 및 렌더링된 사이트 작동하는 것입니다.

    [link text](https://www.microsoft.com/server-cloud/enterprise-mobility/pricing.aspx)

링크를 테스트하려면 포크에 페이지를 푸쉬하고 렌더링된 보기에서 보며 샌드박스에 게시합니다. GitHub 버전의 페이지에 있는 교차 링크는 URL의 대상이 분기에 있는 한 작동해야 합니다.

## 참조 스타일 링크

원본 콘텐츠를 보다 쉽게 읽을 수 있도록 참조 스타일 링크를 사용할 수 있습니다. 참조 스타일 링크는 이 문서 끝에 긴 URL을 이동할 수 있도록 하는 단순화된 구문으로 인라인 링크 구문을 바꿉니다. Daring Fireball의 예제는 다음과 같습니다.

인라인 텍스트:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

이 문서 끝에 있는 연결 참조입니다.

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/


## 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)



<!--HONumber=Mar16_HO1-->


