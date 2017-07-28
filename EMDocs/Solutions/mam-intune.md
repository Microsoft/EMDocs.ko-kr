---
title: "Intune에서 모바일 앱 관리 정책 사용"
description: "Intune에서 모바일 앱 관리 정책을 사용하여 앱을 만들고 배포합니다."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d7c4104-b85f-407e-8832-0e6bbac934f5
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 418aa02b98040a8a74313513f05b231a20ea472a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="use-mobile-app-management-policies-in-intune"></a>Intune에서 모바일 앱 관리 정책 사용
많은 회사에서 Microsoft Intune을 사용하는 주된 이유 중 하나는 사용자가 작업을 완료하는 데 필요한 앱을 배포하기 위해서입니다. 앱을 배포하려면 먼저 [장치를 관리하도록 설정](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)해야 합니다.

예를 들어 회사에서 Microsoft Word를 사용하는 경우 Windows, iOS, Android 등에 사용 가능한 여러 버전이 있습니다. 이러한 경우 IT 관리자는 사용 가능한 여러 앱을 다양한 장치와 컴퓨터 플랫폼에서 관리하여 회사 데이터의 보안을 유지하면서 사용자가 작업을 수행할 수 있도록 해야 합니다.

구성 관리자에서 Intune을 사용하는 경우 [Configuration Manager에서 모바일 응용 프로그램 관리 정책을 사용하여 앱을 제어하는 방법](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396) 항목을 참조하세요.

MAM(모바일 앱 관리) 정책에서는 다음을 지원합니다.
- Android 4 이상을 실행하는 장치
- iOS 7 이상을 실행하는 장치

> [!NOTE]
> MAM 정책에서는 Intune으로 등록된 장치를 지원합니다. Intune에서 관리되지 않는 장치의 앱 관리 정책을 만드는 방법에 대한 자세한 내용은 [Microsoft Intune으로 모바일 앱 관리 정책을 사용하여 앱 데이터 보호](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) 항목을 참조하세요.

다른 Intune 정책과 달리 MAM 정책은 직접 배포하지 않습니다. 대신 제한할 앱에 해당 정책을 연결합니다. 장치에서 앱을 배포하고 설치하면 지정한 설정이 적용됩니다.

앱에 제한을 적용하려면 Microsoft Intune 앱 SDK(소프트웨어 개발 키트)를 통합해야 합니다. 이러한 유형의 앱은 두 가지 방법으로 얻을 수 있습니다.

