---
title: "장치를 관리하지 않고 회사 데이터 보호 | Microsoft 문서"
description: "EMS는 Microsoft Intune의 혁신적인 데이터 손실 방지 기능을 제공합니다. EMS를 사용하면 장치를 관리할 필요 없이 회사 데이터를 보호할 수 있고 직원이 익숙하게 느끼는 Office 365 앱의 최상의 사용자 경험을 그대로 유지할 수 있습니다."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b46877f3-cf32-4919-ba63-4df55cd2af32
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 5a0eef972374efefff886ab9dbf7b6a7e4f7aab7


---

# <a name="protect-company-data-without-managing-devices-with-intune"></a>Intune으로 장치를 관리하지 않고 회사 데이터 보호
현재 우리는 직원들이 이동 중에도 모바일 장치에서 회사 데이터와 생산성 도구에 액세스할 수 있어야 하는 세상에 살고 있습니다. 모바일 장치의 인기와 중요성 때문에 많은 조직이 뛰어난 최종 사용자 환경을 유지하면서 Office 모바일 앱의 데이터 손실을 방지하여 Office 365 데이터 보호를 강화할 방안을 찾고 있습니다. IT 조직은 Office 365에 대한 액세스를 보호하고, 조직이 소유하거나 관리하지 않는 모바일 장치와 앱에서 회사 데이터의 데이터 손실을 방지해야 합니다. 문제는 IT 조직은 회사 데이터 보안을 확보해야 하지만 대다수 직원은 IT 조직의 직원 장치 통제로 인해 자신들의 프라이버시가 손상되지 않을까 우려합니다.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>EMS(Enterprise Mobility + Security)는 사용자에게 어떻게 도움을 줄 수 있나요?

EMS는 Microsoft Intune의 혁신적인 데이터 손실 방지 기능을 제공합니다. EMS를 사용하면 회사 데이터를 보호할 수 있고 직원이 익숙하게 느끼는 Office 365 앱의 최상의 사용자 경험을 그대로 유지할 수 있습니다. 또한 사용자에게 장치를 관리 목적으로 등록하도록 요구할 필요가 없기 때문에, BYOD 프로그램의 성공 가능성과 최종 사용자의 IT 정책 준수 가능성이 크게 높아집니다. 관리자는 필요한 대로 환경을 통제하면서도 사용자는 원하는 최신 환경을 즐길 수 있습니다.  Microsoft Intune이 Azure Active Directory 및 Office 365와 바로 연동하여 회사 데이터에 대한 액세스를 관리하고 보호하기 때문에, 온-프레미스 인프라를 설치하여 유지 관리하거나 모든 트래픽을 해당 인프라를 통해 라우팅할 필요는 없습니다.

### <a name="recommended-solution"></a>권장 솔루션

Microsoft Intune을 통해 조직은 모바일 앱에 대한 액세스 권한을 보장할 수 있고 직원에게 장치 관리에 등록하도록 요구하지 않고 Office 365 데이터 누출을 보호할 수 있습니다. 필요한 경우에 장치 관리(MDM)를 수행할 수는 있지만, 현재 선택 사항입니다. IT 조직은 Intune의 강력한 응용 프로그램 보호 기능으로 실제 장치를 관리할 필요 없이 앱 수준에서 회사 데이터를 효과적으로 보호할 수 있습니다. 기밀 데이터의 경우 Azure Information Protection을 통해 파일 수준까지 보호를 확장할 수 있습니다. 직원, 공급업체 및 파트너는 선호하는 모바일 장치를 사용하여, 자신의 개인 정보에 대한 침해 걱정 없이 익숙한 생산성 도구와 회사 데이터에 액세스할 수 있습니다. IT 조직이 이미 MDM 솔루션을 사용하고 있다면 Intune에서 Office 365 액세스 제어 데이터 손실 방지를 추가할 수 있습니다. 이때 장치를 현재 MDM 솔루션에서 등록 해제하고 Intune MDM에 다시 등록할 필요가 없습니다.

Intune MDM에 사용자 장치를 등록하지 않고 Intune의 혁신적인 응용 프로그램 보호 기능을 사용하여 모바일 앱 (O365 및 LOB(내부-업무용) 앱 포함)에서 데이터 손실을 방지하는 방법을 보려면 이 데모를 시청하세요.

<iframe width="675" height="480"  src="https://www.youtube.com/embed/BcwgKmsAy18?list=TLGGQ9qBhVYxOZIxMzEyMjAxNg" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

이 솔루션의 나머지 부분은 Intune으로 Office 365 회사 데이터를 보호하는 방법을 보여 주는 다음과 같은 섹션으로 구분됩니다.

