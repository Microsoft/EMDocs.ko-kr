<properties pageTitle="기술 문서에서 사용되는 사용자 지정 마크다운 확장"  description="docs.microsoft.com/ems 기술 문서의 포함된 비디오, 정보 및 팁, 재사용 가능 콘텐츠 및 기타 항목을 구현하는 사용자 지정 마크다운 확장을 나열합니다." services="" solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" editor=""/>

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar"/>

## EMS의 사용자 지정 마크다운 확장
방법:
- [ ] #34 참고, 중요 등에 대해 마크다운 확장을 사용하는지 확인합니다. 
- #35 EMS가 토큰과, 정확한 디렉터리 위치를 사용하는지 확인합니다.
- [ ] #36 사용자 지정 아이콘 파일을 사용할 수 있고 정확한 위치에 설치되었는지 확인합니다.
- [ ] #37 미디어 파일을 사용하는 토큰의 디렉터리 이름을 확인합니다.
- [ ] #38 토큰 사용을 위한 정확한 절차를 확인합니다.
- [ ] #39 토큰 사용을 구문의 예를 제공합니다. 
- [ ] #40 EMS 설명서 URL을 확인합니다.
- #41 Channel 9의 비디오를 외부 기록기에서 사용할 수 있는지 확인합니다. 
- [ ] #42 Channel 9의 EMS 비디오 위치를 확인합니다.
- [ ] #43 Channel 9의 EMS 비디오 사용을 확인합니다.
- [ ] #44 비디오 포함 구문을 확인합니다.
- [ ] #45 Github에서 렌더링된 예제가 필요합니다.
- [ ] #46 Github에서 렌더링된 비디오 예제가 필요합니다.
- [ ] #47 EMS 문서 웹 사이트에서 렌더링된 예제가 필요합니다. 
- [ ] #48 선택기가 EMS 문서에 사용 가능한지 확인
- [ ] #49 단순 선택기 대체 예제 필요
- [ ] #50 단순 선택기 구문 확인
- [ ] #51 대체 단순 선택기 구문 필요
- [ ] #52 대체 단순 선택기 예제 필요
- [ ] #53 양방향 선택기가 설명대로 작동하는지 확인합니다.
- [ ] #54 대체 양방향 선택기 예제 필요
- [ ] #55 양방향 선택기 구문 확인
- [ ] #56 대체 양방향 선택기 예제 필요


## 마크다운이 있는 일반 도움말

아직 [EMS에 대한 마크다운 작성](./authoring-in-markdown.md) 항목을 확인하지 않은 경우, 계속하기 전에 해당 항목을 읽는 것이 좋습니다. 

## 기술 문서에서 사용되는 사용자 지정 마크다운 확장

관련 문서에서는 단락, 링크, 목록, 제목 등의 대부분의 서식 지정에 GitHub에서 선호하는 마크다운을 사용하고 있습니다. 그러나 렌더링된 Microsoft.com/ems페이지에서 더 다양한 서식 지정이 필요한 경우 사용자 지정 마크다운 확장을 사용합니다. 다음은 현재 사용 중인 확장입니다.

+ [참고 및 팁]
+ [토큰]
+ [포함된 비디오]
+ [기술 및 플랫폼 선택기]

## 참고 및 팁
<span style="color:red;">참고, 중요 등에 대해 마크다운 확장을 사용하는지 확인합니다.</span>
다음 4가지 유형의 참고 및 팁에서 선택할 수 있습니다.

- EMS.NOTE
- EMS.WARNING
- EMS.TIP
- EMS.IMPORTANT

### 사용량
일반적으로 글 전체에서 참고 및 팁 을 필요에 따라 사용하게 됩니다. 이 항목을 사용할 때는 다음과 같이 적합한 참고 또는 팁 유형을 선택합니다.

- EMS.NOTE: 본문의 요점을 강조하거나 보충하는 중립적 또는 긍정적인 정보를 강조하는 데 사용합니다. 참고는 특별한 경우에만 적용되는 정보를 제공합니다.

  ![](./media/notes-note.png)

- EMS.WARNING: 사용자에게 향후 문제를 야기할 수 있는 상황을 경고하는 데 사용합니다. 예를 들어, 특정 옵션이나 특정 선택 사항을 지정할 경우 특정 상황에 영구적으로 고정되는 상황이 있습니다.

  ![](./media/notes-warning.png)

