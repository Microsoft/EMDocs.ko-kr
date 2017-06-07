---
title: "Intune으로 BYOD를 사용하도록 설정 | Microsoft 문서"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d31eebe-81d2-4c6b-bfec-fbd536096dda
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: b4edb16e4ef00b7376af800ab542f42c0e530197
ms.openlocfilehash: 9defe28a74bc3e53f6ae5dc33b33396e47247265
ms.contentlocale: ko-kr
ms.lasthandoff: 02/13/2017


---
# <a name="enable-byod-with-intune"></a>Intune으로 BYOD를 사용하도록 설정
디지털 변환 지원은 점점 더 복잡해지는 오늘날의 모바일 환경에서 직원들의 생산성을 유지하면서도, 회사 데이터를 보호하기 위해 노력하고 있는 IT에 새로운 과제를 안기고 있습니다. 조직이 계속 클라우드로 전환하면서, 직원들은 이동 중에 소비자 환경과 대등한 다양한 장치 환경에서 생산성을 발휘할 것으로 예상하고 있습니다.

![복잡한 장치 환경에서의 선택 사항](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>이 인포그래픽은 https://gallery.technet.microsoft.com/Infographic-Management-3644ae41에서 다운로드할 수 있습니다.</sup>

이러한 장치 중 일부는 회사에서 관리되는 특정 사용자 전용 장치일 수 있으며, 여러 직원들이 하나의 장치를 공유할 수도 있습니다. 직원이 관리하는 장치도 있습니다. 이러한 개인 장치로는 매일 업무에 사용하는 자신의 iPhone이나 PC 또는 자녀의 iPad, 가족 컴퓨터 등과 같이 가끔 인터넷에 연결할 때 사용하는 포함 장치를 들 수 있습니다.

장치뿐 아니라 업무를 처리하는 장소도 변경되고 있습니다. 더 이상 기존 사무실이나 직장에서만 일하지 않습니다. 오늘날 직원은 집, 카페, 고객 사무실, 자동차에서뿐 아니라 이제 비행기에서도 일을 합니다. 따라서 현대 작업 공간에서는 BYOD(Bring Your Own Device) 프로그램이 흔하게 사용됩니다. 어떻게든 이런 혜택과 기회를 활용하여 직원 만족도를 높이고 비용을 줄이면서도, 회사 데이터에 대한 제어를 유지하는 일은 IT의 책임입니다.

BYOD 프로그램을 성공적으로 구현하면 프로세스를 더 복잡하게 만들거나 직원들의 작업 방식을 변경하지 않으면서, 더 엄격하게 제어하고 보안을 강화할 수 있습니다. 최종 사용자의 환경이 뛰어나면 최종 사용자가 제공되는 보호된 솔루션을 사용할 가능성은 커지고 감시망에서 벗어난 해결 방법을 만들어 작업을 수행할 가능성은 줄어듭니다.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>EMS(Enterprise Mobility + Security)는 사용자에게 어떻게 도움을 줄 수 있나요?

EMS로 어디서든 다양한 작업 스타일을 수용하는 생산적인 작업 공간을 만들기 위한 기능과 환경을 제공할 수 있습니다. 직원들이 iOS, MacOS, Android, Windows 장치 등 무엇을 사용하든, EMS의 일부인 Microsoft Intune을 통해 다양한 장치에서 직원 생산성을 향상하면서도 회사 데이터를 안전하게 보호할 수 있습니다. Intune에서는 장치 관리 사용 여부와 상관없이 회사 데이터를 보호할 수 있는 MAM 및 MDM 기능을 제공합니다. Intune은 포괄적인 모바일 장치 및 앱 수명 주기 관리를 제공할 뿐 아니라 Office 365 및 Office 모바일 앱과 직접 통합됩니다.

### <a name="recommended-solution"></a>권장 솔루션

Intune을 사용하여 회사 정보를 안전하게 유지하면서 직원들이 거의 어디에서 어떤 장치를 사용하든 회사 응용 프로그램, 데이터 및 리소스에 쉽게 액세스할 수 있도록 합니다. Office 365와의 직접 통합을 통해 뛰어난 최종 사용자 환경을 지원하고 Office 모바일 앱에 대한 포괄적인 데이터 손실 보호 기능과 Office 365에 대한 액세스 제어 기능을 제공합니다. 장치를 분실 또는 도난당하거나 장치가 더 이상 업무에 필요하지 않게 되는 경우 Intune에서는 BYOD 장치에서 회사 데이터만 선택적으로 초기화할 수 있습니다.

다음은 모바일 및 클라우드 중심의 환경에서, 생산성과 보호를 둘 다 충족해야 하는 필요성과 과제에 관해 실제 IT 전문가와 사용자의 이야기를 들어보는 짧은 동영상입니다.
<iframe width="675" height="480" src="https://www.youtube.com/embed/pgAmKnluwVw" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

이 솔루션의 나머지 부분은 다음을 수행하는 방법을 설명하는 다음과 같은 섹션으로 구분됩니다.

-   **장치 등록 및 준수 확인**. 이 섹션에서는 사용자가 장치(iOS, MacOS, Android, Android for Work 및 Windows)를 Intune의 관리 기능에 등록하고, 장치에 정책을 배포하며 장치가 기본 보안 요구 사항을 준수하는지 확인하는 방법을 설명합니다.

-   **회사 리소스에 대한 액세스 권한 제공**. 이 섹션에서는 IT가 관리되는 장치에 액세스 프로필을 배포하여 사용자가 회사 리소스에 쉽고 안전하게 액세스할 수 있도록 하는 방법과 Intune을 사용하여 대량 구매 앱 배포를 관리하는 방법을 설명합니다.  

-   **회사 데이터 보호** 이 섹션에서는 회사 리소스에 대한 조건부 액세스를 제공하고, 데이터 손실을 방지하며 더 이상 업무에 필요하지 않거나 분실 또는 도난된 장치에서 회사 앱 및 데이터를 제거하는 방법을 알아볼 수 있습니다.

## <a name="enroll-devices-and-check-for-compliance"></a>**장치 등록 및 준수 확인**

이 섹션에서는 사용자가 장치를 Intune의 관리 기능에 등록하고 장치가 기본 보안 요구 사항을 준수하는지 확인하는 방법을 설명합니다.

### <a name="enable-users-to-enroll-their-personal-devices-into-management"></a>사용자가 관리 기능에 개인 장치를 등록할 수 있도록 설정

Intune의 관리 기능에 장치 및 PC를 등록하면 관리되는 장치에 대해 구성한 모든 정책 및 액세스 프로필이 적용될 수 있습니다. 장치를 등록하기 전에 먼저 사용자에게 라이선스를 할당하고 모바일 장치 관리 권한을 설정하여 [Intune 서비스를 준비](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)하고, 사용자가 관리하려는 여러 다양한 장치 유형에 대한 다양한 등록 요구 사항을 충족해야 합니다. 작업을 시작한 후에도 사용자에게 신뢰할 수 있는 등록 및 지원 환경을 제공할 수 있도록 지원 정보 빛 회사별 브랜딩을 사용하여 [회사 포털을 사용자 지정](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)해야 합니다.

Intune 서비스를 준비한 후 관리 기능에 장치를 등록하는 프로세스는 간단하지만 장치 종류별로 약간 다를 수 있습니다.

-   **iOS 및 Mac 장치**. iPad, iPhone 또는 MacOS 장치를 등록하려면 APNs(Apple Push Notification Service) 인증서가 필요합니다. [Intune에 APNs 인증서를 업로드](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)한 후에는 사용자가 회사 포털 앱을 사용하여[iOS 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)하고 회사 포털 웹 사이트를 사용하여 [MacOS 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)할 수 있습니다.

-   **Android 장치**. Android 장치를 등록하기 위해 Intune 서비스를 준비하는 데 필요한 작업은 없습니다. 사용자는 Google Play에서 제공되는 회사 포털 앱을 사용하여 관리 기능에 [Android 장치를 등록](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)하기만 하면 됩니다.

-   **Android for Work**. 회사 프로필을 Intune에서 관리할 수 있는 Android 5.0 Lollipop 이상 장치에 대해 [Android for Work를 설정](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)하려면 조직에서 Google을 통해 Android for Work에 등록한 다음 Intune 관리 콘솔의 ADMIN 노드에서 Android for Work 설정을 구성해야 합니다.

-   **Windows Phone 및 PC**. [등록 서버에 대해 DNS 별칭을 설정](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)하여 Windows 장치를 보다 쉽게 등록할 수 있습니다. 그렇지 않으면 회사 또는 학교 계정을 추가하여 [Windows 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)할 수 있습니다.

> [!TIP]
> Azure AD(Premium)에서 [자동 등록을 사용하도록 설정](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)면 사용자가 Windows 장치를 더 쉽게 등록할 수 있습니다. 이렇게 하는 경우 사용자가 회사 또는 학교 계정을 추가하여 개인 장치를 등록하거나 회사 소유 장치가 조직의 Azure AD에 연결할 때 장치가 Intune의 관리 기능에 자동으로 등록됩니다.

### <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>관리되는 장치가 기본 보안 요구 사항을 준수하는지 확인

사용자가 장치를 관리 기능에 등록하면 IT는 회사 앱 및 데이터에 액세스하는 데 사용되는 장치가 기본 보안 요구 사항을 준수하는지 확인해야 합니다. 이러한 규칙에는 장치에 액세스하는 데 PIN을 사용하고 장치에 저장된 데이터를 암호화하는 규칙이 포함됩니다. 이러한 규칙의 집합을 [준수 정책](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)이라고 합니다.

[준수 정책을 만들고 사용자에게 배포](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)할 때 사용자가 Intune으로 관리하는 모든 장치를 검사하여 BYOD 정책의 일부로 정의한 기본 보안 요구 사항을 준수하는지 확인합니다. 장치가 정책을 준수한다고 확인되면 장치 상태를 Intune 서비스에 다시 보고합니다. 경우에 따라서는 PIN 또는 장치 암호화 사용과 같은 비준수 설정을 수정하라는 메시지가 표시될 수도 있지만, 회사 포털 앱에서 확인된 준수 문제만 알리는 경우도 있습니다.

## <a name="provide-access-to-company-resources"></a>회사 리소스에 대한 액세스 권한 제공

이 섹션에서는 IT가 관리되는 장치에 액세스 프로필을 배포하고 대량 구매 앱 배포를 관리하여 사용자가 회사 리소스에 쉽고 안전하게 액세스할 수 있도록 하는 방법을 설명합니다.

### <a name="provide-access-to-company-data"></a>회사 데이터에 대한 액세스 제공
대부분 직원들이 모바일 장치에서 원하는 첫 번째 기능은 회사 메일 및 문서에 대한 액세스입니다. 또한 복잡한 단계를 거치거나 지원 센터에 문의하지 않고 설정을 진행할 수 있기 바랍니다. Microsoft Intune을 사용하면 조직에서 사용하는 모바일 장치에 사전 설치되는 기본 메일 앱에 대한 [메일 설정을 쉽게 만들고 배포](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)할 수 있습니다.

> [!NOTE]
> Intune에서는 Google Play 스토어에 있는 Gmail 및 Nine Work 메일 앱에 대해 Android for Work 메일 프로필 구성을 지원합니다.

메일 외에도 EMS에서는 기존 회사 보안 경계 외부에서 액세스하는 온-프레미스 회사 데이터에 대한 액세스를 제어하고 보호할 수도 있습니다. Microsoft Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) 및 전자 메일 프로필은 함께 작동하여 사용자가 어디에 있든지 상관없이 정상적인 작업 수행에 필요한 파일 및 리소스에 쉽게 액세스하게 해 줍니다. 온-프레미스에 호스트된 회사의 웹 응용 프로그램 및 서비스도 Azure Active Directory 응용 프로그램 프록시 및 조건부 액세스를 사용하여 안전하게 액세스하고 보호할 수 있습니다.

