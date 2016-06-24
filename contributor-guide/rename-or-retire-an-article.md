<properties pageTitle="EMS 기술 자료의 사용을 중지하거나 이름을 변경하는 경우 수행할 단계" description="EMS 기술 자료의 사용을 중지하거나 이름을 변경하는 경우 수행할 단계입니다." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# EMS 기술 자료의 이름을 변경하거나 사용을 중지하는 경우 수행할 단계

이렇게 하려면:
- [ ] #57 사용이 중지된 내용이 EMS에서 작동되는 방식인지 확인합니다. 일련의 내부 전용 프로시저처럼 보입니다. 
- [ ] #58 외부 기록기가 Microsoft 콘텐츠에 웹 분석 도구를 실행할 수 있는지 확인합니다. 
- [ ] #59 리포지토리에서 교차 연결을 찾는 프로시저를 테스트합니다.
- [ ] #60 EMS 문서에 대한 URL을 확인합니다.  
- [ ] #61 외부 작성기의 경우 교차 연결 제거가 가능한지 확인합니다. 
- [ ] #62 외부 작성기가 리디렉션을 만들 수 있는지 확인합니다.
- [ ] #63 외부 작성기가 리포지토리에서 문서를 삭제할 수 있는지 확인합니다.
- [ ] #64 외부 작성기가 검색 엔진에서 Microsoft 콘텐츠를 제거하도록 요청할 수 있는지 확인합니다.


<span style="color:red;">사용이 중지된 내용이 EMS에서 작동되는 방식인지 확인합니다. 일련의 내부 전용 프로시저처럼 보입니다. </span>로 변환해야 합니다.
http://docs.microsoft.com/ems의 기술 문서 섹션에서 사용 중지되어야 하는 문서의 작성자로 나열된 SME(주제 전문가)를 위한 지침입니다. 또한 파일의 이름을 바꿀 경우 단계가 적용됩니다.

SME 작성자는 몇 가지 단계를 수행하여 사이트에서 콘텐츠의 사용을 중지하는 경우 웹 사이트의 사용자가 잘못된 환경을 보유하지 않도록 콘텐츠의 사용을 정상적으로 중지해야 합니다. 문서를 삭제하거나 문서의 이름을 변경하는 것은 적절하지 않습니다.

사용자가 EMS 커뮤니티의 멤버이고 어떤 이유로든 문서의 사용을 중지하려는 경우 작성자에게 문서의 잘못된 부분을 알릴 수 있도록 문서에 대한 코멘트를 남겨주세요.

## 1단계: 인바운드 링크 관리

콘텐츠에 대한 타사 인바운드 링크가 있는지를 확인합니다. 문서에 대한 웹 지점의 블로그, 포럼 및 다른 콘텐츠인 경우가 매우 자주 있습니다. 대부분의 경우 블로그 소유자로 작업하여 이 링크를 변경할 수 있으며 포럼 게시물에서 링크를 제거하거나 업데이트할 수 있습니다. <span style="color:red;">외부 기록기가 Microsoft 콘텐츠에 웹 분석을 실행할 수 있는지 확인합니다. </span>웹 분석 도구는 이러한 방식으로 관리해야 할 수도 있는 트래픽이 높은 인바운드 링크가 있는지를 알려줄 수 있습니다.

## 2단계: 기술적 내용 리포지토리에서 문서에 대한 모든 교차 연결 제거
<span style="color:red;">리포지토리에서 교차 연결을 찾는 프로시저를 테스트합니다.</span>
1. 최신 로컬 분기에서 작업하는지 확인하고 `git pull origin master`(또는 이 명령에 적절한 변형)을 실행합니다.

2.  <span style="color:red;">리포지토리에서 경로를 확인합니다.</span> 사용을 중지하려는 문서에 연결된 문서 및 토큰에서 \EMDocs\Solutions 폴더 및 \EMDocs\Token 폴더를 검색하고 교차 연결을 제거하거나 적절한 새 교차 연결로 바꿉니다. 검색을 사용하고 유틸리티를 교체하여 설치되어 있는 교차 연결을 찾을 수 있습니다. 그렇지 않으면 무료로 Windows PowerShell 원격을 사용할 수 있습니다. PowerShell을 사용하여 교차 연결을 찾는 방법은 다음과 같습니다.

 a. Windows PowerShell을 시작합니다.

 b. PowerShell 프롬프트에서 \EMDocs\Solutions 폴더로 변경합니다.

 `cd \EMDocs\Solutions`

 c. 이 명령을 입력하여 삭제 중인 문서에 대한 참조를 포함하는 모든 파일을 나열합니다.

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  파일 이름 목록을 텍스트 파일(이 경우, 명명된 psoutput.txt)에 전송하려는 경우 다음을 수행할 수 있습니다.

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. 변경 내용을 추가 및 커밋하고 원본에 푸시합니다. 그리고 끌어오기 요청을 만들어서 원본에서 기본 리포지토리의 마스터 분기에 변경 내용을 이동합니다.

## 3단계: 모든 교차 연결 제거 
<span style="color:red;">외부 작성기의 경우 교차 연결 제거가 가능한지 확인합니다. </span>로 변환해야 합니다.
<span style="color:red;">의 다른 페이지에서 문서가 있는 경우 EMS 문서에 대한 URL을 확인합니다. </span> http://docs.microsoft.com/ems, 해당하는 경우 이를 제거하고 사용 중지된 페이지에 대한 리디렉션을 만들어야 합니다. 이 부분에 대한 서비스의 경우 설명서 방문 페이지를 유지 관리하고 업데이트한 사람과 작업해야 합니다. 해당 사용자를 알 수 없는 경우 콘텐츠 팀 파트너에게 문의합니다. 문서 방문 페이지를 유지 관리하고 업데이트하는 사용자는 다음의 두 가지를 수행해야 합니다.

1. Visual Studio에서 파일에 대한 교차 참조의 사용을 중지하기 위해 **전체** EMS 웹 솔루션을 스캔합니다. 교차 참조를 제거하거나 업데이트되는 교차 참조로 바꿉니다. HTML 링크에 관련된 리소스 문자열 뿐만 아니라 HTML 링크를 제거해야 합니다. 

2. <span style="color:red;">외부 작성기가 리디렉션을 만들 수 있는지 확인합니다.</span>대체 문서가 있으면 문서에 대한 리디렉션을 만듭니다. 

3. 리포지토리에 대한 변경 내용을 확인합니다.

## 4단계: 문서의 사용 중지
<span style="color:red;">외부 작성기가 리포지토리에서 문서를 삭제할 수 있는지 확인합니다.</span>
이전 세 단계를 완료하고 변경 내용이 활성화된 후에 리포지토리에서 문서를 삭제할 수 있습니다.

## 5단계: 검색 엔진에서 캐시된 페이지 제거
<span style="color:red;">외부 작성기가 검색 엔진에서 Microsoft 콘텐츠를 제거하도록 요청할 수 있는지 확인합니다.</span>
법적 문제 또는 심각한 고객 문제로 인해 콘텐츠를 신속하게 제거해야 하는 경우에만 수행합니다. 기본 검색 엔진 프로세스에서 일반 우선 순위 페이지 삭제를 처리합니다. 이 웹 페이지로 이동하여 검색 엔진에서 캐시된 웹 페이지를 제거합니다.

[Bing](https://www.bing.com/webmaster/tools/content-removal?rflid=1)
[Google](https://www.google.com/webmasters/tools/removals?pli=1)


### 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