- EMS.TIP: 사용자가 자신의 특정 요구에 따라 텍스트에 설명되어 있는 방법과 절차를 적용하는 데 도움을 주기 위해 사용합니다. 팁에서는 명확하지 않을 수 있는 대안을 제시하기도 합니다. 그러나, 팁은 텍스트의 기본적인 이해에 필수적인 것이 아닙니다.

  ![](./media/notes-tip.png)

- EMS.IMPORTANT: 작업을 완료하는 데 필수적인 정보를 제공하기 위해 사용합니다.

  ![](./media/notes-important.png)

이러한 참고와 팁은 코드 블록, 이미지, 목록, 링크 등을 지원하지만 팁은 가능한 간결하고 명확하게 유지합니다. 서식 지정이 많은 복잡한 참고를 작성할 경우 기사 본문에 또 다른 섹션이 필요하게 될 수 있습니다. 또한 기사에 참고가 너무 많으면 산만해지고, 스캔이나 판독이 어려울 수 있습니다.

### 마크다운 샘플

샘플에서는 모두 EMS.NOTE를 나타냅니다. TIP, WARNING 또는 IMPORTANT를 사용하려면 마크다운의 "NOTE"를 대체합니다.

    > [EMS.TIP]

    > [EMS.WARNING]

    > [EMS.IMPORTANT]

단일 단락:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account. If you don't have an account, you can create a free account in just a couple of minutes.

다중 단락:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account.
    >
    > If you don't have an account, you can [create a free account](https://signup.live.com/signup) in just a couple of minutes.

## 토큰
<span style="color:red;">EMS가 토큰과, 정확한 디렉터리 위치를 사용하는지 확인합니다.</span>
GitHub 리포지토리에서 재사용 가능한 텍스트 부분을 "토큰"이라고 합니다. 여러 문서에서 사용해야 하는 텍스트가 있는 경우, 마크다운 파일에 텍스트 부분에 대한 참조를 포함합니다. 텍스트 부분(토큰) 자체는 단순 마크다운(.md) 파일입니다. 여기에는 텍스트, 링크, 이미지 등, 모든 유효한 마크다운이 포함될 수 있습니다. 

모든 토큰 마크다운 파일은 <span style="color:red;">사용자 지정 아이콘 파일이 사용 가능하며 정확한 위치에 설치되었는지 확인</span>에 포함되어야 합니다. 리포지토리 루트의 [/tokens directory](위치 수정 필요)입니다. 문서가 게시되면 토큰 텍스트가 게시된 항목에 자연스럽게 통합됩니다.

- 토큰을 참조하기 위해 특정 구문을 사용합니다.

- 토큰에 넣은 미디어 파일은 토큰에 특정한 `/media` 폴더에 만들어야 합니다. 포함된 토큰의 미디어 폴더 <span style="color:red;">미디어 파일을 사용하는 토큰의 디렉터리 이름을 확인합니다</span>[the ems-content/tokens/media folder](위치 수정 필요)입니다. 

## 사용량
<span style="color:red;">토큰 사용을 위한 정확한 절차를 확인합니다.</span>
- 여러 문서에 같은 텍스트를 표시해야 할 때마다 토큰을 사용합니다.
- 토큰은 한두 단락, 공유 프로시저 또는 공유 섹션 등, 내용이 많은 콘텐츠에 사용하면 유용합니다. 한 문장보다 작은 대상에는 토큰을 사용하지 않습니다. 제품 이름이나 불완전한 문장에 대한 것이 아닙니다.
- 다른 토큰 안에 토큰을 포함하지 않습니다. 게시 시스템에 문제를 일으킬 수 있습니다.
- 파일 간에 미디어를 공유하지 않습니다. 각각의 토큰과 문서에는 고유한 이름이 있는 별도의 파일을 사용합니다. 토큰과 연결된 미디어 폴더에 미디어 파일을 저장합니다.
- 토큰을 문서의 유일한 콘텐츠로 사용하지 않습니다. 토큰은 글의 나머지 콘텐츠를 보완하는 용도입니다.
- 모든 토큰은 `/token` 디렉터리에 있어야 하므로 문서로부터 토큰까지의 경로는 항상

    ../token입니다.

- 문서와 토큰 모두에서 링크나 이미지 파일 이름 참조를 반복하지 않습니다. 참조 반복을 방지하기 위해 링크 참조나 미디어 파일 이름에 "-token"을 추가합니다.

 **링크 참조**

 변경 전: odata.org
 변경 후: odata.org-token

 **이미지 참조**

 변경 전: table.png
 변경 후: table-token.png