### <a name="manage-volume-purchased-apps"></a>대량 구매 앱 관리
[스토어 앱을 관리되는 장치에 쉽게 제공](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)하고 관리되지 않는 장치에도 회사 포털 웹 사이트를 사용하여 앱을 제공할 수 있지만 Intune에서는 iOS 앱 스토어 및 비즈니스용 Windows 스토어에서 대량으로 구입한 앱도 관리하고 배포할 수 있습니다. 이 덕분에 대량으로 구입한 앱을 추적하는 관리 오버헤드를 줄일 수 있습니다.

> [!TIP]
> [Azure AD Connect를 사용하여 SSO(Single Sign-On)를 간단히 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)하여 사용자가 온-프레미스에서 사용하는 도메인 사용자 이름과 암호로 앱에 로그인하도록 할 수 있습니다. 또한 Azure Active Directory 응용 프로그램 프록시를 사용하여 [온-프레미스에 호스트된 웹앱에 대한 인터넷 기반 액세스를 제공](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)할 수 있습니다.

Intune을 사용하면 쉽게 앱 스토어에서 볼륨 라이선스 정보를 가져오고, 사용한 라이선스 수를 추적하고, 사용자가 소유한 앱 복사본 수를 초과하여 설치하지 않도록 할 수 있습니다.

