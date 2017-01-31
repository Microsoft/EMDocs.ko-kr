---
title: "Microsoft Intune을 사용하여 온-프레미스 데이터 보호 | Microsoft 문서"
description: "EMS(Enterprise Mobility + Security)를 사용하면 직원들이 즐겨 사용하는 앱 및 장치로 직원 생산성을 유지할 수 있고 온-프레미스 회사 데이터도 보호할 수 있습니다."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebf7be63-4ac2-4158-9772-58f15416ccb7
ms.reviewer: vlpetros
ms.suite: ems
ms.custom: active-directory
translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 64c859600ba74da47d70a9c58bc261dec4411513


---
# <a name="protect-on-premises-company-data-with-intune"></a>Intune으로 온-프레미스 회사 데이터 보호
더 이상 방화벽만으로는 적절한 회사 보안 경계를 제공할 수 없습니다. 오늘날의 보안 경계에는 최종 사용자와 이 사용자가 회사 데이터를 액세스, 사용 및 공유하는 방법을 포함해야 합니다. 스마트폰, 태블릿, 랩톱 등 무엇으로 작업하든 정보 근로자는 어디서든 필요할 때 원하는 장치에서 리소스에 원활하게 액세스해야 합니다. 사용자에게 액세스 및 보호 기능을 제공하는 일은 회사 데이터도 보호해야 하는 IT 관리자에게 매우 어려운 일입니다. EMS(Enterprise Mobility + Security)를 사용하면 직원들이 즐겨 사용하는 앱 및 장치로 직원 생산성을 유지할 수 있고 온-프레미스 회사 데이터도 보호할 수 있습니다. 방법을 확인하려면 계속 읽어 보세요.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>EMS(Enterprise Mobility + Security)는 사용자에게 어떻게 도움을 줄 수 있나요?
EMS(Enterprise Mobility + Security)는 ID, 장치, 앱, 데이터 등의&4;단계 보호 기능으로 장치뿐 아니라 그 이상에서 기업 데이터를 기본적으로 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS를 사용하면 직원은 회사 메일과 문서에 안전하고 원활하게 액세스할 수 있고 IT는 회사 데이터 확실히 보호할 수 있습니다.

## <a name="recommended-solution"></a>권장 솔루션
Microsoft Intune을 사용하면 리소스 액세스 프로필을 원격으로 구성하여 메일 계정을 자동 프로비전하고 WiFi 또는 VPN 설정과 같은 프로필에 액세스하고 장치에서 신뢰할 수 있는 구성만 수신하여 설치하도록 인증서 프로필을 제공할 수 있습니다.

액세스 제공뿐 아니라 온-프레미스 Microsoft Exchange 2010 이상 서버에 대한 Intune의 조건부 액세스를 통해 관리되는 규격 장치만 회사 메일에 액세스할 수 있도록 합니다. 장치 자체를 넘어 관리를 확장할 뿐 아니라 Intune의 Cisco ISE(ID 서비스 엔진) 및 기타 파트너를 사용하여 intune의 관리 기능에 등록되고 회사 정책을 준수하는 장치만으로 액세스를 제한할 수도 있습니다. Azure Active Directory 응용 프로그램 프록시를 활용하여 VPN, DMZ 또는 온-프레미스 역방향 프록시 없이도 온-프레미스 응용 프로그램에 대한 보안 액세스를 제공할 수도 있습니다. 무엇보다 추가 온-프레미스 인프라를 설치 또는 유지 관리하거나 트래픽을 라우팅할 회사 방화벽을 열지 않고도 이 모든 작업을 수행할 수 있습니다.

다음은 EMS의 조건부 액세스를 통해 직원에게 iOS, Android 및 Windows 장치에서 회사 데이터에 안전하게 액세스하는 원활한 환경을 제공하는 방법에 대한 개요를 제공하는 간단한 동영상입니다.

