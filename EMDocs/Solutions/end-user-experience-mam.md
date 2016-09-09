---
title: "MAM의 최종 사용자 환경"
description: "모바일 앱 관리 정책의 최종 사용자 환경입니다."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc9f6ea-fc92-468d-bb5b-60c67949ca28
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 3c1fa5aac308beb3710fa52ae99efa389a0d5465


---

# 모바일 앱 관리 정책의 최종 사용자 환경
MAM 정책은 앱이 회사 컨텍스트에서 사용되는 경우에만 적용됩니다. 관리되는 앱의 작동 방식을 파악할 수 있도록 사용자를 교육하려면 다음 예제 시나리오를 읽어보세요.

이 섹션에서는 다음 최종 사용자 환경의 예제를 제공합니다.

- 시나리오: iOS 장치에서 OneDrive 액세스
- 시나리오: Android 장치의 OneDrive 액세스

다른 특정 최종 사용자 환경에 대한 자세한 내용은 다음 문서를 참조하세요.

- [다중 ID가 지원되는 앱 사용](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support)
- [사용자 계정 관리](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts)
- [Rights Management 공유 앱을 사용하여 미디어 파일 보기](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)

## 시나리오: iOS 장치에서 OneDrive 액세스

1. 사용자가 **OneDrive** 앱을 시작하여 로그인 페이지를 엽니다.
> [!NOTE]
> 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다. 장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2. 사용자가 회사 계정 사용자 이름을 입력하고 회사 자격 증명을 입력하기 위한 **O365 인증** 페이지로 리디렉션됩니다.

  Azure AD에서 자격 증명을 성공적으로 인증하면 MAM 정책이 적용됩니다.
3. 앱의 **PIN**을 설정하라는 메시지가 표시됩니다(해당 정책을 구성한 경우).

4.  PIN이 설정되고 확인되면 **비즈니스용 OneDrive**에서 파일에 액세스할 수 있습니다.
> [!NOTE]
> 배포된 정책을 변경하는 경우 다음에 앱을 열 때 변경 내용이 적용됩니다.

## 시나리오: Android 장치의 OneDrive 액세스
1. 사용자가 **OneDrive** 앱을 시작하여 로그인 페이지를 엽니다.
> [!NOTE]
> 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다. 장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2.  사용자가 회사 계정 사용자 이름을 입력하고 회사 자격 증명을 입력하기 위한 **O365 인증** 페이지로 리디렉션됩니다.

  Azure AD에서 자격 증명을 성공적으로 인증하면 MAM 정책이 적용됩니다.

3.  **OneDrive** 앱이 자동으로 시작되고, 정책 설정이 **OneDrive** 앱 액세스 시 **PIN**을 요구하도록 설정된 경우 **PIN** 을 설정하라는 메시지가 표시됩니다.

4.  PIN이 설정 및 확인되고 나면 이제 앱 정책에 의해 관리되는 **OneDrive**를 계속 사용할 수 있습니다.

## 추가 정보
[다중 ID가 지원되는 앱 사용](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support), [사용자 계정 관리](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts) 및 [Rights Management 공유 앱을 사용하여 미디어 파일 보기](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)를 비롯하여 다른 최종 사용자 환경에 대해 읽어볼 수 있는 다양한 리소스가 있습니다.



<!--HONumber=Sep16_HO1-->