-   [iOS 장치용 대량 구매 앱 관리](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). [Apple 비즈니스용 VPP(Volume Purchase Program)](http://www.apple.com/business/vpp/)를 통해 iOS 앱의 라이선스를 여러 개 구매합니다. 이 경우 Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드해야 합니다. 그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

-   [비즈니스용 Windows 스토어](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). [비즈니스용 Windows 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 스토어를 Microsoft Intune에 연결하여 Intune 포털에서 대용량 구입 앱을 관리할 수 있습니다.

## <a name="protect-company-data"></a>회사 데이터 보호

Intune은 여러 기술 계층을 통해 회사 데이터를 보호합니다. ID 계층에서 조건부 액세스를 통해 관리되는 호환 장치에서만 액세스를 허용하여 서비스에 대한 액세스를 보호합니다. 클라이언트 응용 프로그램 계층에서 MAM(모바일 응용 프로그램 관리)은 보호되지 않는 앱 또는 저장소 위치로 데이터가 이동되는 것을 방지하고 장치를 분실하거나 도난당한 경우 데이터를 삭제하여 데이터 손실을 보호합니다.

### <a name="enforce-conditional-access-to-company-resources"></a>회사 리소스에 대한 조건부 액세스 적용

준수 정책을 [조건부 액세스 정책](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)과 함께 사용하여 장치가 BYOD 정책에서 요구하는 기본 보안 요구 사항을 준수하는지 확인할 수 있습니다. 장치가 정책을 준수하지 않는 경우 조건부 액세스 규칙이 적용되고 장치가 정책 요구 사항에 맞게 구성될 때까지 액세스가 거부됩니다. 이 경우 관리되는 준수 장치만 Exchange([Exchange 온-프레미스](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune) 또는 [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)), SharePoint Online, 비즈니스용 Skype Online 등과 같은 서비스에서 회사 데이터에 액세스할 수 있습니다.

> [!IMPORTANT]
> 규정 준수 유효성을 검사하기 위한 준수 정책이 없으면 조건부 액세스 정책이 작동되지 않습니다.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>응용 프로그램 보호 정책으로 회사 데이터 손실 방지

Intune의 응용 프로그램 보호 정책을 사용하면 장치 등록 여부와 관계없이 데이터에 액세스하는 방법을 유연하게 관리할 수 있습니다. 장치 등록 여부와 관계없이 회사 데이터를 보호할 수 있는 기능을 통해 데이터 보호 시나리오를 사용하도록 설정할 수 있으므로 사용자가 장치를 관리 기능에 등록하지 않는 경우에도 회사 데이터에 안전하게 액세스할 수 있습니다.

[Intune 앱 보호 정책](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)을 사용하여 사용자의 iOS 및 Android 장치를 통해 액세스되는 회사 데이터를 보호할 수 있습니다. 이러한 앱 수준 정책을 구현하면 장치 자체를 Intune에서 관리하지 않더라도 직원들이 회사 데이터를 사용하고 공유하는 방법을 제어할 수 있습니다.

관리되는 Windows 10 장치의 경우 [WIP(Windows Information Protection) 정책](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies)을 사용하여 동일한 기능을 수행할 수 있습니다. 이러한 정책은 직원 환경을 방해하거나 네트워크 환경 또는 다른 앱을 변경하지 않으면서 작동합니다.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>개인 데이터를 그대로 두고 회사 데이터 초기화

장치가 더 이상 작업에 필요하지 않거나, 용도 변경 중이거나, 유실된 경우 장치에서 회사 앱과 데이터를 제거해야 합니다. 이를 위해, Intune의 선택적 초기화 및 전체 초기화 기능을 사용할 수 있습니다. 사용자는 Intune 회사 포털에서 관리 기능에 등록한 개인 소유의 장치를 원격으로 초기화할 수 있습니다.

장치를 공장 기본 설정으로 복원하고 사용자 데이터 및 설정을 제거하는 [전체 초기화](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe)를 수행하기보다는 [선택적 초기화](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) 기능을 사용하여 사용자의 개인 데이터를 그대로 유지하면서 장치에서 회사 데이터만 제거할 수 있습니다.

시작되면 장치가 즉시 선택적 초기화 프로세스를 시작하여 관리 기능에서 제거됩니다. 프로세스가 완료되면 모든 회사 데이터가 삭제되고 장치 이름이 Intune 관리자 콘솔에서 제거되면서 장치 관리 수명 주기가 완료됩니다.

### <a name="learn-more"></a>자세한 정보
[EMS(Enterprise Mobility + Security) 사용 시작](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

