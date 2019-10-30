---
title: IT 관리자를 위한 최종 사용자 Intune 등록 지침
description: IT 관리자를 위한 최종 사용자 Intune 등록 지침
keywords: ''
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 5c13446e-aa31-47df-ad9d-373be7660197
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 2b9f32d79ab00c55962df67cab9bc2bad9549c44
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196817"
---
# <a name="end-user-intune-enrollment-instructions-for-it-administrators"></a>IT 관리자를 위한 최종 사용자 Intune 등록 지침

이 문서에는 Microsoft Intune™에서 iOS 및 Android 디바이스를 등록하는 데 도움이 되도록 사용자에게 사용자 지정하여 제공할 수 있는 등록 지침이 포함되어 있습니다(Windows 디바이스의 경우 [Intune에서 Windows 디바이스 사용 참조](/intune-user-help/using-your-windows-device-with-intune)). 사용자에게 가장 적합하다고 생각되는 이 문서의 부분을 복사하는 것이 좋습니다. 예를 들어 각 디바이스 플랫폼을 위한 단일 문서를 생성하거나 더 많은 스크린샷을 추가할 수 있습니다.

이러한 작성된 지침 외에 Intune 최종 사용자 동영상([https://channel9.msdn.com/Series/IntuneEnrollment](https://channel9.msdn.com/Series/IntuneEnrollment)에 있음)의 하이퍼링크를 포함할 수도 있습니다.

> [!NOTE]
> Microsoft, Intune 및 Office 365는 Microsoft Corporation의 등록 상표입니다. iPhone, Mac 및 Apple은 Apple의 상표 이며, i n c. Android는 Google i n c .의 상표입니다. Samsung KNOX는 Samsung 전자식 Co의 상표입니다.

## <a name="why-enroll-in-intune"></a>Intune에서 등록하는 이유
등록할 때 모바일 디바이스를 사용하여 회사 또는 학교 파일 및 데이터에 액세스할 수 있습니다. 또한 선호하는 디바이스를 자유롭게 사용하여 작업을 완료하는 동안 IT 부서에서 해당 회사 또는 학교 리소스를 관리하고 보안을 유지할 수 있습니다.

회사에서 디바이스를 사용하려면 회사 포털을 사용하여 Intune에서 디바이스를 등록합니다. 그런 다음 손쉽게 설치할 회사 앱을 찾고, 사용자가 추가한 다른 디바이스를 확인하며, IT 관리자의 연락처 정보를 찾을 수 있습니다. 회사 포털에 디바이스를 추가하면 IT 관리자가 디바이스의 회사 정보를 보호하기 위해 사용자의 디바이스를 관리할 수 있는 권한도 부여하는 것입니다. 등록을 시작하기 전에 Wi-Fi 또는 셀룰러와 인터넷의 연결 상태가 양호한지 확인합니다.

## <a name="enroll-your-android-device-in-intune-using-the-intune-company-portal-app"></a>Intune 회사 포털 앱을 사용하여 Intune에서 Android 디바이스 등록

이러한 등록 단계는 Samsung Knox Android 디바이스와 "네이티브"(Samsung Knox가 아닌) Android 디바이스에 대한 것입니다. Samsung Knox 디바이스가 있는지 확인하려면 **설정 &gt; 휴대폰 정보**로 이동합니다. 여기에 나열된 "Knox"라는 단어가 보이지 않으면 네이티브 Android 디바이스가 있어야 합니다. 디바이스에 표시된 화면은 이 섹션의 화면과 약간 다르게 보일 수 있습니다.

Intune에서 디바이스를 등록하는 동안 오류가 발생할 경우 [IT 관리자에게 등록 오류 보내기](https://technet.microsoft.com/library/mt502762(TechNet.10).aspx#BKMK_andr_send_enroll_errors)를 참조하세요.

등록하기 전이나 이후에 디바이스 사용 방법을 가장 잘 설명하는 범주를 선택하라는 메시지가 표시될 수도 있습니다. IT 관리자는 이 범주를 사용하여 액세스할 수 있는 앱을 확인합니다.
1. [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)에서 디바이스에 무료 Microsoft Intune 회사 포털 앱을 설치합니다.
2. Microsoft Intune 회사 포털 앱을 엽니다.
3. 회사 포털의 **시작** 화면에서 **로그인**을 탭한 다음, 회사 또는 학교 계정으로 로그인합니다.

   ![Android 디바이스의 Intune 회사 포털 로그인 화면을 보여 주는 스크린샷](./media/ft-userEnrollAndroid-1-signUp.png)

4. IT 관리자가 회사 사용 약관을 설정하는 경우 **동의함**을 탭하여 조건에 동의합니다.

   ![Android 디바이스에서 사용 약관에 동의하는지 묻는 스크린샷](./media/ft-userEnrollAndroid-2-accept.png)
5. Android 6.0 이상 디바이스를 사용하는 경우 이 단계를 수행하고 그러지 않으면 다음 단계로 이동합니다.

   IT 관리자가 특정 정책을 설정한 경우 다음과 같은 메시지 중 하나 또는 둘 다가 표시될 수 있습니다.

   - **회사 포털에 연락처에 대한 액세스를 허용할까요?** 메시지가 표시되면 **허용**을 탭합니다. Microsoft는 결코 연락처에 액세스하지 않으므로 허용을 탭하는 것이 안전합니다. Google이 메시지 텍스트를 제어하므로 Microsoft에서 변경할 수 없습니다. 액세스를 허용하는 경우 회사 포털 앱이 디바이스에 발생한 문제를 해결하기 위해 데이터 로그에 액세스할 수 있습니다.

       ![포털이 Android 디바이스의 연락처에 액세스할 수 있도록 허용할지 묻는 스크린샷](./media/ft-userEnrollAndroid-3-accessContacts.png)
   - **회사 포털에서 통화를 하고 전화 통화를 관리하도록 허용할까요?** 메시지가 표시되면 **허용**을 탭합니다. Microsoft는 결코 전화를 걸거나 전화 통화를 관리하지 않으므로 허용을 탭하는 것이 안전합니다. Google이 메시지 텍스트를 제어하므로 Microsoft에서 변경할 수 없습니다. 액세스를 허용할 경우 회사 포털 앱에서 전화 번호 및 IMEI라는 ID를 볼 수 있도록 허용하는 것뿐입니다.

       ![포털이 Android 디바이스의 통화를 관리할 수 있도록 허용할지 묻는 스크린샷](./media/ft-userEnrollAndroid-4-manageCalls.png)

   **거부**를 탭하면 다음에 회사 포털 앱에 로그인할 때 메시지가 다시 표시되지만, **다시 묻지 않음** 확인란을 탭하여 이후 메시지를 해제할 수 있습니다. 나중에 액세스를 허용하려는 경우 **설정 > 앱 > 회사 포털 > 사용 권한 > 전화**로 이동한 다음 사용 권한을 설정합니다.
6. 회사 또는 학교 계정과 암호를 사용하여 회사 포털 앱에 로그인하고 **로그인**을 탭합니다.

   ![Android 디바이스에서 회사 포털에 로그인할 것인지 묻는 스크린샷](./media/ft-userEnrollAndroid-5-signIn.png)
7. 회사 액세스 설정 페이지에서 **시작**을 탭합니다.

   ![Android 디바이스의 회사 액세스 설정 페이지를 보여 주는 스크린샷](./media/ft-userEnrollAndroid-6-beginSetup.png)
8. 디바이스를 등록할 때 수행할 수 있는 작업을 확인한 다음 **계속**을 탭합니다.

   ![Android 디바이스를 등록해야 하는 이유에 대한 정보를 보여 주는 스크린샷](./media/ft-userEnrollAndroid-7-whyEnroll.png)
9. IT 관리자가 등록된 디바이스에서 볼 수 있는 사항과 볼 수 없는 사항의 목록을 확인하고 **계속**을 탭합니다.

   ![Android 디바이스에서 개인 정보 취급 방침을 보여 주는 스크린샷](./media/ft-userEnrollAndroid-8-privacy.png)
10. 등록을 탭한 후 표시될 수 있는 사항 중 일부를 검토합니다. 읽기를 마쳤으면 **등록**을 탭합니다.

    ![Android 디바이스에서 향후 등록 단계를 보여 주는 스크린샷](./media/ft-userEnrollAndroid-9-whatNext.png)
11. 활성화 디바이스 관리자 화면에서 **성화**를 탭합니다.

    ![Android 디바이스에서 디바이스 관리자를 활성화할지 묻는 스크린샷](./media/ft-userEnrollAndroid-10-activateAdmin.png)
12. 지시에 따라 PIN이나 암호를 입력합니다. 이미 이 디바이스에서 암호나 PIN을 설정했다면 이 화면에 표시되지 않거나 새 PIN이나 암호를 입력할 필요가 없습니다.

    ![Android 디바이스에서 PIN을 입력하라는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollAndroid-11-enterPIN.png)
13. 사용 중인 디바이스의 형식(네이티브 Android 또는 Samsung Knox)과 일치하는 다음 지침에 따릅니다. Samsung Knox 디바이스가 없는 경우 네이티브 Android에 대한 지침을 따릅니다. Samsung Knox 디바이스가 있는지 확인하려면 **설정 &gt; 휴대폰 정보**로 이동합니다. 여기에 나열된 "Knox"라는 단어가 보이지 않으면 네이티브 Android 디바이스가 있어야 합니다.
    - 네이티브(Samsung Knox가 아닌) 디바이스: **Name the certificate**(인증서 이름 지정) 화면에서 **확인**을 탭하여 기본 인증서를 적용합니다.

        ![사용자에게 기본 Android 디바이스에서 기본 인증서를 수락하라는 메시지를 표시하는 스크린샷](./media/ft-userEnrollAndroid-12-android.png)
    - Samsung Knox 디바이스: **확인**을 탭합니다.

        ![사용자에게 Samsung Knox 디바이스에 대한 개인정보처리방침을 확인하라는 메시지를 표시하는 스크린샷](./media/ft-userEnrollAndroid-13-knox.png)

    Intune에서 디바이스를 등록하는 것처럼 화면에 다음과 같은 메시지가 표시됩니다.

    ![Android 디바이스가 등록되고 있음을 보여 주는 스크린샷](./media/ft-userEnrollAndroid-14-enrollingDevice.png)
14. **회사 액세스 설정** 화면에서 **계속**을 탭합니다. IT 관리자가 추가 보안 요구 사항(예: 암호를 설정해야 함)을 설정한 경우 화면상의 지침을 따른 다음 회사 액세스 설정 화면으로 돌아갈 때까지 **계속**을 탭합니다.

    ![Android 디바이스가 준수 상태임을 보여 주고 계속할 것인지 묻는 스크린샷](./media/ft-userEnrollAndroid-15-coAccessSetup.png)
15. **완료**를 탭합니다.

    ![Android 디바이스에서 회사 액세스 설정이 완료되었음을 보여 주는 스크린샷](./media/ft-userEnrollAndroid-16-SetupComplete.png)
16. 이제 Intune에 디바이스를 등록했으므로 회사 포털 앱으로 다시 이동합니다.
17. 회사 앱을 설치하기 전에 **설정 > 보안**으로 이동하고 **알 수 없는 소스**를 설정합니다. 앱을 설치하기 전에 이 옵션을 설정하지 않으면 "설치가 차단되었습니다. 보안상의 이유로 휴대폰이 알 수 없는 소스에서 가져온 앱의 설치를 차단하도록 설정되었습니다."라는 메시지가 표시됩니다. 오류 대화 상자에서 **설정**을 탭하여 **알 수 없는 소스** 옵션으로 이동할 수 있습니다.

## <a name="enroll-your-ios-device-in-intune"></a>Intune에서 iOS 디바이스 등록
다음 지침에 따라 Intune에서 iOS 디바이스를 등록합니다. 등록에 대한 자세한 내용은 [Intune에서 회사 포털 앱을 설치하고 디바이스를 등록하면 어떻게 되나요?](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_what_happ_enroll)를 참조하세요. Intune에서 디바이스를 등록하는 동안 오류가 발생할 경우 [IT 관리자에게 등록 오류 보내기](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_error_enrolling_tbl)를 참조하세요.

등록하기 전이나 이후에 디바이스 사용 방법을 가장 잘 설명하는 범주를 선택하라는 메시지가 표시될 수도 있습니다. IT 관리자는 이 범주를 사용하여 액세스할 수 있는 앱을 확인합니다.
1. 앱 스토어에서 디바이스에 무료 Microsoft Intune 회사 포털 앱을 설치합니다.
2. Microsoft Intune 회사 포털 앱을 엽니다.
3. 회사 포털의 **시작** 화면에서 **로그인**을 탭한 다음, 회사 또는 학교 계정으로 로그인합니다.

   ![iOS 디바이스의 Intune 회사 포털 로그인 화면을 보여 주는 스크린샷](./media/ft-userEnrollIOS-1-signUp.png)
4. IT 관리자가 회사 사용 약관을 설정한 경우 **동의함**을 탭하여 조건에 동의합니다.
5. 회사 액세스 설정 페이지에서 **시작**을 탭합니다.

   ![iOS 디바이스에서 등록 프로세스를 시작하라는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollIOS-2-coAccessSetup.png)
6. 디바이스를 등록할 때 수행할 수 있는 작업을 확인한 다음 **계속**을 탭합니다.

   ![iOS 디바이스를 등록해야 하는 이유에 대한 정보를 보여 주는 스크린샷](./media/ft-userEnrollIOS-3-whyEnroll.png)
7. IT 관리자가 등록된 디바이스에서 볼 수 있는 사항과 볼 수 없는 사항의 목록을 확인하고 **계속**을 탭합니다.

   ![iOS 디바이스에서 개인 정보 취급 방침을 보여 주는 스크린샷](./media/ft-userEnrollIOS-4-privacy.png)
8. 등록을 탭한 후 표시될 수 있는 사항 중 일부를 검토합니다. 읽기를 마쳤으면 **등록**을 탭합니다.

   ![iOS 디바이스에서 향후 등록 단계를 보여 주는 스크린샷](./media/ft-userEnrollIOS-5-whatNext.png)
9. 프로필 설치 화면에서 **설치**를 탭하고 메시지가 표시되면 암호를 입력합니다.

   ![iOS 디바이스에 대한 관리 프로필을 설치할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollIOS-6-installProfile.png)
10. **설치**를 탭합니다.

    ![iOS 디바이스에서 프로필을 설치하려면 설치 단추를 탭하라는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollIOS-7-tapInstall.png)
11. **설치**를 탭하여 경고를 읽었음을 나타냅니다.

    ![iOS 디바이스에서 프로필 관리 경고를 읽었는지를 나타내라는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollIOS-8-readWarning.png)
12. **신뢰**를 탭합니다.

    ![iOS 디바이스에서 프로필의 소스를 확인할 것인지 묻는 스크린샷](./media/ft-userEnrollIOS-9-tapTrust.png)
13. 프로필 설치를 완료했다고 표시하도록 화면이 변경되면 **완료**를 탭합니다. 화면에는 "등록 디바이스" 메시지가 표시됩니다.

    ![iOS 디바이스에 프로필이 설치되었음을 보여 주는 스크린샷](./media/ft-userEnrollIOS-10-profileInstalled.png)
14. 회사 포털에서 페이지를 열려는지를 묻는 메시지가 표시되는 경우 **열기**를 탭합니다.

    ![iOS 디바이스에서 회사 포털에서 페이지를 열 것인지 묻는 스크린샷](./media/ft-userEnrollIOS-11-openPage.png)
15. 회사 액세스 설정 화면에서 **계속**을 탭합니다. IT 관리자가 추가 보안 요구 사항(예: 암호를 설정해야 함)을 설정한 경우 모든 준수 요구 사항을 만족할 때까지 화면상의 지침을 따른 다음 회사 액세스 설정 화면으로 돌아오면 **계속**을 탭합니다.

    ![iOS 디바이스가 준수 상태임을 보여 주고 계속할 것인지 묻는 스크린샷](./media/ft-userEnrollIOS-12-coAccessSetup.png)
16. **완료**를 탭합니다.

    ![iOS 디바이스에서 회사 액세스 설정이 완료되었음을 보여 주는 스크린샷](./media/ft-userEnrollIOS-13-setupComplete.png)

이제 Intune에 디바이스를 등록했으므로 회사 포털 앱으로 다시 이동합니다.

## <a name="enroll-your-mac-os-x-device-in-intune"></a>Intune에서 Mac OS X 디바이스 등록
1. Safari 브라우저를 사용하여 [회사 포털 웹 사이트](https://portal.manage.microsoft.com/)를 열고 알림 표시줄을 탭합니다.
2. **이 디바이스는 등록되지 않았거나 회사 포털에서 해당 디바이스를 식별할 수 없습니다.** 를 탭합니다.

   ![회사 포털에서 Mac OS X 디바이스를 식별할 수 없음을 보여 주는 스크린샷](./media/ft-userEnrollMacOSx-1-enrollBegin.png)
3. **설치**를 탭하여 디바이스 등록을 시작합니다.

   ![Mac OS X 디바이스를 등록할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollMacOSx-2-enrollDevice.png)
4. 관리 프로필 설치 대화 상자에서 **설치**를 탭합니다. 자격 증명을 입력하라는 대화 상자가 나타나면 사용자 이름 및 암호를 입력한 다음 **계속 > 설치**를 탭합니다.

   ![Mac OS X 디바이스에서 관리 프로필을 설치할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-userEnrollMacOSx-3-installProfile.png)

등록이 끝나면 프로필이 확인되었음을 보여 주는 관리 프로필 페이지가 표시됩니다.

  ![Mac OS X 디바이스에서 관리 프로필이 확인되었음을 보여 주는 스크린샷](./media/ft-userEnrollMacOSx-4-profileVerified.png)

### <a name="want-to-learn-more"></a>더 자세한 내용을 원하세요?
[Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 참조하세요.