<iframe width="675" height="480" src="https://youtube.com/embed/fvCT7Y3nlAY" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
이 솔루션의 나머지 부분은 Intune으로 Office 365 회사 데이터를 보호하는 방법을 보여 주는 다음과 같은 섹션으로 구분됩니다.
- **모바일 장치 및 Windows PC를 관리 기능에 등록**. 이 섹션에서는 Intune으로 온-프레미스 리소스에 대한 보안 액세스를 구성할 수 있도록 장치(iOS, Android, Android for Work 및 Windows PC)를 관리 기능에 등록하는 방법을 설명합니다.
- **회사 메일 액세스 및 보호**. 이 섹션에서는 Intune에서 사용자의 네이티브 앱 메일 설정을 자동으로 구성하는 방법 및 온-프레미스 Exchange 서버에 조건부 액세스를 제공하는 방법을 설명합니다.
- **다른 온-프레미스 회사 리소스에 대한 액세스 권한 제공**. 이 섹션에서는 Wi-Fi, VPN 또는 Azure Active Directory 응용 프로그램 프록시를 사용하여 직원에게 온-프레미스 네트워크 리소스에 대한 보안 액세스를 제공하는 방법을 설명합니다.
- **인증서를 사용하여 회사 리소스 액세스 보호**. 이 섹션에서는 PKCS #12(.PFX) 또는 SCEP(단순 인증서 등록 프로토콜)을 만들고 배포하여 회사 리소스에 대한 사용자 액세스를 보호할 수 있도록 도와줍니다.

## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>모바일 장치 및 Windows PC를 관리 기능에 등록
Intune의 관리 기능에 장치 및 PC를 등록하면 관리되는 장치에 대해 구성한 모든 정책 및 액세스 프로필이 적용될 수 있습니다. 장치를 등록하기 전에 먼저 사용자에게 라이선스를 할당하고 모바일 장치 관리 권한을 설정하여 [Intune 서비스를 준비](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)하고, 사용자가 관리하려는 여러 다양한 장치 유형에 대한 다양한 등록 요구 사항을 충족해야 합니다. 작업을 시작한 후에도 사용자에게 신뢰할 수 있는 등록 및 지원 환경을 제공할 수 있도록 지원 정보 빛 회사별 브랜딩을 사용하여 [회사 포털을 사용자 지정](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)해야 합니다.

Intune 서비스를 준비한 후 관리 기능에 장치를 등록하는 프로세스는 간단하지만 장치 종류별로 약간 다를 수 있습니다.

-   **iOS 및 Mac 장치**. iPad, iPhone 또는 Mac OS X 장치를 등록하려면 APNs(Apple Push Notification service) 인증서를 구해야 합니다. [Intune에 APNs 인증서를 업로드](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)한 후에는 사용자가 회사 포털 앱을 사용하여[iOS 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)하고 회사 포털 웹 사이트를 사용하여 [Mac OS X 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)할 수 있습니다.
-   **Android 장치**. Android 장치를 등록하기 위해 Intune 서비스를 준비하는 데 필요한 작업은 없습니다. 사용자는 Google Play에서 제공되는 회사 포털 앱을 사용하여 관리 기능에 [Android 장치를 등록](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)하기만 하면 됩니다.
-   **Android for Work**. 회사 프로필을 Intune에서 관리할 수 있는 Android 5.0 Lollipop 이상 장치에 대해 [Android for Work를 설정](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)하려면 조직에서 Google을 통해 Android for Work에 등록한 다음 Intune 관리 콘솔의 ADMIN 노드에서 Android for Work 설정을 구성해야 합니다.
-   **Windows Phone 및 PC**. [등록 서버에 대해 DNS 별칭을 설정](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)하여 Windows 장치를 보다 쉽게 등록할 수 있습니다. 그렇지 않으면 회사 또는 학교 계정을 추가하여 [Windows 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)할 수 있습니다.

> [!TIP]
> Azure AD(Premium)에서 [자동 등록을 사용하도록 설정](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)면 사용자가 Windows 장치를 더 쉽게 등록할 수 있습니다. 이렇게 하는 경우 사용자가 회사 또는 학교 계정을 추가하여 개인 장치를 등록하거나 회사 소유 장치가 조직의 Azure AD에 연결할 때 장치가 Intune의 관리 기능에 자동으로 등록됩니다.