### 토큰에 대한 마크다운 예제
<span style="color:red;">토큰 사용을 구문의 예를 제공합니다. </span> 
설명서 문서에 토큰을 추가하기 위한 구문은 다음과 같습니다.

    [EMS.TOKEN [token-short-name](../tokens/token-file-name.md)]

예제

    [EMS.INCLUDE [howto-blob-storage](../tokens/howto-blob-storage.md)]

토큰의 첫 부분은 경로나 .md 확장명 없는 토큰 이름입니다. 두 번째 부분은 /token 디렉터리에서 토큰에 대한 상대 경로로, .md 확장명이 포함됩니다.

### 렌더링 

렌더링된 GitHub 페이지에서 토큰은 다음과 같이 렌더링됩니다.

 [EMS.TOKEN howto-blob-storage]

<span style="color:red;">EMS 설명서 URL 확인</span> http://docs.microsoft.com/ems의 렌더링된 HTML 페이지에서 토큰으로부터의 HTML은 문서의 나머지 HTML에 병합됩니다. 그러나 HTML은 원래의 토큰 마크다운 파일 이름과 GitHub 커밋 해시가 있는 HTML 주석을 포함합니다. 이 주석은 문제 해결을 위해 포함된 것이므로, 원본 콘텐츠를 GitHub에서 쉽게 식별 및 확인할 수 있습니다.

  ![](./media/token.png)


