<properties pageTitle="Enterprise Mobility Suite 기술 문서에 대한 메타데이터" description="문서에 필요한 메타데이터를 설명합니다." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Enterprise Mobility Suite 기술 문서에 대한 메타데이터

이렇게 하려면: 
- [ ] #11 각 속성에 대한 지침이 정확한지 확인합니다.
- [ ] #12 속성: 설명 섹션의 URL을 확인합니다.
- [ ] #13 서비스 목록 및 MS-Service 목록 값을 업데이트합니다(RobMazz 전자 메일 #3 2016-02-18 참조).
- [ ] #14 속성: 태그 섹션(EMS 문서 위치)에서 URL을 확인합니다.
- [ ] #15 속성: 태그에서 선택적 태그의 간단한 목록(3)을 확인합니다. 더 많은 태그가 필요한가요? 
- [ ] #16 태그: MS-Service 섹션에서 서비스 목록을 확인합니다.
- [ ] #17 태그: mstopic 섹션(RobMazz 전자 메일 #1 2016-02-18)에서 문서 유형(리소스 유형)의 목록을 업데이트합니다.
- [ ] #18 태그: ms.devlang 섹션(RobMazz 전자 메일 #4 2016-02-18)에서 프로그래밍 언어의 목록을 업데이트하고 승인합니다.
- [ ] #19 태그: ms.tgt_pltfrm 섹션(RobMazz 전자 메일 #2 2016-02-18)의 대상 플랫폼 목록을 확인합니다.
- [ ] #20 모든 링크(특히 앵커)가 제대로 작동하는지 확인합니다. 

모든 EMS 기술 문서는 속성 섹션 및 태그 섹션이라는 두 메타데이터 섹션을 포함합니다. 태그 섹션이 내부 콘텐츠 보고를 많이 사용하는 반면 속성 섹션은 일부 웹 사이트 자동화 및 SEO 자료를 사용합니다. 두 섹션이 모두 필요합니다.

- [구문]
- [사용량]
- [속성 섹션에 대한 특성 및 값]
- [태그 섹션에 대한 특성 및 값]

## 구문

속성 섹션에서는 다음 구문을 사용합니다.

    <properties
       pageTitle="Page title that displays in search results and the browser tab | Microsoft EMS"
       description="Article description that will be displayed on landing pages and in most search results"
       services="service-name"
       documentationCenter="dev-center-name"
       authors="GitHub-alias-of-only-one-author"
       manager="manager-alias"
       editor=""
       tags="optional"
       keywords="Separate terms with commas. Check with your SEO champ before you change content in this article containing these terms."/>

태그 섹션에서는 다음 구문을 사용합니다.

    <tags
       ms.service="required"
       ms.devlang="may be required"
       ms.topic="article"
       ms.tgt_pltfrm="may be required"
       ms.workload="na"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

## 사용량

- 요소 이름과 특성 이름은 대/소문자를 구분합니다.
- 속성 섹션은 파일의 첫 번째 줄이어야 합니다.
- 각 메타데이터 섹션의 뒤와 페이지 제목 앞에 빈 줄을 그대로 두어서 프로세스를 게시하는 동안 페이지 제목을 HTML로 올바르게 변환하도록 합니다.

## 속성 섹션에 대한 특성 및 값

![](./media/checkmark-small.png)**pageTitle**: 필수적이고, SEO에 중요합니다. 이 특성에 대한 텍스트는 브라우저 탭에 검색 결과의 제목으로 나타납니다. 공백을 포함하고 사이트 식별자를 포함하여 55-60자를 사용합니다 *| Microsoft EMS*(공간 파이프 공간 Microsoft EMS 형식).  pageTitle은 H1과 달라야 합니다.

![](./media/checkmark-small.png)**설명**: 필수적이고 SEO(관련성) 및 사이트 기능에 대해 중요합니다. 설명은 공백을 포함하여 최소 125자이며 최대 155자 길이여야 합니다. 고객이 검색 결과의 목록에서 선택할지 여부를 결정할 수 있도록 콘텐츠의 목적을 설명합니다. 값은 다음과 같습니다.

