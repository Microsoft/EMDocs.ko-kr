<properties pageTitle="새 문서를 만들거나 기존 문서를 업데이트하는 Git 명령" description="Azure 기술적 내용 GitHub 리포지토리로 작업하기 위한 단계입니다." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Git 작업

이렇게 하려면:
- [ ] #22 완성된 문서에 대한 EMS URL 바꾸기(지침 마지막 참조)

## 표준 프로세스(분기에서 작업)
이 문서의 단계를 수행하여 Microsoft.com/ems의 기술 문서 섹션에 새 문서를 만들거나 기존 아티클을 업데이트할 수 있도록 컴퓨터에 로컬 작업 분기를 만듭니다.

1. Git Bash를 시작합니다. 

2. 리포지토리 `emdocs`에 대한 변경 사항은 다음과 같습니다.

        cd emdocs
        
3. 새 작업 분기를 만듭니다.

        git checkout <branchname>

4. 새 로컬 작업 분기를 만듭니다.

        git pull origin master:<branchname>

5. 새 문서를 만들거나 기존 아티클을 변경합니다. Atom(http://atom.io)을 Markdown 편집기(또는 원하는 다른 편집기)로 사용하여 새 마크다운 파일을 만들고 엽니다. 문서 및 이미지를 만들거나 수정한 후에 다음 단계로 이동합니다.

6. 만든 새 파일을 추가하고 커밋합니다.

        git add <path-to-file>
        git commit –m "<comment>"
        
   또는 수정한 특정 파일만 커밋하려면:

        git commit -a –m "<comment>"

7. 로컬 작업 분기를 만든 것을 원본에 알립니다.

        git push origin <branchname>

8. GitHub의 해당 분기에 변경 내용을 푸시합니다.

        git push origin <branchname>

9. 스테이징, 유효성 검사 및/또는 게시하기 위한 마스터 분기에 내용을 제출할 준비가 되면 GitHub UI에 있는 분기에서 마스터 분기에 끌어오기 요청을 만듭니다.

10. 끌어오기 요청 수신자는 끌어오기 요청을 검토, 끌어오기 요청을 제공하며/하거나 끌어오기 요청을 수락합니다. 

11. 필요에 따라 
게시된 문서를 보기 위해 올바른 URL 필요에서 게시된 문서 또는 변경 내용을 확인합니다.
 http://docs.microsoft.com/ems/articles/name-of-your-article-without-the-MD-extension


<!--HONumber=Mar16_HO1-->


