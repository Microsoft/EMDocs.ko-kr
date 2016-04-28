<properties pageTitle="EMS 기술 문서의 파일 이름과 위치" description="새 문서를 만들 때 따라야 하는 명명 규칙과 문서의 파일 구조를 설명합니다." metaKeywords="" services="" solutions="" documentationCenter="" authors="tysonn" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# EMS 기술 문서의 파일 이름과 위치
방법: 
- [ ] #7 예제에 대한 서비스 동적 필드 가져오기
- [ ] #8 파일 명명 패턴 확인
- [ ] #9 파일 명명 패턴의 대체 예제 제공
- #10 모든 링크(특히 앵커)가 제대로 작동하는지 확인

기술 콘텐츠 저장소에서는 모든 문서에 단일 폴더(**articles** 폴더)를 사용합니다. 폴더 계층 구조는 없으며 모든 문서가 플랫 파일 구조로 있게 됩니다. 그 안에 문서가 담긴 폴더를 만들 경우 문서가 게시되지 않습니다.

파일 구조를 구성 기준으로 사용하는 대신, 항목을 명확히 식별하고 웹에서의 원할한 검색을 위해 엄격한 명명 규칙을 사용하고 있습니다.

기억해야 하는 사항은 다음과 같습니다.

+ [파일 명명 규칙]
+ [파일 이름 패턴]
+ [예제]
+ [파일 이름 승인]

## 파일 명명 규칙

- 공백이나 문장 부호가 없습니다. 파일 이름의 단어를 구분하려면 하이픈을 사용합니다.
- 모두 소문자를 사용합니다.
- 80자를 넘지 않습니다(게시 시스템 제한).
- 개발, 구매, 구축, 문제 해결 등과 같이 특정한 동사를 사용합니다. 진행형(동명사)를 사용하지 않습니다.
- a, and, the, in, or 등의 짧은 단어를 포함하지 않습니다.
- 모든 파일은 마크다운 형태로, 확장장명 .md를 사용해야 합니다.

## 파일 이름 패턴

일반 명명 패턴은 다음과 같습니다.

<span style="color:red;">이 파일 명명 패턴에 대한 확인이 필요합니다.</span>
 **service-platform-language-content-product-version.md**

적용되는 패턴의 부분을 사용하고 저장소에서 기사 목록을 검토하여 기존 이름을 확인합니다. 

## 예
<span style="color:red;"> **docs.microsoft.com/ems에서 이 섹션의 대체 예제 필요**  </span>

패턴을 따르는 유효한 이름의 몇 가지 예는 다음과 같습니다.

- cloud-services-dotnet-continuous-delivery.md
- mobile-services-ios-get-started.md
- documentdb-manage-account.md
- mobile-services-dotnet-backend-get-started-settings-sync.md
- active-directory-java-authenticate-users-access-control-eclipse.md
- virtual-machines-install-windows-server-2008r2.md

## 파일 이름 승인

새 파일이 저장소에 처음 제출되면 파일 이름을 검토하는 것은 끌어오기 요청 검토자 그룹이 담당합니다. 끌어오기 요청 검토자는 파일 이름을 검토하고 변경이 필요한 경우 피드백을 제공해야 합니다. 파일 이름을 정정해야 끌어오기 요청이 승인됩니다. 참가자는 보류 중인 끌어오기 요청에 대한 업데이트를 간단히 푸시할 수 있습니다.

## 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)


<!--Anchors-->
[Rules for naming files]: #rules
[File name patterns]: #pattern
[Examples]: #standard-examples
[File name approval]: #file-name-approval


<!--HONumber=Mar16_HO1-->