## <a name="access-and-protect-company-email"></a>회사 메일 액세스 및 보호
대부분 직원들이 모바일 장치에서 원하는 첫 번째 기능은 회사 메일 및 문서에 대한 액세스입니다. 또한 복잡한 단계를 거치거나 지원 센터에 문의하지 않고 설정을 진행할 수 있기 바랍니다. Microsoft Intune을 사용하면 조직에서 사용하는 모바일 장치에 사전 설치되는 기본 메일 앱에 대한 메일 설정을 쉽게 만들고 배포할 수 있습니다.

Exchange 온-프레미스에 대해 Intune 조건부 액세스 정책을 사용하면 Azure Active Directory에 등록되고 정책을 준수하는 관리되는 장치만 회사의 온-프레미스 Exchange 서버 정보에 액세스하도록 할 수 있습니다.

### <a name="configure-exchange-email-settings-for-native-email-apps-on-managed-devices"></a>관리되는 장치에서 기본 메일 앱에 대한 Exchange 메일 설정 구성
다음과 같은 장치에서 메일 프로필 구성 정책을 만들고 사용자에게 배포하여 간단히 [기본 메일 앱 설정을 구성](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)할 수 있습니다.

-   Windows Phone&8; 이상
-   Windows 10 Desktop 및 Mobile
-   iOS&8;.0 이상
-   Android(삼성 Knox Standard 4.0 이상 및 Android for Work)
> [!NOTE]
> Intune에서는 Google Play 스토어에 있는 Gmail 및 Nine Work 메일 앱에 대해 Android for Work 메일 프로필 구성을 지원합니다.

### <a name="protect-access-to-your-on-premises-exchange-server"></a>온-프레미스 Exchange 서버에 대한 액세스 보호
Intune으로 메일 구성 설정을 제공하여 온-프레미스 Exchange 서버에 연결할 수 있을 뿐 아니라 Intune을 사용하여 Intune [온-프레미스 Exchange Connector](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)를 통한 [온-프레미스 Exchange 서버(2010 이상)에 대한 메일 액세스도 제어](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)할 수 있습니다.

장치가 등록되지 않았거나 회사 정책을 준수하지 않는 경우 사용자에게 장치를 관리 기능에 등록하는 방법이나 메일 액세스를 차단하는 준수 문제를 해결하는 방법에 대한 정보가 표시됩니다.