- 이 텍스트는 Google의 검색 결과에서 설명 또는 추상 단락으로 표시될 수 있습니다.
- 이 텍스트는 <span style="color:red;">확인 URL</span> [문서 색인 결과](http://docs.microsoft.com/ems/articles/)에 표시됩니다.

![](./media/checkmark-small.png)**서비스**: 서비스를 처리하는 문서에 필요합니다. 이 값은 "서비스 Slug"라고도 합니다. 모든 해당 서비스를 나열하여 쉼표로 구분합니다. 나열한 첫 번째 서비스는 페이지에 대한 탐색 이동 경로 및 페이지와 함께 표시되는 왼쪽 탐색 영역을 결정합니다.

서비스 값과 documentationCenter 값을 지정하는 문서에서 서비스 값은 이동 경로를 결정합니다. 나열된 추가 값은 게시된 문서에서 태그로 표시됩니다. 값은

- active-directory
- active-directory-b2c
- active-directory-ds
- app-service-api
- api-management
- app-service
- app-service-mobile
- app-service-web
- application-gateway
- application-insights
- 자동화
- 백업
- batch
- best-practice
- 요금 청구
- biztalk-services
- 캐시
- cdn
- cloud-services
- data-catalog
- data-factory
- data-lake-analytics
- data-lake-store
- devtest-lab
- dns
- documentdb
- expressroute
- event-hubs
- hdinsight
- iot-hub
- key-vault
- load-balancer
- machine-learning
- marketplace
- media-services
- mobile-engagement
- mobile-services
- multi-factor-authentication
- notification-hubs
- operational-insights
- operations-management-suite
- powerapps
- recovery-manager
- redis-cache
- remoteapp
- rights-management
- 스케줄러
- 검색
- security-center
- service-bus
- service-fabric
- site-recovery
- sql-database
- sql-data-warehouse
- sql-reporting
- 저장소
- 저장소
- storsimple
- stream-analytics
- traffic-manager
- virtual-machines
- virtual-network
- visual-studio-online
- vpn-gateway
- web-sites

![](./media/checkmark-small.png)**documentationCenter**: 개발자 센터를 통해 개발자 중심 문서 최상의 기능이 필요합니다. 문서에 적용되는 단일 개발자 센터 또는 언어를 지정합니다. 나열한 값은 페이지에 대한 탐색 이동 경로를 결정합니다. 서비스 값과 documentationCenter 값을 지정하는 문서에서 서비스 값은 이동 경로를 결정합니다. 값은

- **.net**
- **nodejs**
- **java**
- **php**
- **python**
- **ruby**
- **mobile**: 사용되지 않음 특정 모바일 플랫폼으로 대체합니다.
- **ios**: 새 값 검사
- **android**: 새 값 검사
- **windows**: 새 값 검사
- **xamarin**: 새 값 검사

![](./media/checkmark-small.png)**authors**: 하나의 값만 필요합니다. 기본 작성자 또는 문서 SME에 대한 GitHub 계정이 나열됩니다. 이 특성은 게시된 문서에 저자명을 결정합니다. 특성이 이름이 복수임에도 불구하고 하나만 나열합니다.

![](./media/checkmark-small.png)**manager**: Microsoft 참가자인 경우 필요합니다. 기술 영역에 대한 콘텐츠 게시 관리자의 전자 메일 별칭을 나열합니다. 커뮤니티 기고가 인 경우 특성이 포함 되어 있지만 우리가 양식을 채울 수 있도록 비워 둡니다.

![](./media/checkmark-small.png)**editor**: 사용되지 않습니다. 다른 용도로 사용하지 마십시오.

![](./media/checkmark-small.png)**tags**: 선택 사항입니다. 문서 인덱스 페이지에 대한 문서 이동 경로의 링크를 사용하려는 경우에만 포함됩니다. 미리 승인된 값 중 하나와 일치하는 필터링된 문서 목록에 대한 <span style="color:red;">URL 확인</span>(http://docs.microsoft.com/ems/articles/)합니다. 이러한 값은 콘텐츠 그룹화가 서비스에 되지 않은 경우 콘텐츠를 함께 그룹화하는 방법을 제공하도록 합니다. 이러한 태그는 문서를 적용하는 기술 스택을 나타내는 레이블을 제공할 수도 있습니다. 이 값은 자유 형식 태그 또는 해시 태그를 지원하지 **않습니다**. 사이트에서 태그를 사용할 수 있어야 합니다. 하나의 문서에 여러 태그 값을 제공할 수 있으며 이는 쉼표로 구분됩니다. 승인된 값은 다음과 같습니다.

<span style="color:red;">다음 태그 값을 확인합니다</span>
  - 검토
  - 요금 청구
  - mysql

![](./media/checkmark-small.png)**keywords**: 선택 사항입니다. SEO champs에서만 사용합니다. 쉼표로 용어를 구분합니다. **이러한 용어를 포함하는 이 문서의 콘텐츠를 변경하거나 삭제하기 전에 SEO champ로 확인합니다.** 이 특성은 SEO 챔피언이 대상으로 삼은 키워드를 기록하고 검색 순위를 개선하기 위해 추적합니다. 키워드는 게시된 HTML에서 제공되지 않습니다. 유효성 검사에는 이 특성이 필요하지 않습니다.

## 태그 섹션에 대한 특성 및 값

![](./media/checkmark-small.png)**ms.service**: 필요합니다. 문서를 적용하는 서비스, 도구 또는 기능을 지정합니다. 페이지당 하나의 값입니다.

 페이지가 여러 서비스에 적용되는 경우 대부분 직접 적용되는 서비스를 선택합니다. 예를 들어 서비스 버스 기능을 설명하는 웹 사이트에서 호스팅되는 앱을 사용하는 문서에는 **web-sites**가 아닌 **service-bus** 값이 있어야 합니다. 페이지는 여러 서비스에 동일하게 적용되는 경우 **multiple**을 선택합니다 페이지가 어떤 서비스에도 적용되지 않는 경우(드물지만) **NA**를 선택합니다.

<span style="color:red;">다음 값을 확인합니다</span>
 - **active-directory**
 - **api-management**
 - **app-service**: 앱 서비스에서 일반 개념 자료에만 적용됩니다
 - **app-service-api**
 - **app-service-logic**
 - **app-service-mobile**
 - **app-service-web**
 - **application-insights**
 - **자동화**
 - **백업**
 - **batch**
 - **biztalk-services**
 - **요금 청구**
 - **캐시**
 - **cdn**
 - **cloud-services**
 - **expressroute**
 - **hdinsight**
 - **iot-hub**
 - **key-vault**
 - **machine-learning**
 - **media-services**
 - **mobile-engagement**
 - **mobile-services**
 - **multi-factor-authentication**
 - **multiple**: 페이지는 여러 서비스에 동일하게 적용됩니다
 - **na**: 페이지는 (드물게) 서비스에 적용되지 않습니다
 - **notification-hubs**
 - **operational-insights**
 - **powerapps**
 - **recovery-manager**
 - **redis-cache**
 - **remoteapp**
 - **rights-management**
 - **스케줄러**
 - **service-bus**
 - **service-fabric**
 - **site-recovery**: 이전의 복구 서비스
 - **sql-database**
 - **sql-data-warehouse**
 - **sql-reporting**
 - **저장소**
 - **storsimple**
 - **traffic-manager**
 - **virtual-machines**
 - **virtual-network**
 - **visual-studio-online**
 - **vpn-gateway**
 - **web-sites**

![](./media/checkmark-small.png)**ms.devlang**: 필요합니다. 이 문서가 적용할 프로그래밍 언어를 지정합니다. 페이지당 단일 값입니다.

 페이지가 두 가지 프로그래밍 언어에 동일하게 적용되는 경우 **multiple**을 선택합니다. 페이지가 주로 개념적이며 해당 콘텐츠가 여러 프로그래밍 언어에 일반적으로 적용될 수 있는 경우 **multiple**을 선택합니다. 개발자에 페이지가 지정되지 않고 프로그래밍 언어 적용성가 관련되지 않은 경우 **NA**를 선택합니다. **rest-api**를 사용하여 REST API 참조 항목을 식별합니다.

<span style="color:red;">다음 값 확인</span>
 - **cpp**
 - **dotnet**
 - **java**
 - **javascript**
 - **multiple**: 페이지가 여러 프로그래밍 언어에 동일하게 적용됩니다.
 - **na**: 페이지가 개발자를 대상으로 하지 않고 프로그래밍 언어에 한정되지 않습니다.
 - **nodejs**
 - **objective-c**
 - **php**
 - **python**
 - **rest-api**
 - **ruby**


![](./media/checkmark-small.png)**ms.topic**: 필요합니다. 항목 유형을 지정합니다. 참가자가 생성한 새 페이지는 대부분 문서 또는 참조입니다.

<span style="color:red;">다음 값 확인</span>
 - **article**: 개념 항목, 자습서, 기능 가이드 또는 다른 비참조 문서입니다.

 - **get-started-article**: 서비스에서 왼쪽 탐색의 시작 섹션에 소개된 문서에 할당합니다.

 - **hero-article**: 방문자가 신속하게 서비스를 사용하기 시작하고 가져오고 무료 평가판 등록 및 MSDN 정품 인증을 구동하는 서비스 또는 기능에 대한 소개를 제공하도록 디자인된 "hero" 자습서입니다. 서비스에 대한 설명서 방문 페이지 맨 위에 있는 기능을 제공하는 문서에만 이 값을 할당합니다.

 - **reference**: API 참조 페이지(REST API 포함) 또는 PowerShell cmdlet 참조 페이지입니다.

![](./media/checkmark-small.png)**ms.tgt_pltfrm**: 필요합니다. 예를 들어 Windows, Linux, Windows Phone, iOS, Android 또는 특수 캐시 플랫폼 등 대상 플랫폼을 지정합니다. 페이지당 하나의 값입니다. 이 값은 모바일 및 가상 컴퓨터를 제외한 대부분의 항목에서 **NA**입니다.

<span style="color:red;">다음 값 확인</span>
 - **cache-in-role**
 - **cache-multiple**
 - **cache-redis**
 - **cache-service**
 - **cache-shared**
 - **command-line-interface**
 - **ibiza**: Ibiza 포털을 사용하는 콘텐츠입니다. Ibiza 포털과 현재 포털 모두에서 설명하는 기능을 사용할 수 있는 경우에만 사용합니다.
 - **mobile-android** 
 - **mobile-html**
 - **mobile-ios**
 - **mobile-kindle**
 - **mobile-multiple**
 - **mobile-nokia-x**
 - **mobile-phonegap**
 - **mobile-sencha**
 - **mobile-windows**
 - **mobile-windows-phone**
 - **mobile-windows-store**
 - **mobile-xamarin**
 - **mobile-xamarin-android**
 - **mobile-xamarin-ios**
 - **multiple**: 페이지는 여러 플랫폼에 동일하게 적용됩니다
 - **na**: 플랫폼 지정자는 이 페이지에 적용되지 않습니다.
 - **powershell**
 - **vm-linux**
 - **vm-multiple**
 - **vm-windows**
 - **vm-windows-sharepoint**
 - **vm-windows-sql-server**
 - **vs-getting-started**: VS 시작하기 페이지 그룹을 식별합니다. 12/1/14에 추가된 태그입니다.
 - **vs-what-happened**: VS 시작하기 변경된 내용 페이지를 식별합니다. 12/1/14에 추가된 태그입니다.

![](./media/checkmark-small.png)**ms.workload**: 필요합니다. 페이지가 적용되는 워크로드를 지정합니다. 문서만 당 하나의 값이 있습니다. 

![](./media/checkmark-small.png) **ms.date**: 필요합니다. 문서가 관련성, 정확성, 올바른 스크린샷 및 작업 링크에 대해 마지막으로 검토된 날짜를 지정합니다. Mm/dd/yyyy 형식으로 날짜를 입력합니다. 이 날짜가 게시된 문서에도 마지막 업데이트된 날짜로 나타납니다.

![](./media/checkmark-small.png) **ms.author**: 필요합니다. 항목과 연결된 작성자를 지정합니다. 여러 값을 지정하려면 세미콜론으로 구분해야 합니다. Microsoft 별칭 또는 전체 전자 메일 주소를 사용할 수 있습니다. 길이는 200자 이하여야 합니다.

## 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)


<!--Anchors-->
[Syntax]: #syntax
[Usage]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section


<!--HONumber=Mar16_HO1-->


