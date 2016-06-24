<properties pageTitle="GitHub에 제작을 위한 도구 설치 및 설정" description="GitHub에서 EMS 콘텐츠를 제작하기 위해 설정한 도구 및 단계입니다." services="contributor-guide" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# GitHub에 제작을 위한 도구 설치 및 설정
이렇게 하려면:
- [ ] #21 전체 프로시저는 Microsoft가 아닌 계정 및 컴퓨터로 테스트해야 합니다. 

이 문서의 단계를 수행하여 EMS 기술 문서에 기여하는 도구를 설정합니다. 

- Git에 익숙하지 않은 경우 몇 가지 Git 용어를 검토하려고 할 수 있습니다. [https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary)
- 또한 [Git 및 Github 기초](https://www.youtube.com/playlist?list=PLg7s6cbtAD15G8lNyoaYDuKZSKyJrgwB-)에 대한 일련의 비디오를 추천합니다. 신속하고 따라하기 쉽습니다.  

## 단계별 지침

- [GitHub 계정을 만들기 및 프로필 설정](#create-a-github-account-and-set-up-your-profile)
- [GitHub의 사용 권한](#permissions-in-github)
- [Windows용 Git 설치](#install-git-for-windows)
- [2단계 인증 사용](#enable-two-factor-authentication)
- [개인 액세스 토큰 만들기](#create-a-personal-access-token)
- [마크다운 편집기 설치](#install-a-markdown-editor)
- [Atom 구성](#configure-atom)
- [저장소에서 분기 만들기](#create-a-branch-from-the-repository)
- [원격 리포지토리 연결 설정 및 자격 증명 구성](#set-remote-repository-connection-and-configure-credentials)
- [사용자 이름 및 전자 메일을 로컬로 구성](#configure-your-user-name-and-email-locally)
- [다음 단계](#next-steps)

## GitHub 계정을 만들기 및 프로필 설정

EMS 기술적 내용에 참여하려면 [GitHub](http://www.github.com) 계정이 필요합니다.

- **프로필 사진**: 사용자의 사진(필수)
- **이름**: 이름 및 성(필수)
- **전자 메일**: 전자 메일 주소(필수)
- **회사**: 회사(필수)
- **위치**: 사용자의 위치 나열(필수)

프로필은 다음 프로필과 유사해야 합니다.

 ![GitHub 프로필 예제](./media/githubprofile.png)

## GitHub의 사용 권한

GitHub 계정이 있는 모든 사용자는 [http://www.github.com/microsoft/emdocs](http://www.github.com/microsoft/emdocs)의 공용 리포지토리를 통해 EMS 기술적 내용에 참여할 수 있습니다. 특별한 권한이 필요하지 않습니다.

## Windows용 Git 설치

[http://git-scm.com/download/win](http://git-scm.com/download/win)에서 **Windows용 Git**를 설치합니다. 이 다운로드는 Git 버전 제어 시스템을 설치하고 이는 Git Bash, 로컬 Git 리포지토리와 상호 작용하는 데 사용하는 명령줄 앱을 설치합니다.

**참고**
이 프로그램은 "Windows용 Github"과 동일하지 않습니다. "Windows용 Github"는 사용자가 직접 읽으려는 경우 작동하는 다른 GUI 기반 도구입니다. [https://windows.github.com/](https://windows.github.com/)) 

설치하는 동안 Github 리포지토리와 상호 작용하는 방법을 선택하도록 합니다. Git Bash에서 Git를 사용하는 것이 좋습니다. 
 ![GitHub 프로필 예제](./media/gitbashinstall.png)

## 2단계 인증 사용

개인 콘텐츠 리포지토리에서 작업하는 경우 GitHub 계정에 2FA(2단계 인증)를 사용하도록 설정해야 합니다. 이 기능을 사용하려면 다음 GitHub 도움말 항목의 지침을 따릅니다.

- [2단계 인증 사용 정보](https://help.github.com/articles/about-two-factor-authentication/)

## 개인 액세스 토큰 만들기
개인 액세스 토큰은 GitHub에서 작업하는 사용자와 컴퓨터를 인증합니다.
1. GitHub에서 직접 클릭한 다음 설정을 클릭합니다.
2. 개인 액세스 토큰 탭에서 새 토큰 생성을 클릭합니다.
3. 토큰을 대한 설명을 제공합니다. 
4. 범위를 설정합니다. 해당 권한 확인란을 선택하여 리포지토리 및 사용자에 대한 전체 액세스 권한을 보유하려 합니다.
5. 토큰 생성을 클릭합니다.
6. 표시된 토큰을 복사하고 전자 메일 또는 Word 문서와 같은 안전한 곳에 붙여 넣습니다. 이 토큰을 끌어오고 GitHub에 푸시해야 합니다.

## 마크다운 편집기 설치

복잡한 "마크업"(HTML, XML 등) 대신 파일에서 간단한 "마크다운" 표기법을 사용하는 콘텐츠를 작성합니다. 따라서 마크다운 편집기를 설치해야 합니다. GitHub 지원 마크다운을 사용합니다. 

- **Atom**: 참가자는 GitHub의 Atom 마크다운 편집기를 사용합니다. [http://atom.io](http://atom.io) 비즈니스 사용을 위해 라이선스를 요구하지 않고 맞춤법을 검사합니다. 
- **메모장**: 아주 간단한 옵션에 메모장을 사용할 수 있습니다.
- **문체**: 미리 보기를 제공하는 경량의 세련된 온라인 오픈 소스 마크다운 편집기입니다. [http://prose.io](http://prose.io)를 방문하고 리포지토리의 문체 권한을 부여합니다.
- **[Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)** - 이 공간에 있는 Microsoft의 항목입니다.
- **MarkdownPad 2**: 무료로 [MarkdownPad 2](http://markdownpad.com/)를 사용할 수 있지만 라이선스를 구입하는 경우 라이브 미리 보기에서 Github을 선호하는 마크다운 렌더링을 활용할 수 있습니다.  

## Atom 마크다운 편집기 구성

Atom을 사용할 경우 몇 가지를 설정해야 합니다.

- Atom은 기본적으로 탭에 2개의 공백이 설정되지만 마크다운에는 4개의 공백이 필요합니다. 둘의 기본값을 놔두면 문서는 로컬 미리 보기 상태에서는 훌륭해 보이지만 docs.microsoft.com로 가져올 때는 그렇지 않습니다. 따라서 4개의 공백을 사용하도록 Atom을 구성합니다. 이 설정은 파일->설정->편집기 설정->탭 길이에서 찾을 수 있습니다. 
- 이 섹션에서 Soft Wrap을 설정하려고 할 수 있으며 이는 메모장에서 "자동 줄 바꿈"과 동일합니다. 
- 마크다운 미리 보기를 설정하려면 패키지->마크다운 미리 보기->미리 보기 설정/해제를 클릭합니다. 미리 보기 HTML 뷰를 설정/해제하려면 Ctrl-Shift-M을 사용할 수 있습니다. 

## 저장소에서 분기 만들기

GitHub의 저장소에서 분기 만들기 

1. Git Bash를 엽니다. 
2. 명령 프롬프트에서 다음 명령을 입력합니다. 

        git clone https://[your GitHub user name]:[token]@github.com/microsoft/emdocs.git

이 명령은 사용자의 컴퓨터에서 `emdocs` 디렉터리를 만듭니다.  기본 위치를 사용하는 경우 `c:\users\<your Windows user name>\emdocs`에 배치됩니다. 예를 들어 이 복제 명령은 다음과 같아 보입니다.

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/microsoft/emdocs.git  

## 원격 리포지토리 연결 설정 및 자격 증명 구성

Git를 구성하여 `push` 또는 `pull` 동작에 해당 액세스 토큰을 수동으로 입력하거나 붙여 넣을 필요가 없도록 기본적으로 GitHub ID 및 개인 액세스 토큰을 사용합니다. 

Git Bash에서 다음 명령을 실행합니다.

        cd emdocs
        git remote –v 
        git remote remove origin
        git remote add origin http://<githubID>:<token>@github.com/microsoft/emdocs
        git remote -v

일반적으로 시간이 오래 걸립니다. 이 작업을 수행한 후에 자격 증명을 다시 입력할 필요가 없습니다. 다른 컴퓨터에서 도구를 설정하는 경우 프로세스를 다시 반복하기만 하면 됩니다.

## 사용자 이름 및 전자 메일을 로컬로 구성

참가자로 올바르게 나열되도록 하려면 Git에서 사용자 이름 및 전자 메일을 로컬로 구성해야 합니다.

1. Git Bash 시작 및 emdocs로 전환
   ````
   cd emdocs
   ````
2. GitHub 프로필에서 설정한 이름과 일치하도록 사용자 이름을 구성합니다.

    ````
    git config --global user.name "John Doe"
    ````
3. GitHub 프로필에 지정된 기본 전자 메일과 일치하도록 전자 메일을 구성합니다.

    ````
    git config --global user.email "alias@example.com"
    ````
4. `git config -l`을 입력하고 로컬 설정을 검토하여 구성에서 사용자 이름 및 전자 메일이 올바른지 확인합니다.

## 다음 단계

- 작성을 시작할 수 있도록 [Git 작업](./work-with-git.md)의 지침을 읽고 따릅니다.


## 홈으로 돌아가기

- [개요 문서](./../README.md)
- [지침 문서 인덱스](./contributor-guide-index.md)


<!--Anchors-->
[Create a GitHub account and set up your profile]: #create-a-github-account-and-set-up-your-profile
[Permissions in GitHub]: #permissions-in-github
[Install Git for Windows]: #install-git-for-windows
[Enable two-factor authentication]: #enable-two-factor-authentication
[Create a personal access token]: #create-a-personal-access-token
[Install a markdown editor]: #install-a-markdown-editor
[Configure Atom]:#configure-atom
[Create a branch from the repository]: #create-a-branch-from-the-repository
[Set remote repository connection and configure credentials]: #set-remote-repository-connection-and-configure-credentials
[Configure your user name and email locally]: #configure-your-user-name-and-email-locally
[Next steps]: #next-steps

<!--HONumber=Mar16_HO1-->


