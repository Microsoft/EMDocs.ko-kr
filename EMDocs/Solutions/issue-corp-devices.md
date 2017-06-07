---
title: "회사 소유 장치를 Intune으로 관리 | Microsoft 문서"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9e695ec-5608-43bb-bbfb-808b869b1567
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: b5be7105266a7f455e1482a814929f65a130db82
ms.openlocfilehash: 6b220f4992651b5f3c107b5b958c47900515b77f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/08/2017


---

# <a name="manage-company-owned-devices-with-intune"></a>Intune으로 회사 소유 장치 관리

현대의 직장에서 직원의 이동성 경험에 관한 기대치를 충족할 수 있는 옵션에는 여러 가지고 있으며, 그 중에 BYOD(Bring Your Own Device) 프로그램도 포함됩니다. 그러나 대부분의 조직에서는 회사 데이터에 액세스하는 데 사용되는 장치를 더 엄밀하게 제어하고자 합니다. 이러한 시나리오에서 기업은 IT 부서에서 직원들에게 관리되는 모바일 장치를 제공하는 CYOD(Choose Your Own Device) 전략을 구현할 수 있습니다.

CYOD 전략이 성공하려면 회사에서 사용자가 선택할 수 있는 장치를 다양하게 엄선하여 제공할 수 있어야 합니다. BYOD 대신 CYOD를 구현하려는 조직에서 특히 이 점이 중요합니다. 사용자는 조직에서 발급한 장치가 마음에 들지 않으면 관리되지 않는 자기 장치를 사용하려 하기 때문입니다. CYOD를 사용하면 IT 부서에서 특정 장치만 관리 대상으로 등록하여 지원 비용을 절감하고, 장치가 직원에게 발급되는 순간부터 회사 데이터를 보호할 수 있습니다.  직원들은 추가 단계를 수행하거나 지원 센터에 연락해서 장치를 관리하고 회사 데이터 액세스를 구성하지 않아도 이미 생활에서 익숙한 모바일 장치 옵션을 사용할 수 있습니다.  

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?

장치 유형, 장치 구매 방법, 조직의 요구 사항에 따라 다양한 방법으로 Microsoft Intune을 통해 관리할 조직 소유 또는 회사 소유의 장치를 등록할 수 있습니다. 회사 포털 앱을 설치하여 [BYOD(Bring Your Own Device) 시나리오](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod)의 경우처럼 회사 소유 장치를 등록하고 관리할 수도 있습니다. Apple이 제공하는 구성 도구를 통해 Intune에서 관리할 회사 소유의 iOS 장치를 직접 등록할 수 있습니다. 관리자(admin) 또는 관리자(manager)는 장치 등록 관리자를 사용하여 모든 장치 유형을 등록할 수 있습니다. COD 시나리오를 사용할 수 있도록 IMEI 번호가 있는 장치도 식별하고 회사 소유로 태그를 지정할 수 있습니다.

EMS로 어디서든 다양한 작업 스타일을 수용하는 생산적인 작업 공간을 만들기 위한 기능과 환경을 제공할 수 있습니다. 직원들이 iOS, MacOS, Android, Windows 장치 등 무엇을 사용하든, Intune을 통해 다양한 장치에서 직원 생산성을 향상하면서도 회사 데이터를 안전하게 보호할 수 있습니다. Intune은 포괄적인 모바일 장치 앱 및 수명 주기 관리를 제공할 뿐 아니라, Office 365 및 Office 모바일 앱과 직접 통합되므로 회사 데이터를 쉽게 보호할 수 있습니다.

### <a name="recommended-solution"></a>권장 솔루션

Intune을 사용하여 회사 정보를 안전하게 유지하면서 직원들이 거의 어디에서 어떤 장치를 사용하든 회사 응용 프로그램, 데이터 및 리소스에 쉽게 액세스할 수 있도록 합니다. Office 365와의 직접 통합을 통해 뛰어난 최종 사용자 환경을 지원하고 Office 모바일 앱에 대한 포괄적인 데이터 손실 보호 기능과 Office 365에 대한 액세스 제어 기능을 제공합니다. 장치를 분실 또는 도난당하거나 장치가 더 이상 업무에 필요하지 않게 되는 경우 Intune에서는 관리되는 장치에서 회사 데이터만 선택적으로 초기화할 수 있습니다.