> [!TIP]
> Intune 조건부 액세스를 사용하여 회사의 Exchange 메일을 보호하는 방법에 대한 자세한 내용은 다음 [example scenarios](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios#all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune)(예제 시나리오)를 참조하세요.

조직에서 사용하는 다음과 같은 장치 유형에 대해 [Exchange 온-프레미스에 대한 조건부 액세스 정책을 구성](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune#configure-a-conditional-access-policy)할 수 있습니다.

-   Windows Phone&8;.1 이상
-   iOS&8;.0 이상
-   Android(4.0 이상 및 삼성 Knox Standard 4.0)
-   Android for Work(현재 Gmail 및 Nine Work 앱 메일 프로필만 지원)
-   관리되는 Windows PC의 메일 응용 프로그램

> [!NOTE]
> Intune 조건부 액세스 정책은 Android for Work용 Gmail 및 Nine Work 메일 앱을 제외하고 장치의 기본 메일 앱에만 적용됩니다. Android 및 iOS용 Microsoft Outlook 앱은 현재 지원되지 않지만 나중에 지원될 예정입니다.

## <a name="provide-access-to-other-on-premises-company-resources"></a>다른 온-프레미스 회사 리소스에 대한 액세스 권한 제공
메일 외에도 EMS에서는 기존 회사 보안 경계 외부에서 액세스하는 온-프레미스 회사 데이터에 대한 액세스를 제어하고 보호할 수도 있습니다. Microsoft Intune Wi-Fi, VPN 및 전자 메일 프로필은 함께 작동하여 사용자가 어디에 있든지 상관없이 정상적인 작업 수행에 필요한 파일 및 리소스에 쉽게 액세스하게 해 줍니다. 온-프레미스에 호스트된 회사의 웹 응용 프로그램 및 서비스도 Azure Active Directory 응용 프로그램 프록시 및 조건부 액세스를 사용하여 안전하게 액세스하고 보호할 수 있습니다.

### <a name="deploy-wi-fi-settings-to-managed-devices"></a>관리되는 장치에 Wi-Fi 설정 배포
Intune Wi-Fi 구성 정책을 사용하면 [무선 네트워크 설정을 사용자에게 쉽게 배포](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)할 수 있습니다. 이러한 설정을 사용하면 다음과 같은 지원되는 장치에서 사용자가 Wi-Fi 설정을 수동으로 구성하지 않고 회사 네트워크에 쉽게 연결할 수 있습니다.

-   Android(4.0 이상, 삼성 Knox Standard, Android for Work)<sup>1</sup>
-   iOS&8;.0 이상<sup>1</sup>
-   Mac OS X&10;.9 이상<sup>1</sup>
-   Windows 장치(Windows 8.1 이상 PC, Windows Phone 8.1 또는 Windows 10 Mobile 이상)<sup>2</sup>

> <sup>1</sup>기본 제공 Intune Wi-Fi 구성 정책을 사용할 수 있습니다.

> <sup>2</sup>[이전에 내보낸 Wi-Fi 설정 .xml 구성 프로필을 가져올](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune#export-or-import-a-wi-fi-configuration-profile-for-windows-devices) 수 있습니다.

### <a name="deploy-vpn-settings-to-managed-devices"></a>관리되는 장치에 VPN 설정 배포
VPN 연결은 사용자가 모바일 장치에서 회사 리소스에 원격으로 연결해야 하는 경우 사용됩니다. Intune을 사용하면 [VPN 구성 프로필을 만들고 배포](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile)하여 사용자가 VPN 서버 또는 인증 방법 정보를 수동으로 구성하지 않고도 회사 네트워크 리소스에 쉽고 안전하게 액세스하도록 할 수 있습니다.

다음과 같은 장치에서 [Intune에서 지원하는 여러 VPN 연결 형식](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#vpn-connection-types)에 대한 VPN 설정을 구성할 수 있습니다.

-   Android(4.0 이상, 삼성 Knox Standard, Android for Work)
-   iOS&8;.0 이상
-   Mac OS X&10;.9 이상
-   Windows 장치(Windows 8.1 이상 PC, Windows Phone 8.1 및 Windows 10 Mobile 이상)

### <a name="protect-network-access"></a>네트워크 액세스 보호
관리되는 규격 장치에만 회사 Exchange 정보 액세스를 허용하는 것과 같이 [Cisco ISE(ID 서비스 엔진)](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_00.html) 네트워크 정책을 사용하여 네트워크 환경에 대한 액세스를 보호할 수 있습니다. Cisco ISE는 802.1X 유선, 무선 및 VPN을 지원하는 엔터프라이즈 인프라에서 배포할 수 있는 정책 기반 네트워크 액세스 제어 시스템입니다.

Intune 관리 콘솔에서 설정을 구성하지 않고 Cisco ISE 관리 네트워크에 대한 장치 액세스는 Cisco ISE 서버에서 구성합니다. [Cisco ISE 서버에 Intune 테넌트에 액세스할 수 있는 권한을 부여](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-networks)한 다음 Cisco ISE 정책을 사용하여 관리되는 규격 장치에만 네트워크 환경에 대한 액세스를 허용하기만 하면 됩니다.

> [!IMPORTANT]
> 이 보호 기능을 활용하려면 EMS에 포함되지 않은 [Cisco ISE licenses](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_0110.html)(Cisco ISE 라이선스)가 필요합니다.

또한 SSO(Single Sign-On) 및 조건부 액세스를 사용하도록 설정하여 Azure AD 응용 프로그램 프록시를 사용하여 온-프레미스에 호스트된 웹 응용 프로그램에 대한 원격 액세스도 보호할 수 있습니다. Azure AD 응용 프로그램 프록시를 사용하면 사용자가 VPN 없이도 SharePoint 사이트, Outlook Web Access 또는 기타 LOB 웹 응용 프로그램과 같은 온-프레미스에 호스트된 웹 응용 프로그램에 쉽게 액세스할 수 있습니다. 원격 데스크톱 게이트웨이 뒤에 호스트된 다른 장치 및 앱을 지원하는 웹 API에 대한 연결도 보호할 수 있습니다.

[Azure Active Directory 응용 프로그램 프록시 설정](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-enable)은 간단합니다. Azure AD(Basic 또는 Premium)에서 기능을 사용하도록 설정하고 네트워크 내에 커넥터라는 작은 Windows Server 서비스를 설치한 다음 여기에 응용 프로그램을 게시하면 됩니다. 모든 인바운드 방화벽 포트를 열거나 어느 항목도 DMZ에 배치할 필요가 없습니다. 설정한 후에는 Azure AD에 대한 Single Sign-On을 통해 온-프레미스 웹 응용 프로그램에 액세스할 수 있습니다. 다단계 인증 요구 또는 직원이 회사에 없을 때 액세스 차단과 같은 [조건부 액세스 규칙](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-conditional-access)을 통해 추가로 보호할 수 있습니다

## <a name="use-certificates-to-secure-company-resource-access"></a>인증서를 사용하여 회사 리소스 액세스 보호
VPN, Wi-Fi 또는 메일 프로필을 통해 사용자에게 회사 리소스 액세스 권한을 부여하는 경우 단순한 사용자 이름과 암호를 인증하는 대신 각 사용자 장치에 설치된 [인증서를 사용하여 액세스 보안을 유지](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)할 수 있습니다.

다음과 같은 장치 플랫폼에서 **PKCS #12(.PFX)** 또는 **SCEP(단순 인증서 등록 프로토콜)** 인증서 프로필을 만들고 배포하여 인증 인증서를 요구하는 장치에 사용할 수 있습니다.

-   iOS&8;.0 이상
-   Mac OS X&10;.9 이상
-   Android(4.0 이상 및 Android for Work)
-   Window 8.1 이상
-   Windows Phone&8;.1 이상
-   Windows 10(데스크톱 및 모바일) 이상

회사에 대해 인증서 기반 인증을 수행하려면 엔터프라이즈 CA(인증 기관)가 필요하지만 SCEP 또는 .PFX 인증서를 사용하여 회사 리소스에 대한 액세스 보안을 유지하려면 충족해야 하는 다른 필수 조건도 있습니다.

-   Intune을 사용하여 SCEP 인증서 프로필을 만들고 배포하려면 먼저 [SCEP에 대한 인증서 인프라를 구성](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)해야 합니다. 이 단계에서는 엔터프라이즈 CA(인증 기관), NDES(네트워크 장치 등록 서버) 및 Microsoft Intune Certificate Connector 서버를 비롯한 여러 온-프레미스 서버를 구성해야 합니다.
-   엔터프라이즈 인증 기관 외에 [.PFX 인증서 프로필](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)(신뢰할 수 있는 모바일 장치 인증서)을 사용하려면 CA에서 설치할 수 있는 Intune Certificate Connector가 필요합니다. NDES는 필요하지 않습니다.

> [!NOTE]
> WAP(웹 응용 프로그램 프록시) 서버는 장치에서 인터넷 연결을 사용하여 인증서를 받고 갱신할 수 있도록 SCEP 및 .PFXS 인증서를 모두 사용하는 경우에 선택 사항입니다.

사용자에게 [인증서 프로필을 배포](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)하면 사용자 장치에 신뢰할 수 있는 CA 인증서가 설치됩니다. 그러면 장치는 SCEP 또는 .PFX 인증서 프로필을 사용하여 인증서 요청을 만듭니다. 인증서 요청이 완료되면 사용자 이름과 암호 대신 인증서 정책 인증 방법 옵션을 선택하여 인증서로 Wi-Fi, VPN 및 메일 프로필 구성 정책을 인증할 수 있습니다.

### <a name="learn-more"></a>자세한 정보

[EMS(Enterprise Mobility + Security) 사용 시작](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Jan17_HO4-->