- **Intune 모바일 앱 보호 정책을 사용하여 앱 데이터를 보호**합니다. 이 섹션에서는 관리 대상이 아닌 모바일 장치 사용자에게 데이터 손실 방지 기능(예: copy/paste/save as/PIN/encryption/selective wipe/etc.)을 제공하기 위해 Microsoft Intune 응용 프로그램 보호 정책을 만들고 배포하는 방법을 설명합니다. 

- **Intune MAM 정책을 지원하는 모바일 앱만 Office 365 서비스에 액세스하도록 허용** 이 섹션에서는 Intune MAM 정책을 지원하는 모바일 앱만 Exchange Online과 같은 Office&365; 서비스 액세스에 허용하는 정책을 만드는 방법을 배울 수 있습니다.

## <a name="protect-app-data-with-intune-mobile-app-protection-policies"></a>Intune 모바일 앱 보호 정책을 사용하여 앱 데이터 보호

관리 대상이 아닌 장치에서 앱 데이터를 보호하는 경우 관리 대상 장치에서처럼 앱을 배포하지 않습니다. 대신 사용자는 개인 iOS 또는 Android 장치의 공용 앱 스토어에서 Office 365 앱을 다운로드한 뒤 평소처럼 회사 계정으로 로그인합니다.

그러한 앱에 대한 앱 보호 정책은 Azure 포털에서 iOS 및 Android 장치에 대해 간단하게 만들 수 있습니다. 이러한 종류의 정책으로, 잘라내기, 복사, 붙여넣기, 다른 이름으로 저장, PIN 강제 적용 같은 사용자 작업을 제한하고 암호화를 요구하며 모바일 앱에서 회사 데이터를 선택적으로 지울 수 있습니다. 사용자에게 할당된 앱 보호 정책은 자동으로 Intune에서 적용되며 개인 계정/응용 프로그램과 회사 계정/응용 프로그램 간에 적용됩니다. Intune이 Azure AD 및 Office 365와 원활하게 통합되기 때문에 작업 데이터가 보호되면서 동시에 Office 앱의 개인 데이터가 그대로 보존됩니다.

>[!NOTE]
>이 같은 앱 보호 정책은 Intune에서 [WIP(Windows 정보 보호) 정책](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune)을 통해 모바일 장치 형태로 관리하는 Windows 10 컴퓨터에 사용할 수 있습니다.

다음에서, 앱 보호 정책 설정을 보호하고 구성할 앱을 선택하고 Azure 포털에 로그인한 후 최종 사용자 그룹에 정책을 배포하는 게 얼마나 쉬운지 알 수 있습니다.

