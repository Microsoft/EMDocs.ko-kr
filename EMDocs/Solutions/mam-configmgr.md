---
title: "Configuration Manager에서 모바일 앱 관리 정책 사용"
description: "Configuration Manager에서 MAM(모바일 앱 관리) 정책을 사용하여 앱을 만들고 배포합니다."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 74288276-84d3-4d24-8307-7875491be9c9
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: 75ebd7a7bf49ce640dd8bb2914d6f9748c18db6b


---

# Configuration Manager에서 모바일 앱 관리 정책 사용
System Center 2012 Configuration Manager SP2부터 응용 프로그램 관리 정책을 사용하면 배포하는 앱의 기능을 회사의 규정 준수 및 보안 정책에 맞게 수정할 수 있습니다. 예를 들어 제한된 앱 내에서의 잘라내기/복사/붙여넣기 작업을 제한하거나 모든 웹 링크를 관리되는 브라우저 안에서 열도록 앱을 구성할 수 있습니다. 앱 관리 정책은 다음 장치를 지원합니다.

- Android 4 이상을 실행하는 장치
- iOS 7 이상을 실행하는 장치

> [!TIP]
> MAM(모바일 앱 관리) 정책은 관리되는 장치 외에 Intune으로 관리하지 않는 장치에 있는 앱을 보호하는 데에도 사용할 수 있습니다. 이 새 기능을 사용하여 Office 365 서비스에 연결하는 앱에 대해 모바일 앱 관리 정책을 적용할 수 있습니다. 온-프레미스 Exchange 또는 SharePoint에 연결하는 앱에 대해서는 지원되지 않습니다.
이 새 기능을 사용하려면 Azure 포털을 사용해야 합니다. 다음 항목은 시작하는 데 도움이 될 수 있습니다.
- [Microsoft Intune을 사용하여 모바일 앱 관리 정책 구성 준비](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
- [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

응용 프로그램 관리 정책은 Configuration Manager의 구성 항목 및 기준과 달리 직접 배포하지 않습니다. 대신 제한할 앱 DT(배포 유형)와 정책을 연결합니다. 장치에서 앱 DT를 배포하고 설치하면 지정한 설정이 적용됩니다.

앱에 제한을 적용하려면 Microsoft Intune 앱 SDK(소프트웨어 개발 키트)를 통합해야 합니다. 이러한 유형의 앱은 두 가지 방법으로 얻을 수 있습니다.

- **정책 관리 앱 사용**(Android 및 iOS): 앱 SDK가 기본으로 제공됩니다. 이 유형의 앱을 추가하려면 iTunes 스토어, Google Play 등의 앱 스토어에 있는 앱의 링크를 지정합니다. 이러한 앱 유형은 추가로 처리할 필요가 없습니다. iOS 및 Android 장치에 대해 사용 가능한 정책 관리 앱의 목록은 [Microsoft Intune 모바일 응용 프로그램 갤러리](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)를 참조하세요.
- **'래핑된' 앱 사용**(Android 및 iOS): Microsoft Intune 앱 래핑 도구를 사용하여 앱 SDK를 포함하도록 다시 패키지된 앱입니다. 이 도구는 일반적으로 사내에서 작성된 회사 앱을 처리하는 데 사용되며, 앱 스토어에서 다운로드한 앱을 처리하는 데 사용할 수는 없습니다. [Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 및 [Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 항목을 참조하세요.

## Configuration Manager에서 모바일 앱 관리 정책을 사용하여 앱 만들기 및 배포

- 1단계: 정책으로 관리되는 앱의 링크를 가져오거나 래핑된 앱을 만듭니다.
- 2단계: 앱이 포함된 Configuration Manager 응용 프로그램을 만듭니다.
- 3단계: 모바일 앱 관리 정책을 만듭니다.
- 4단계: 앱 관리 정책을 배포 유형과 연결합니다.
- 5단계: 앱 배포 모니터링

### 1단계: 정책으로 관리되는 앱의 링크를 가져오거나 래핑된 앱을 만듭니다.
- **정책으로 관리되는 앱의 링크를 가져오려면** - 배포하려는 정책으로 관리되는 앱의 URL을 앱 스토어에서 찾아서 적어 둡니다.
예를 들어 iPad용 Microsoft Word 앱의 URL은 [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)입니다.
- **래핑된 앱을 만들려면** - [Microsoft Intune 앱 래핑 도구를 사용한 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 및 [Microsoft Intune 앱 래핑 도구를 사용한 모바일 응용 프로그램 관리를 위해 Android 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 항목의 정보를 사용하여 래핑된 앱을 만듭니다. 이 도구는 처리된 앱 및 연결된 매니페스트 파일을 만듭니다. 앱을 포함하는 Configuration Manager 응용 프로그램을 만들 때 이러한 파일을 사용합니다.

### 2단계: 앱이 포함된 Configuration Manager 응용 프로그램을 만듭니다.
Configuration Manager 응용 프로그램을 만드는 절차는 정책 관리 앱(외부 링크)을 사용하는지 아니면 iOS용 Microsoft Intune 앱 래핑 도구(iOS용 앱 패키지)를 사용하여 만든 앱을 사용하는지에 따라 달라집니다.

앱이 포함된 Configuration Manager 응용 프로그램을 만드는 데 필요한 전체 단계를 보려면 [Configuration Manager에서 모바일 응용 프로그램 관리 정책을 사용하여 앱을 제어하는 방법](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step2)을 참조하세요.

응용 프로그램을 만들면 **소프트웨어 라이브러리** 작업 영역의 **응용 프로그램** 노드에 표시됩니다.

### 3단계: 모바일 응용 프로그램 관리 정책을 만듭니다.
다음으로는 응용 프로그램과 연결할 [응용 프로그램 관리 정책을 만듭니다](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#bkmk_step3). 일반 정책 또는 관리 브라우저 정책을 만들 수 있습니다.

새 정책을 만들면 **소프트웨어 라이브러리** 작업 영역의 **응용 프로그램 관리 정책** 노드에 표시됩니다.

### 4단계: 앱 관리 정책을 배포 유형과 연결합니다.
응용 프로그램 관리 정책이 필요한 앱에 대해 배포 유형을 만들면 Configuration Manager에서는 연결된 앱을 배포할 때 이 배포 유형에 앱 관리 정책을 연결해야 함을 인식하고 앱 관리 정책을 연결하라는 메시지를 표시합니다. 관리 브라우저의 경우에는 일반 정책과 관리 브라우저 정책을 모두 연결해야 합니다. 자세한 내용은 [Configuration Manager에서 모바일 장치용 응용 프로그램을 만들고 배포하는 방법](https://technet.microsoft.com/library/dn469410.aspx)을 참조하세요.

> [!TIP]
> iOS 7.1 이전 운영 체제를 실행하는 장치의 경우에는 앱을 제거해도 연결된 정책이 제거되지 않습니다.

> Configuration Manager에서 장치 등록을 취소해도 정책은 앱에서 제거되지 않습니다. 정책을 적용한 앱은 제거했다가 다시 설치하더라도 정책 설정을 그대로 유지합니다.


### 5단계: 앱 배포 모니터링
MAM 정책과 연결된 앱을 만들고 배포한 후에는 [앱을 모니터링하고 정책 충돌을 해결](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step5)할 수 있습니다.

응용 프로그램 모니터링에 대한 일반 정보를 보려면 [Configuration Manager에서 응용 프로그램을 모니터링하는 방법](https://technet.microsoft.com/library/gg682201.aspx)을 참조하세요.

## 추가 정보

MAM 정책과 관련된 앱을 만들고 배포한 후에는 [MAM의 최종 사용자 환경](end-user-experience-mam.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 발생할 수 있는 모든 문제에 대비하는 데 도움이 됩니다.



<!--HONumber=Aug16_HO1-->