- **정책 관리된 앱 사용** – 앱 SDK가 기본으로 제공됩니다. 이 유형의 앱을 추가하려면 iTunes 스토어, Google Play 등의 앱 스토어에 있는 앱의 링크를 지정합니다. 이러한 앱 유형은 추가로 처리할 필요가 없습니다. 지원되는 Microsoft 앱의 전체 목록을 보려면 Microsoft Intune 응용 프로그램 파트너 페이지의 [Microsoft Intune 모바일 응용 프로그램 갤러리](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)로 이동합니다. 앱을 클릭하여 지원되는 시나리오, 플랫폼 및 앱에서 다중 ID를 지원하는지 여부를 확인합니다.
- **'래핑된' 앱 사용** - Microsoft Intune 앱 래핑 도구를 사용하여 앱 SDK를 포함하도록 다시 패키지된 앱입니다. 이 도구는 일반적으로 사내에서 작성된 회사 앱을 처리하는 데 사용되며, 앱 스토어에서 다운로드한 앱을 처리하는 데 사용할 수는 없습니다. 참조:
  - [Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
  - [Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

iOS 및 Android용 Outlook 등과 같은 일부 관리 앱은 **다중 ID**를 지원합니다. 즉, Intune은 회사 계정 또는 앱의 데이터에만 관리 설정을 적용합니다.

예: Outlook 앱 사용:
- 사용자가 회사 및 개인 전자 메일 계정을 구성하는 경우, Intune에서는 회사 계정에만 관리 설정을 적용하고 개인 계정은 관리하지 않습니다.
- 장치가 사용되지 않거나 등록되지 않은 경우 회사 Outlook 데이터가 장치에서 제거됩니다.
- 사용한 회사 계정은 Intune으로 장치를 등록하는 데 사용한 계정과 같아야 합니다.

Word, Excel 및 PowerPoint는 OneDrive 또는 SharePoint와 같은 서비스에서 회사를 식별할 수 있는 데이터를 관리 및 편집하는 경우에만 정책 제한이 적용된다는 점을 제외하고 다중 ID도 지원합니다.

## <a name="create-and-deploy-an-app-in-intune-with-a-mobile-app-management-policy"></a>Intune에서 모바일 앱 관리 정책을 사용하여 앱 만들기 및 배포

- 1단계: 정책으로 관리되는 앱의 링크를 가져오거나 래핑된 앱을 만듭니다.
- 2단계: 클라우드 저장소 공간에 앱을 게시합니다.
- 3단계: 모바일 앱 관리 정책을 만듭니다.
- 4단계: 모바일 앱 관리 정책에 앱을 연결하는 옵션을 선택하여 앱을 배포합니다.
- 5단계: 앱 배포 모니터링

### <a name="step-1-obtain-the-link-to-a-policy-managed-app-or-create-a-wrapped-app"></a>1단계: 정책으로 관리되는 앱의 링크를 가져오거나 래핑된 앱 만들기
- **정책으로 관리되는 앱의 링크를 가져오려면** - 배포하려는 정책으로 관리되는 앱의 URL을 앱 스토어에서 찾아서 적어 둡니다.
예를 들어 iPad용 Microsoft Word 앱의 URL은 [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)입니다.
- **래핑된 앱을 만들려면** - [Microsoft Intune 앱 래핑 도구를 사용한 모바일 응용 프로그램 관리를 위해 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 및 [Microsoft Intune 앱 래핑 도구를 사용한 모바일 응용 프로그램 관리를 위해 Android 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) 항목의 정보를 사용하여 래핑된 앱을 만듭니다. 이 도구는 클라우드 저장 공간에 응용 프로그램을 게시할 때 사용할 처리된 앱을 만듭니다.

### <a name="step-2-upload-the-app-to-your-cloud-storage-space"></a>2단계: 클라우드 저장소 공간에 앱 업로드
관리되는 앱을 게시하는 절차는 정책으로 관리되는 앱을 게시하는지 아니면 iOS용 Microsoft Intune 앱 래핑 도구를 사용하여 처리한 앱을 게시하는지에 따라 달라집니다.

클라우드 저장소 공간에 앱을 업로드하는 데 필요한 전체 단계에 대해서는 [Microsoft Intune에서 모바일 장치용 앱 추가](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune#add-the-app)를 참조하세요.

### <a name="step-3-create-a-mobile-app-management-policy"></a>3단계: 모바일 앱 관리 정책 만들기
Azure 포털은 MAM 정책을 만들기 위한 권장 관리 콘솔입니다. Azure 포털에서는 다음 MAM 시나리오를 지원합니다.
- Intune에서 등록된 장치
- 타사 MDM 솔루션에서 관리되는 장치
- MDM 솔루션(BYOD)에서 관리되지 않는 장치

Azure 포털을 사용하여 MAM 정책을 관리하는 방법에 대한 자세한 내용은 [Microsoft Intune으로 모바일 앱 관리 정책 만들기 및 배포](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)를 참조하세요.

현재 [Intune 관리 콘솔](https://docs.microsoft.com/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console#-step-3-create-a-mobile-application-management-policy)을 사용하여 장치를 관리하는 경우 Intune 관리 콘솔을 사용하여 Intune에 등록된 장치의 앱을 지원하는 MAM 정책을 만들 수 있습니다.


### <a name="step-4-deploy-the-app-selecting-the-option-to-associate-the-app-with-a-mobile-application-management-policy"></a>4단계: 모바일 응용 프로그램 관리 정책에 앱을 연결하는 옵션을 선택하여 앱을 배포합니다.
Azure 포털을 사용하는 경우 [사용자에게 MAM 정책을 배포](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune#deploy-a-policy-to-users)합니다.

Intune 포털을 사용하는 경우 [앱을 배포하고](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune#deploy-an-app) 모바일 앱 관리 페이지에서 모바일 앱 관리 정책을 선택하여 해당 정책이 앱에 연결되었는지 확인합니다.

Intune에서 장치 등록을 취소해도 정책은 앱에서 제거되지 않으며, 정책이 적용되었던 앱은 제거했다가 다시 설치해도 정책 설정이 그대로 유지됩니다.

#### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>앱을 장치에 이미 배포한 경우 수행할 작업

앱을 배포할 때 대상 사용자 또는 장치 중 하나에 관리되지 않는 버전의 앱이 이미 설치되어 있는 경우가 있습니다. 사용자가 앱 스토어에서 Microsoft Word를 설치한 경우 등을 예로 들 수 있습니다.

이 경우에는 구성한 관리 버전을 설치할 수 있도록 사용자에게 관리되지 않는 버전을 수동으로 제거하도록 요청해야 합니다.

그러나 iOS 9 이상을 실행하는 장치의 경우 Intune에서는 기존 앱 관리를 수행할 권한을 제공할 것인지를 사용자에게 묻는 메시지를 자동으로 표시합니다. 사용자가 권한 제공에 동의하면 앱은 Intune에서 관리되며, 해당 앱과 연결한 MAM 정책도 적용됩니다.


### <a name="step-5-monitor-the-app-deployment-with-mam-policy"></a>5단계: MAM 정책을 사용하여 앱 배포 모니터링
Intune 콘솔을 통해 앱 배포를 모니터링하고 정책 충돌을 해결하려면 다음 절차를 따르세요.

1. [Microsoft Intune 관리 콘솔](https://manage.microsoft.com/)에서 **그룹**을 클릭합니다.
2. 다음 단계 중 하나를 수행합니다.
  -  **모든 사용자**를 클릭한 다음 검사할 장치의 사용자를 두 번 클릭합니다. 사용자 속성 페이지에서 **장치**를 클릭하고 검사할 장치를 두 번 클릭합니다.
  -  **모든 장치 > 모든 모바일 장치**를 클릭합니다. 장치 그룹 속성 페이지에서 **장치**를 클릭하고 검사할 장치를 두 번 클릭합니다.
3. 모바일 장치 속성 페이지에서 **정책**을 클릭하여 장치에 배포된 MAM 정책의 목록을 표시합니다.
4. 상태를 보려는 MAM 정책을 선택합니다. 아래쪽 창에서 정책의 세부 정보를 보고 해당 노드를 확장하여 정책의 설정을 표시할 수 있습니다.
5.  MAM 정책의 상태 열에는 준수, 준수(보류 중) 또는 오류가 표시됩니다. 선택한 정책에서 하나 이상의 설정이 충돌하면 이 필드에 오류가 표시됩니다.
6.  충돌이 확인되면 충돌하는 정책 설정이 같은 설정을 사용하도록 수정하거나 앱과 사용자에 대한 하나의 정책만을 배포할 수 있습니다.

> [!NOTE]
> [Azure 포털](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune)을 통해 또는 [Intune 콘솔](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune)을 사용하여 앱을 모니터링하는 방법에 대한 추가 정보를 자세히 알아보세요.

## <a name="where-to-go-from-here"></a>추가 정보

MAM 정책과 관련된 앱을 만들고 배포한 후에는 [MAM의 최종 사용자 환경](end-user-experience-mam.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 발생할 수 있는 모든 문제에 대비하는 데 도움이 됩니다.