>[!TIP]
>Intune 앱 보호 정책 설정을 찾으려면 Intune 관리자 자격 증명으로 [Azure 포털](https://portal.azure.com)에 로그인하고 포털 맨 위에 있는 *리소스 검색* 상자에서 **Intune 앱 보호**를 검색하면 됩니다. 거기서 다음 모든 단계가 완료됩니다.

-   **모바일 앱 보호 정책을 만듭니다.** 정책 이름을 지정(및 선택적으로 설명 제공)하는 것 외에, [앱 보호 정책 만들려면](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#create-an-app-protection-policy) 플랫폼을 정의하고 보호하려는 앱을 선택하고 적용할 정책 설정을 구성하기만 하면 됩니다.

> **플랫폼 정의**: 새 정책을 만들 때 iOS 또는 Android 플랫폼을 선택할 수 있지만 여기서는 Windows 장치에 대한 앱 보호 정책을 만들 수 없습니다. 대신에 [WIP(Windows Information Protection) 정책](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune)을 사용할 수 있습니다.

> 관리되지 않는 장치의 보호 가능한 앱 목록에서 대상으로 할 **앱을 하나 이상 선택**합니다. 더 많은 앱이 지원되면 사용 가능한 앱 목록에 자동으로 추가됩니다. 기본적으로 아무것도 선택되어 있지 않지만 Ctrl+클릭으로 정책을 통해 보호할 앱을 원하는 만큼 여러 개 선택할 수 있습니다. 또는 iOS 또는 Android용의 [LOB(기간 업무) 앱 항목을 추가](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune)할 수 있습니다.

> 데이터 재배치(잘라내기, 복사, 붙여넣기, 다른 이름으로 저장, 암호화 등) 및 액세스(PIN 요구, 오프라인 간격 등)에 대해 [iOS 또는 Android](https://docs.microsoft.com/en-us/intune-azure/manage-apps/app-protection-policies#policy-settings)에 **필요한 정책 설정을 구성**합니다.

- 정책을 적용할 [사용자 그룹을 선택](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#deploy-a-policy-to-users)하여 **사용자 그룹에 앱 보호 정책을 배포**합니다. Office 365에서 이미 관리하는 그룹이거나 Azure Active Directory에서 사용할 수 있는 그룹과 같은 그룹이어도 됩니다.

처음으로 최종 사용자가 앱 보호 정책으로 보호되는 앱을 열면 IT 부서에서 앱의 회사 데이터를 현재 보호 중이라는 메시지를 받게 됩니다. PIN 또는 암호를 요구하도록 정책 액세스 설정을 구성한 경우, 아래와 같이 Android 장치에서 액세스할 때처럼 보호된 앱에 액세스하려면 PIN 또는 암호를 만들라는 메시지가 사용자에게 표시됩니다.

![앱 보호 정책 PIN 요구](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig1.png)

앱 보호 정책이 장치 수준 대신에 앱 수준에서 작동하기 때문에 Intune을 통해 IT 부서는 관리 앱과 개인 앱 간의 회사 데이터 공유와 동일한 앱의 회사 계정과 개인 계정 간의 회사 데이터 공유를 제한하고 회사 데이터를 승인된 위치에만 저장하도록 함으로써 회사 데이터를 쉽게 보호할 수 있습니다. 모바일 직원은 이동 중에도 개인 기기를 제어하면서 중요한 회사 도구와 데이터에 액세스할 수 있습니다.

>[!TIP]
>기밀 데이터의 경우 Azure Information Protection에 의해 사용되는 보호 기술을 통해 파일 수준까지 보호를 확장할 수 있습니다. [Azure RMS(Azure Rights Management)](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

## <a name="allow-only-mobile-apps-that-support-app-protection-policies-to-access-office-365-services"></a>Intune MAM 정책을 지원하는 모바일 앱만 Office 365 서비스에 액세스하도록 허용
기본적으로 모든 사용자 및 모든 앱이 Exchange Online에서 호스팅하는 회사 정보에 액세스할 수 있습니다. Intune에서 Office 365 서비스에 대한 액세스를 Intune의 앱 보호 정책을 지원하는 앱으로만 제한하는 앱 조건부 액세스 정책을 구성하여 액세스 권한이 있는 사람과 앱을 쉽게 제어할 수 있습니다. 예를 들어 [Azure 포털](https://portal.azure.com)에서 장치가 관리 대상인지에 상관없이 Exchange Online에 대한 액세스를 특정 그룹과 Android 및 iOS의 앱으로 제한하는 정책을 만들 수 있습니다.

- **Exchange Online에 대한 앱 보호 조건부 액세스 정책을 만듭니다.** [이러한 정책은](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-exchange-online) 앞서 설명한 앱 보호 정책과 동일한 위치에서 만들어집니다. Exchange Online 액세스가 허용되는 앱을 정의하는 것 외에도 Exchange Online에 대한 연결을 관리하는 사용자 액세스 그룹도 정의해야 합니다.

- 사용자는 Exchange Online에 액세스하도록 정책에서 지원하는 앱을 맨 처음 사용하려고 할 때 **브로커 앱**을 구성해야 합니다. iOS 장치의 경우 브로커 앱은 Microsoft Authenticator 앱이기 때문에 Intune Company Portal 앱을 설치하려면 Android 장치가 필요합니다. [이러한 브로커 앱](https://docs.microsoft.com/intune/deploy-use/use-apps-with-mam-ca)은 장치를 Azure AD에 등록하여 장치 ID 인증을 제공하지만 장치를 관리에 등록하지는 않습니다.

Exchange Online에 대한 조건부 액세스 정책이 있으면 사용자는 Android 장치에 나타난 것처럼, 고유 메일 클라이언트를 사용하여 회사 메일에 액세스하려고 할 때 다음과 비슷한 메일을 받게 됩니다.

![앱 보호 정책 Outlook 앱 요구 사항](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig2.png)

최종 사용자가 메일에서 *지금 시작* 링크를 탭하면 장치의 기본 웹 브라우저가 열리고 https://portal.manage.microsoft.com/OutlookRedirect.aspx가 표시됩니다. 그러면 사용자에게 장치의 앱 스토어에서 무료 Microsoft Outlook 앱을 설치하라는 메시지가 표시됩니다.

### <a name="learn-more"></a>자세한 정보

[EMS(Enterprise Mobility + Security) 사용 시작](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Jan17_HO4-->