## 포함된 비디오
<span style="color:red;">Channel 9의 비디오를 외부 기록기에서 사용할 수 있는지 확인합니다.</span>
기술 문서에서는 비디오가 Microsoft [Channel 9](http://channel9.msdn.com/) 사이트에 있으면 비디오를 포함할 수 있게 지원합니다. Channel 9의 비디오는 <span style="color:red;">Channel 9의 EMS 비디오 위치 확인</span> [docs.microsoft.com 비디오 센터](실제 위치 필요)에 통합되어야 합니다. 현재는 포함된 YouTube 비디오를 지원하지 않습니다. **link-- to YouTube커뮤니티에 포함하려는 비디오가 게시된 경우 해당 커뮤니티를 활용할 수 있습니다.

### 사용량
<span style="color:red;">Channel 9에서 EMS 비디오의 사용방법을 확인합니다.</span>
- 비디오가 채널 9 비디오 센터에 있는지 확인합니다.

- Channel 9에 있는 비디오의 친숙한 URL에서 비디오 ID를 복사합니다. 예를 들어 [https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more](https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more)에 있는 비디오 ID는 ** ???입니다. **.

### 구문
<span style="color:red;">비디오 포함 구문을 확인합니다. </span> 
    > [EMS.VIDEO video-id-string]

### 렌더링 
<span style="color:red;">Github에서 렌더링된 비디오 예제가 필요합니다. </span> 
GitHub: [Github에서 추가될 때 문서가 보이는 방식에 대한 예제 필요](something.md)

<span style="color:red;">EMS 문서 웹 사이트에서 렌더링된 예제가 필요합니다. </span> 
게시된 문서: [통합 시 문서 웹 사이트에서 문서가 보이는 방식에 대한 예제 필요](실제 위치 필요)

## 기술 및 플랫폼 선택기
<span style="color:red;">선택기가 EMS 문서에 사용 가능한지 확인</span>
모든 기술 및 플랫폼 구현에서 차이를 해결하기 위해 동일한 문서의 여러 버전을 제작할 때 기술 및 플랫폼 전환 기능을 사용합니다. 이 기능은 일반적으로 개발자용 모바일 플랫폼 콘텐츠 제작에 가장 많이 해당합니다. 현재 [단순 선택기](#simple-selectors)와 [양방향 선택기](#two-way-selectors) 등의 2가지 선택기 유형이 있습니다.

선택의 각 항목마다 동일한 선택기 마크다운이 있으므로 토큰에서 항목에 대한 선택기를 배치한 다음 동일한 선택기를 사용하는 모든 항목에서 해당 토큰을 참조하는 것이 좋습니다.

### 단순 선택기

단순(단방향) 선택기는 제목 바로 아래에 옵션 단추 집합을 렌더링합니다. 고객이 .NET, Node.js, Java처럼 단일 플랫폼이나 기술 집합을 선택해야 할 경우 이 단추를 사용합니다.  모든 선택기에 사용자 지정 마크다운 확장을 사용하며, 선택기에는 HTML을 사용하지 않습니다.  

<span style="color:red;">단순 선택기 대체 예제가 필요합니다. 참조를 위해 이 Azure 버전을 여기에 유지합니다.</span>
[알림 허브 시작](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/)에서 제작자가 동일한 문서의 8개 버전을 만들면서도 선택기를 사용하여 해당 문서 간의 탐색을 구현한 방법을 확인할 수 있습니다.

![단순 선택기 예제](./media/selectors.png)

#### 구문
<span style="color:red;">단순 선택기 구문 확인</span>
    > [EMS.SELECTOR]
    - [Link #1 Label](link #1 url)
    - [Link #2 Label](link #2 url)

#### 예제
<span style="color:red;">대체 단순 선택기 구문 필요</span>
    > [EMS.SELECTOR]
    - [Windows Runtime 8.1 Universal](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone Silverlight 8.x](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [Baidu](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)
    - [Chrome](../articles/notification-hubs-chrome-get-started/)

#### 렌더링 

<span style="color:red;">단순 선택기 대체 예제가 필요합니다. 참조를 위해 이 항목을 여기에 유지합니다.</span>
위의 이미지는 docs.microsoft.com/ems에서의 렌더링을 보여 줍니다. 렌더링된 GitHub 페이지에서 선택기는 링크의 글머리 기호 목록으로 렌더링됩니다.

### 양방향 선택기
<span style="color:red;">양방향 선택기가 설명대로 작동하는지 확인합니다.</span>
양방향 선택기에서는 사용자가 양방향 매트릭스에서 항목을 선택할 수 있습니다. Mobile Services 등과 같은 EMS 기술이 여러 백엔드 플랫폼과 여러 클라이언트를 모두 지원할 경우 양방향 선택기가 반드시 필요합니다. 고려할 사항은 다음과 같습니다.

- `(Platform | Backend)`로 설계되었으나, 이제 드롭다운 텍스트를 사용자 지정할 수 있습니다.
- 매트릭스의 모든 지점마다 목록 항목이 필요하지 않으며 항목 URL이 존재하는 위치에 한 항목만 있으면 되므로 중복되지 않습니다.
- 이 링크는 보통은 다른 GitHub 항목이지만 모든 URL이 될 수 있습니다.

<span style="color:red;">양방향 선택기 대체 예제가 필요합니다. 참조를 위해 이 Azure 버전을 여기에 유지합니다.</span>
[Mobile Services 시작](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/)에서 제작자가 동일한 문서의 15개 버전을 만들면서도(모바일 클라이언트 플랫폼 9개, 백엔드 플랫폼 2개) 선택기를 사용하여 해당 문서 간의 탐색을 구현한 방법을 확인할 수 있습니다. 3개 문서는 두 백엔드 버전을 갖지 않습니다.

![양방향 선택기 예제](./media/selector-list.png)

#### 구문
<span style="color:red;">양방향 선택기 구문 확인</span>
    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Dropdown1Text1 | Dropdown2Text1 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 | Dropdown2Text2 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 | Dropdown2Text3 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 | Dropdown2Text4 )](../articles/dropdown1-text1-dropdown2-text1.md)

#### 예제
<span style="color:red;">대체 양방향 선택기 예제 필요</span>
    > [AZURE.SELECTOR-LIST (Platform | Backend )]
    - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Windows Runtime 8.1 universal | C#)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Runtime 8.1 universal C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)
    - [HTML](../articles/mobile-services-html-get-started/)
    - [PhoneGap](../articles/mobile-services-javascript-backend-phonegap-get-started/)
    - [Sencha](../articles/partner-sencha-mobile-services-get-started/)

#### 렌더링 
<span style="color:red;">양방향 선택기 대체 예제가 필요합니다. 참조를 위해 여기에 유지합니다.</span>
위의 이미지는 azure.microsoft.com에서의 렌더링을 보여 줍니다. 렌더링된 GitHub 페이지에서 선택기는 링크의 글머리 기호 목록으로 렌더링됩니다.

<!--Anchors-->
[Notes and tips]: #notes-and-tips
[Tokens]: #tokens
[Embedded videos]: #embedded-videos
[Technology and platform selectors]: #technology-and-platform-selectors

##홈으로 돌아가기

- [Overview article](./../README.md)
- [Index of guidance articles](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