>[!Note]
>Intune에서는 이 솔루션에 설명된 방법 중 하나를 사용하여 장치를 등록한 경우 그 장치를 *회사* 소유 장치로 인식합니다. 장치가 Intune 서비스에서 회사 장치로 인식되면 관리자 콘솔의 해당 장치 레코드에서 소유권 열에 **회사**로 표시됩니다.

![복잡한 장치 환경에서의 선택 사항](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>이 인포그래픽은 https://gallery.technet.microsoft.com/Infographic-Management-3644ae41에서 다운로드할 수 있습니다.</sup>

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
이 솔루션의 나머지 부분은 다음을 수행하는 방법을 설명하는 다음과 같은 섹션으로 구분됩니다.
- **회사 소유의 iOS 장치 등록**. 이 섹션에서는 Apple Configurator(Mac 장치) 및 Apple DEP 통합을 사용하여 회사 소유의 장치를 등록하는 방법을 설명합니다.
- **회사 소유의 Windows 10 장치 등록**. 이 섹션에서는 Windows 10 장치가 회사의 Azure Active Directory에 참가할 때 관리 대상으로 자동 등록하는 방법을 설명합니다.
- **DEM(장치 등록 관리자) 계정을 사용하여 장치 등록**. DEM 계정을 사용하여 IT 직원 한 사람이 기본 수량보다 많은 장치를 관리 대상으로 등록하는 방법을 알아봅니다.
- **IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 태그 지정**. 이 섹션에서는 등록 시에 회사 소유의 장치를 식별하는 IMEI 번호를 가져와서 회사 소유의 장치를 관리하기 시작하는 다른 옵션을 설명합니다.
- **관리되는 장치가 기본 보안 요구 사항을 준수하는지 확인**. 이 섹션에서는 회사 앱 및 데이터에 액세스하는 장치가 기본적인 보안 요구 사항을 준수하도록 하는 방법을 설명합니다.
- **회사 리소스에 대한 액세스 권한 제공**. 이 섹션에서는 IT가 관리되는 장치에 액세스 프로필을 배포하여 사용자가 회사 리소스에 쉽고 안전하게 액세스할 수 있도록 하는 방법과 Intune을 사용하여 대량 구매 앱 배포를 관리하는 방법을 설명합니다.
- **회사 데이터 보호** 이 섹션에서는 회사 리소스에 대한 조건부 액세스를 제공하고, 데이터 손실을 방지하며 더 이상 업무에 필요하지 않거나 분실 또는 도난된 장치에서 회사 앱 및 데이터를 제거하는 방법을 알아볼 수 있습니다.

## <a name="enroll-corporate-owned-ios-devices"></a>회사 소유의 iOS 장치 등록
CYOD 전략을 통해 사용자가 선택할 수 있는 iOS 장치를 제공할 경우, 사용자가 처음 장치를 켤 때부터 Intune으로 관리되도록 등록을 미리 구성할 수 있습니다. Intune에서는 [Apple DEP(장치 등록 프로그램)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)을 통한 등록, Mac 컴퓨터의 Apple Configurator 도구를 통한 [설치 도우미](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) 사용 또는  [직접](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) 등록을 지원합니다. DEP를 통해 구매한 iOS 장치에 등록 프로필을 *무선으로* 배포할 수도 있습니다.

### <a name="setup-assistant-enrollment"></a>설치 도우미 등록
[iOS 장치의 설치 도우미 등록 옵션](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)을 사용하면 장치가 공장 기본 설정으로 복원되고 장치의 새 사용자가 최종 설정을 할 수 있도록 준비됩니다. 이 방법을 사용하려면 관리자가 iOS 장치를 [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017)를 실행하는 Mac 컴퓨터에 USB로 연결하여 등록을 미리 구성해야 합니다. 그러면 설치 도우미 프로세스를 실행하는 사용자에게 장치가 제공됩니다. 이 프로세스에서는 회사 또는 학교 자격 증명을 사용하여 장치를 구성하고 등록 프로세스를 완료합니다.

### <a name="direct-enrollment"></a>직접 등록
[iOS 장치의 직접 등록](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)에서는 장치 준비에 사용할 Apple Configurator 규격 파일을 만듭니다. 등록된 장치가 공장 기본 설정으로 복원되지 않았으나 사용자 정보가 없습니다. 이 방법을 사용하려면 관리자가 iOS 장치를 [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017)를 실행하는 Mac 컴퓨터에 USB로 연결하여 장치를 등록해야 합니다.

### <a name="dep-enrollment"></a>DEP 등록
Microsoft Intune은 *무선으로* [DEP(장치 등록 프로그램)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)를 통해 구매한 iOS 장치를 등록하는 등록 프로필을 배포할 수 있습니다. 등록 패키지에는 사용자가 장치에서 설치 도우미를 실행할 때 장치가 Intune에 등록되면서 *0일* 관리 기능을 제공할 수 있도록 설치 도우미 옵션을 포함할 수 있습니다.

>[!Important]

>[DEP를 통해 등록된 장치](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)는 사용자가 등록을 취소할 수 없습니다.

## <a name="enroll-corporate-owned-windows-10-devices"></a>회사 소유의 Windows 10 장치 등록
Azure AD(Premium)에서 자동 등록을 사용하도록 설정하면 사용자가 Windows 장치를 관리 대상으로 원활하게 등록할 수 있습니다. 이렇게 하는 경우 사용자가 회사 또는 학교 계정을 추가하면 회사 소유 장치가 조직의 Azure AD에 연결할 때 장치가 Intune의 관리 기능에 자동으로 등록됩니다.

[Windows 10 Azure AD 조인(Azure Active Directory 조인)](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-overview)을 사용하면 사용자가 Azure AD를 통해 쉽게 엔터프라이즈 클라우드에 연결할 수 있습니다. 여기에서 Windows 장치로 조직의 앱 및 리소스에 액세스할 수 있습니다. 자동 장치 등록 통합을 사용하면 이러한 장치도 Microsoft Intune에서 자동으로 관리됩니다.

>[!Tip]

>[Microsoft Azure 포털](https://portal.azure.com)에서 Azure AD Premium 디렉터리에 자동 MDM 등록하도록 설정하려면 **Azure Active Directory** > **이동성(MDM 및 MAM)** > **Microsoft Intune**으로 이동합니다.

Azure AD 조인은 클라우드 중심/클라우드 전용 기업을 위한 것입니다. 이러한 조직은 일반적으로 온-프레미스 Windows Server AD DS(Active Directory Domain Services) 인프라가 없는 중소기업입니다. 한편, Azure AD 조인은 대형 조직에서 기존의 도메인 조인을 수행할 수 없는 장치나(모바일 장치 등) 주로 Office 365 또는 기타 Azure AD SaaS 앱에 액세스하는 사용자가 사용할 수도 있습니다. Intune을 사용해서 장치 관리를 수행하면 IT 관리자는 [하이브리드 MDM](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management#what-is-hybrid-mdm-with-configuration-manager)을 통해 Configuration Manager 관리 콘솔에서 AD DS 도메인으로 조인된 장치와 함께 Azure AD로 조인된 장치를 관리할 수 있습니다.
사용자가 Windows 10 장치에서 회사 또는 학교 계정을 추가하면 장치에는 자동으로 “회사 소유”라는 태그가 지정됩니다.

## <a name="enroll-devices-with-a-device-enrollment-manager-dem-account"></a>DEM(장치 등록 관리자) 계정을 사용하여 장치 등록
Intune [DEM(장치 등록 관리자) 계정](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) 하나를 사용하여 조직에 다수의 모바일 장치를 등록할 수 있습니다. DEM 계정을 만들면 그 계정으로 최대 1,000개의 장치를 등록할 수 있습니다.

DEM 계정을 사용하여 한 명의 특정 사용자가 사용하지 않는 장치만 등록할 수 있습니다. 해당 장치 유형은 예를 들어 POS(Point-Of-Sale) 또는 유틸리티 앱에는 유용하지만 메일 또는 회사 리소스에 액세스해야 하는 사용자에게는 유용하지 않습니다.
- 앱 관리에 대한 사용자별 Apple ID 요구 사항으로 인해 Apple VPP(Volume Purchase Program) 앱을 사용할 수 없습니다.
- DEM을 사용하여 iOS 장치를 등록하는 경우 Apple Configurator 또는 Apple DEP(장치 등록 프로그램)를 사용하여 장치를 등록할 수 없습니다.

## <a name="tag-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>IMEI(International Mobile Equipment Identity) 번호로 회사 소유의 장치 태그 지정
Microsoft Intune에서는 관리자가 회사 소유의 모바일 장치를 식별하는 데 도움이 되는 IMEI 번호가 있는 모바일 장치 플랫폼에 대해 [IMEI(International Mobile Equipment Identity) 번호를 가져올](https://docs.microsoft.com/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) 수 있습니다.

특수한 서식이 지정된 .CSV 파일을 사용하여 최대 5,000개의 IMEI 번호를 가져오거나 Intune 관리 콘솔에서 한 번에 최대 15개의 장치 IMEI 번호를 수동으로 입력할 수 있습니다. IMEI 번호가 있는 장치가 Intune에서 등록되면, 일반적으로 사용자가 회사 포털 앱을 설치하고 등록 프로세스를 완료할 때 장치에 회사 소유로 태그가 지정되며 IMEI 장치 그룹에 등록된 것으로 표시됩니다.

## <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>관리되는 장치가 기본 보안 요구 사항을 준수하는지 확인
iOS, Android 또는 Windows 10 장치 어느 것을 등록하는 경우건, IT 부서에서는 회사 앱 및 데이터 액세스에 사용되는 장치가 기본 보안 요구 사항을 준수하는지 확인해야 합니다. 이러한 규칙에는 장치에 액세스하는 데 PIN을 사용하고 장치에 저장된 데이터를 암호화하는 규칙이 포함됩니다. 이러한 규칙의 집합을 [준수 정책](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)이라고 합니다.

[준수 정책을 만들고 사용자에게 배포](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)할 때 사용자가 Intune으로 관리하는 모든 장치를 검사하여 CYOD 또는 BYOD 정책의 일부로 정의한 기본 보안 요구 사항을 준수하는지 확인합니다. 장치가 정책을 준수한다고 확인되면 장치 상태를 Intune 서비스에 다시 보고합니다. 경우에 따라서는 PIN 또는 장치 암호화 사용과 같은 비준수 설정을 수정하라는 메시지가 표시될 수도 있지만, 회사 포털 앱에서 확인된 준수 문제만 알리는 경우도 있습니다.

## <a name="provide-access-to-company-resources"></a>회사 리소스에 대한 액세스 권한 제공

이 섹션에서는 IT가 관리되는 장치에 액세스 프로필을 배포하고 대량 구매 앱 배포를 관리하여 사용자가 회사 리소스에 쉽고 안전하게 액세스할 수 있도록 하는 방법을 설명합니다.

### <a name="provide-access-to-company-data"></a>회사 데이터에 대한 액세스 제공
대부분 직원들이 모바일 장치에서 원하는 첫 번째 기능은 회사 메일 및 문서에 대한 액세스입니다. 또한 복잡한 단계를 거치거나 지원 센터에 문의하지 않고 설정을 진행할 수 있기 바랍니다. Microsoft Intune을 사용하면 조직에서 사용하는 모바일 장치에 사전 설치되는 기본 메일 앱에 대한 [메일 설정을 쉽게 만들고 배포](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)할 수 있습니다.

> [!NOTE]
> Intune에서는 Google Play 스토어에 있는 Gmail 및 Nine Work 메일 앱에 대해 Android for Work 메일 프로필 구성을 지원합니다.

메일 외에도 EMS에서는 기존 회사 보안 경계 외부에서 액세스하는 온-프레미스 회사 데이터에 대한 액세스를 제어하고 보호할 수도 있습니다. Microsoft Intune [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) 및 전자 메일 프로필은 함께 작동하여 사용자가 어디에 있든지 상관없이 정상적인 작업 수행에 필요한 파일 및 리소스에 쉽게 액세스하게 해 줍니다. 온-프레미스에 호스트된 회사의 웹 응용 프로그램 및 서비스도 Azure Active Directory 응용 프로그램 프록시 및 조건부 액세스를 사용하여 안전하게 액세스하고 보호할 수 있습니다.

### <a name="add-apps-for-enrolled-devices"></a>등록된 장치용 앱 추가
Intune을 사용하여 등록된 장치에 앱을 추가하기는 쉽지만, 앱을 배포하거나 관리하기 전에 Intune Software Publisher를 사용하여 [Intune에 추가](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)해야 합니다. Intune 소프트웨어 게시자를 사용하여 앱 속성을 구성한 다음 해당하는 경우 클라우드 저장소 공간에 앱을 업로드합니다.

Intune을 사용하면 등록된 장치에서 [다음과 같은 유형의 앱을 배포 또는 관리](https://docs.microsoft.com/intune/deploy-use/add-apps)할 수 있습니다.
- **소프트웨어 설치 관리자**. 이러한 종류의 앱에는 Windows 소프트웨어 설치 관리자(.exe 또는 .msi), Android용 앱 패키지(.apk), iOS용 앱 패키지(.ipa), Windows Phone 앱 패키지(.xap, .appx 및 .appxbundle), Windows 앱 패키지(.appx, .appxbundle) 및 Windows Installer through MDM(.msi) 파일이 포함됩니다. 모든 소프트웨어 설치 관리자 앱 유형은 [클라우드 저장소 공간](https://docs.microsoft.com/intune/deploy-use/add-apps#cloud-storage-space)에 업로드됩니다.
- **외부 링크**. 이 유형의 앱 배포에서는 사용자가 앱 스토어에서 앱을 다운로드할 수 있는 외부 링크(URL)나 웹 브라우저에서 실행되는 웹 기반 앱의 링크를 제공합니다. 외부 링크를 기반으로 하는 앱은 Intune 클라우드 저장소 공간에 저장되지 않습니다.
- **앱 스토어의 관리되는 iOS 앱**. 관리되는 iOS 앱을 사용하여 앱 스토어에서 무료 iOS 앱을 관리하고 배포할 수 있습니다. 또한 관리되는 iOS 앱을 사용하여 모바일 응용 프로그램 관리 정책을 호환되는 앱과 연결하고 관리자 콘솔에서 관련 상태를 검토할 수 있습니다. 관리되는 iOS 앱은 Intune 클라우드 저장소 공간에 저장되지 않습니다.

### <a name="manage-volume-purchased-apps"></a>대량 구매 앱 관리
[스토어 앱을 관리되는 장치에 쉽게 제공](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)하고 관리되지 않는 장치에도 회사 포털 웹 사이트를 사용하여 앱을 제공할 수 있지만 Intune에서는 iOS 앱 스토어 및 비즈니스용 Windows 스토어에서 대량으로 구입한 앱도 관리하고 배포할 수 있습니다. 이 덕분에 대량으로 구입한 앱을 추적하는 관리 오버헤드를 줄일 수 있습니다.

> [!TIP]
> [Azure AD Connect를 사용하여 SSO(Single Sign-On)를 간단히 구성](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)하여 사용자가 온-프레미스에서 사용하는 도메인 사용자 이름과 암호로 앱에 로그인하도록 할 수 있습니다. 또한 Azure Active Directory 응용 프로그램 프록시를 사용하여 [온-프레미스에 호스트된 웹앱에 대한 인터넷 기반 액세스를 제공](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)할 수 있습니다.

Intune을 사용하면 쉽게 앱 스토어에서 볼륨 라이선스 정보를 가져오고, 사용한 라이선스 수를 추적하고, 사용자가 소유한 앱 복사본 수를 초과하여 설치하지 않도록 할 수 있습니다.

-   [iOS 장치용 대량 구매 앱 관리](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). [Apple 비즈니스용 VPP(Volume Purchase Program)](http://www.apple.com/business/vpp/)를 통해 iOS 앱의 라이선스를 여러 개 구매합니다. 이 경우 Apple 웹 사이트에서 Apple VPP 계정을 설정하고 Apple VPP 토큰을 Intune에 업로드해야 합니다. 그런 다음 대량 구매 정보를 Intune과 동기화하고 대량 구매 앱 사용을 추적할 수 있습니다.

-   [비즈니스용 Windows 스토어](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). [비즈니스용 Windows 스토어](https://www.microsoft.com/business-store)는 개별적으로 또는 대량으로 조직에 대한 앱을 찾고 구입할 수 있는 위치를 제공합니다. 스토어를 Microsoft Intune에 연결하여 Intune 포털에서 대용량 구입 앱을 관리할 수 있습니다.

## <a name="protect-company-data"></a>회사 데이터 보호

Intune은 여러 기술 계층을 통해 회사 데이터를 보호합니다. ID 계층에서 조건부 액세스를 통해 관리되는 호환 장치에서만 액세스를 허용하여 서비스에 대한 액세스를 보호합니다. 클라이언트 응용 프로그램 계층에서 앱 보호 정책은 보호되지 않는 앱 또는 저장소 위치로 데이터가 이동되는 것을 방지하고 장치를 분실하거나 도난당한 경우 데이터를 삭제하여 데이터 손실을 보호합니다.

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

