---
title: "권장되는 보안 정책 및 구성 - Microsoft 365 Enterprise | Microsoft docs"
description: "보안 메일, 문서 및 앱 정책 및 구성을 배포하기 위한 Microsoft 권장 사항과 핵심 개념을 설명합니다."
author: dougeby
manager: dougeby
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: a7f6ab6765be5462c652feb006839f0839b1136e
ms.sourcegitcommit: 8d42bd1ec3d7bf5f873a7b681b0fea73a748b413
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="recommended-security-policies-and-configurations"></a>권장되는 보안 정책 및 구성

## <a name="introduction"></a>소개
모든 고객 환경에 가장 적합한 유일한 권장 사항은 없지만, 이 문서의 모범 사례와 권장 사항은 직원의 안전성과 생산성을 보장하기 위해 Microsoft 클라우드 내에서 정책 및 구성을 적용하는 방법에 데한 일반적인 Microsoft 권장 사항을 설명합니다.  

**대상 독자** 이 권장 사항은 특히 Azure Active Directory(ID), Microsoft Intune(장치 관리) 및 Azure Information Protection(데이터 보호)를 포함하는 [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) 및 [Microsoft Enterprise Mobility + Security](http://microsoft.com/ems)를 잘 알고 있는 엔터프라이즈 인프라 설계자와 IT 전문가를 위한 것입니다.

**고객 환경** 권장 정책은 전적으로 Microsoft 클라우드 내에서 운영하는 엔터프라이즈 조직 및 인프라가 온-프레미스와 Microsoft 클라우드에 걸쳐 배포된 고객에게 적용됩니다.

**가정** 제공되는 권장 사항 중 다수는 Enterprise Mobility + Security(EMS) E5 구독을 통해서만 사용할 수 있는 서비스를 기준으로 합니다. 제공한 권장 사항은 전체 EMS E5 구독 기능을 가정합니다.

**경고** 사용자의 조직에 이 권장 구성과 달라지는 정책을 적용해야 할 수 있는 특정 권장 사항을 포함하여 규정 또는 기타 준수 요구 사항이 적용될 수 있습니다.  이러한 구성은 지금까지 사용할 수 없었던 사용 제어를 권장합니다.  이러한 제어를 권장하는 이유는 보안과 생산성 간의 균형을 나타내는 것으로 생각하기 때문입니다.  

다양한 조직의 보호 요구 사항을 고려하기 위해 최선을 다했지만 모든 요구 사항 또는 사용자 조직의 모든 특이한 측면을 고려할 수는 없습니다. 이러한 권장 사항을 Microsoft 및 안전하고 생산적인 엔터프라이즈 팀이 정책을 정확하게 적용하는 방법에 대해 어떻게 생각하는지 보여 주는 가이드로 사용하십시오.  

>[!NOTE]
>이러한 권장 사항에서 설명하는 보호 기능을 이해하는 데 필요한 핵심 개념의 개요는 [Microsoft 365 Enterprise 설명서 홈 페이지](index.md)를 참조하세요.
>

## <a name="core-concepts"></a>핵심 개념
실제로 모든 보안 대책이 사용자가 작업을 수행하려고 할 때 불필요한 마찰을 경험하는 조직의 보안 정책을 우회하는 경우를 무시하는 것은 아닙니다. Azure AD SSD(Single-Sign On)는 사용자에 대한 부담을 최소화하려고 합니다. 이 방법으로 사용자는 조직의 액세스 제어 정책을 준수하면서도 생산성을 유지할 수 있습니다.

### <a name="single-sign-on-authentication"></a>Single Sign-On 인증

다음 다이어그램은 일반적인 SSO 인증 흐름을 보여 줍니다.

![최종 사용자 Single Sign-On 환경](./media/policies-configurations/authentication-flow.png)

인증을 시작하려면 클라이언트가 자격 증명(예: 사용자 이름 및 암호) 및/또는 과거에 얻은 SSO 아티팩트를 Azure AD에 제출합니다. SSO 아티팩트는 브라우저의 경우 세션 토큰 또는 많은 응용 프로그램의 경우 새로 고침 토큰일 수 있습니다.

Azure AD에서 자격 증명 및/또는 SSO 아티팩트를 확인하고 모든 적용 가능한 정책을 평가한 후 리소스 공급자에 대한 액세스 토큰(위 다이어그램의 경우 Office 365)을 발급합니다. 또한 Azure AD는 클라이언트가 이후 요청에서 SSO를 구현할 수 있도록 하는 응답의 일부로 SSO 아티팩트를 발급합니다. 클라이언트는 SSO 아티팩트를 저장하고 액세스 토큰을 ID의 증거로 리소스 공급자에게 제출합니다. Office 365가 액세스 토큰을 확인하고 필요한 검사를 수행한 후 문서에 대한 클라이언트 액세스를 허용합니다.

#### <a name="single-sign-on-sso-refresh-tokens"></a>SSO(Single Sign-On) 새로 고침 토큰
SSO는 다양한 방법으로 구현할 수 있습니다. 예를 들어 ID 공급자의 쿠키를 SSO 아티팩트로 사용하여 브라우저 내에서 사용자의 로그인 상태를 저장할 수 있습니다. 그러면 나중에 같은 ID 공급자를 사용하여 응용 프로그램에 자동으로(자격 증명 프롬프트 없이) 로그인을 시도할 수 있습니다.

사용자가 Azure AD를 사용하여 인증하는 경우 사용자의 브라우저 및 Azure AD를 사용하여 SSO 세션이 설정됩니다. 쿠키 형태의 SSO 토큰이 이 세션을 나타냅니다. Azure AD는 영구 및 비영구 두 종류의 SSO 세션 토큰을 사용합니다. 영구 세션 토큰은 로그인할 때 **로그인 유지** 확인란을 선택하면 브라우저에서 영구 쿠키로 저장됩니다. 비영구 세션 토큰은 세션 쿠키로 저장되며 브라우저를 닫을 때 삭제됩니다.

[OpenId Connect](http://openid.net/specs/openid-connect-core-1_0.html) 및 [OAuth 2.0](https://tools.ietf.org/html/rfc6749) 등 최신 인증 프로토콜을 사용할 수 있는 강력한 응용 프로그램의 경우, 새로 고침 토큰을 SSO 아티팩트로 사용하여 SSO를 활성화합니다(앞서 설명한 SSO 쿠키에 더하여). 새로 고침 토큰은 응용 프로그램이 새 액세스 토큰을 요청할 때 인증 서버에 제공됩니다. 새로 고침 토큰은 클레임 및 사용자를 인증할 때 사용한 인증 방법의 종류에 대한 특성을 포함합니다. 예를 들어 사용자가 여러 가지 방법(사용자 이름과 암호 및 전화 기반 인증)을 사용하여 성공적으로 인증된 경우 다단계 인증(MFA) 클레임이 새로 고침 토큰에 제공됩니다. 또한 MFA 유효성 같은 데이터를 포함하는 추가 클레임이 있을 수 있습니다.

새로 고침 토큰을 사용하여 클라이언트는 다른 대화형 인증을 수행할 필요 없이 새 액세스 토큰을 얻을 수 있습니다. 새로 고침 토큰은 액세스 토큰보다 수명이 훨씬 더 길며 새 액세스 및 새로 고침 토큰 쌍을 얻을 수 있습니다. 그 후 새로 얻은 새로 고침 토큰을 계속 사용하여 액세스 및 새로 고침 토큰의 다른 세트를 가져올 수 있습니다. 클라이언트는 새로 고침 토큰 최대 비활성 시간 설정이 만료되거나 새로 고침 토큰 최대 수명이 만료되거나 인증 및 권한 부여 정책 요구 사항이 변경될 때까지 이 SSO 프로세스를 계속합니다. 이 변경은 원본 새로 고침 토큰을 발급하는 동안 이루어집니다. 중요한 사용자 특성 변경, 예를 들어 암호 재설정 시에도 새 인증 토큰을 생성해야 합니다. 클라이언트는 더 계속하려면 새 대화형 인증을 수행해야 합니다. 기본적으로 이는 클라이언트가 지금까지 경험하지 못한 SSO 프로세스의 중단을 의미합니다.

#### <a name="conditional-access"></a>조건부 액세스
응용 프로그램에 대한 인증 서비스 역할을 하는 Azure AD는 액세스하려는 리소스에 적용되는 조건부 액세스 정책에 대한 평가를 기반으로 액세스 토큰을 발급할지 여부를 결정합니다. 정책 요구 사항이 충족되면 액세스 토큰 및 업데이트된 새로 고침 토큰이 발급됩니다. 정책이 충족되지 않은 경우 사용자는 정책을 충족하는 방법에 관한 지침을 받거나 다단계 인증(MFA)을 포함한 추가 단계를 완료해야 합니다. MFA가 완료된 후 MFA 클레임이 결과 새로 고침 토큰에 추가됩니다.  

새로 고침 토큰의 클레임은 시간이 경과함에 따라 누적됩니다. 일부 클레임은 만료 타임라인을 가지고 있으며, 해당 타임라인이 경과한 후에는 더 이상 권한 부여 확인 중에 고려되지 않습니다. 가끔 이러한 상황 때문에 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 조건부 액세스 정책이 익스트라넷 위치에서 들어오는 인증 시도에 대해 MFA를 요구하도록 구성된 경우를 생각해 보겠습니다. 이 경우 사용자는 가끔 익스트라넷에서 리소스에 액세스할 때 예상한 MFA 프롬프트를 받지 않을 수 있습니다. 이 문제의 예상 원인은 사용자가 이전에 인트라넷을 떠나기 직전에 MFA를 수행했기 때문일 수 있습니다. 그러므로 사용자의 액세스 토큰에 유효한 MFA 클레임이 있습니다. 이 MFA 클레임은 정책 요구 사항을 충족하므로 Azure AD는 추가 MFA 요청을 통해 사용자에게 프롬프트를 표시하지 않습니다.

#### <a name="token-lifetime-policy"></a>토큰 수명 정책
토큰의 개별 클레임이 만료된 후 토큰 자체는 만료 시간을 가지고 있습니다. 앞에서 지적했듯이 만료된 토큰은 SSO 환경이 중단될 수 있는 한 가지 이유입니다. [토큰 수명 정책](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)을 사용하여 발급한 토큰의 수명을 설정할 수 있습니다. 위에서 유추할 수 있듯이, SSO 세션의 윤곽을 정의하는 것은 캡처하기가 더 어렵습니다. 예를 들어 중단된 것 같은 여러 요인만큼이나 많은 앱이 SSO 세션의 수명에 영향을 미칠 수 있습니다.

>[!NOTE]
>Azure AD 전역 관리자는 새로 고침 토큰의 유효성 및 비활성 기간을 제어할 수 있습니다. 설정을 사용하는 액세스 토큰 및 클레임에 관한 정보는 [Azure Active Directory에서 구성할 수 있는 토큰 수명](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) 문서에서 설명했습니다.
>

#### <a name="primary-refresh-tokens"></a>기본 새로 고침 토큰
지금까지 이 문서에서는 단일 클라이언트 상황에서 SSO가 작동하는 방법을 설명했지만 이 방법은 단일 앱 내에서 SSO를 경험하기에 부족합니다. 현재 사용자는 Microsoft Office 같은 동일한 응용 프로그램 패키지 내의 여러 응용 프로그램에 걸쳐 대화형 워크플로를 경험합니다. 또한 사용자는 내부에서 개발한 업무 계열(LOB) 응용 프로그램을 포함하여 서로 무관한 응용 프로그램을 오가며 액세스해야 합니다.

일반적으로 Windows 통합 인증(Kerberos)을 사용하여 도메인에 가입된 Windows 장치는 여러 응용 프로그램과 리소스에 걸쳐 높은 수준의 SSO 경험을 구현합니다. 이러한 앱은 Internet Explorer 또는 Edge 등 지원되는 브라우저를 포함합니다. Azure AD 영역에도 기본 새로 고침 토큰(PRT) 형태의 유사한 상황이 있습니다. 이 권한 있는 토큰은 클라이언트 엔터티의 선택 집합에만 사용할 수 있습니다(플랫폼 시스템 구성 요소 등). 그 후 엔터티를 사용하여 다른 클라이언트 응용 프로그램에 대한 인증 액세스를 중개할 수 있으므로 원활한 SSO 경험을 제공할 수도 있습니다. [iOS](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-ios) 및 [Android](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-android) 장치의 Office 365 사용자는 인증 브로커 기능을 적용하여 필수 인증 수를 줄이기 위해 추가 작업을 해 왔습니다. 이 기능은 Microsoft Authenticator 및 Intune 회사 포털 앱에 기본 제공됩니다.

>[!NOTE]
>이 문서에서 설명하는 권장 사항은 이러한 앱(Microsoft Authenticator 또는 Intune 회사 포털) 중 하나를 사용자의 iOS 또는 Android 장치에 배포한 것으로 가정합니다.

### <a name="multi-factor-authentication"></a>Multi-factor Authentication
다단계 인증(MFA)은 인증 주체가 ID에 관한 여러 증거 또는 증거의 조각을 제공하므로 인증 주체에 대해 높은 수준의 신뢰를 제공합니다. 이러한 증거는 주체와 기관만이 알고 있는 사전 설정된 비밀이거나 주체만이 소유할 것으로 예상되는 물리적 엔터티일 수 있습니다. MFA는 일반적으로 단계별로 수행됩니다. 먼저 암호를 사용하여 ID를 설정한 다음 두 번째 요인으로 다른(악의적 공격에 덜 취약한) 인증 방법을 요구합니다.

다른 기관은 MFA를 약간 다르게 해석하거나 강력한 인증을 적용할 수 있습니다. 예를 들어 어떤 기관(또는 더 구체적으로 해당 기관에 대한 정책을 구성하는 관리자)은 물리적 스마트 카드 기반 인증을 MFA로 해석할 수 있습니다. 이 상황은 엄격한 말하는 스마트 카드 인증이 단일 단계 인증이더라도 발생할 수 있습니다.

스마트 카드를 사용하기 위해 물리적 스마트 카드 요구와 PIN(비밀) 입력 요구의 조합을 MFA로 해석할 수 있습니다. 그러나 조직이 흔히 더 부담스러운 인증 방법을 수행해야 하는 방법 면에서 더 관대할 수 있습니다. 이 경우 일반적으로 강력한 인증을 요구하는 리소스의 경우 강력한 인증 사이에 발생하는 일반 인증이 유효한 것으로 생각할 수 있습니다. 예를 들어 어떤 조직에서는 사용자가 몇 시간 또는 몇 일마다 MFA를 수행하도록 요구하는 것이 적절할 수도 있습니다. 시간은 보호하는 리소스의 중요도 및 리소스에 액세스를 시도하는 사용자의 물리적 위치가 변하지 않은 기간에 따라 달라집니다.

Azure AD 및 AD FS는 MFA 클레임을 사용하여 MFA를 통해 인증을 수행하는지 여부를 나타냅니다. 기본적으로 Azure AD는 [Azure MFA](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) 또는 [비즈니스용 Windows Hello](https://docs.microsoft.com/windows/access-protection/hello-for-business/hello-identity-verification)을 사용하여 인증을 수행할 때 MFA 클레임을 포함한 토큰을 발급합니다. 페더레이션 시나리오에서 Azure AD는 AD FS 등 페더레이션된 ID 공급자의 MFA 클레임을 존중하고 토큰의 MFA 클레임을 통해 전달합니다.

## <a name="recommended-client-configurations"></a>권장되는 클라이언트 구성
이 섹션에서는 조건부 액세스에 대한 기술적인 필수 구성 요소뿐만 아니라 사용자에게 최상의 SSO 환경을 제공하기 위해 Microsoft에서 권장하는 기본 플랫폼 클라이언트 구성에 대해서도 설명합니다.

### <a name="windows-devices"></a>Windows 장치
Azure는 온-프레미스와 Azure AD에 대해 모두 가장 원활한 SSO 경험을 제공하도록 설계되었으므로 Windows 10(버전 1703 이상)을 사용하는 것이 좋습니다. 회사 또는 학교에서 발급한 장치는 Azure AD에 직접 가입하도록 구성하거나 조직이 온-프레미스 AD 도메인 가입을 사용하는 경우 해당 장치를 [Azure AD에 자동으로 등록하도록 구성](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)해야 합니다.

BYOD Windows 장치의 경우 사용자는 "회사 또는 학교 계정 추가"를 사용할 수 있습니다. 참고로 Windows 10의 Chrome 브라우저 사용자는 사용자가 Edge/IE와 같은 원활한 로그인 경험을 얻을 수 있도록 [확장 기능을 설치](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)해야 합니다. 또한 조직이 도메인에 가입된 Windows 7 장치를 가지고 있는 경우 Azure AD에 장치를 등록하려면 Windows 10이 아닌 컴퓨터에 대해 Microsoft Workplace Join [패키지를 설치](https://www.microsoft.com/download/details.aspx?id=53554)할 수 있습니다.

### <a name="ios-devices"></a>iOS 장치
조건부 액세스 또는 MFA 정책을 배포하기 전에 사용자 장치에 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 적어도 사용자에게 회사 또는 학교 계정을 추가하여 Azure AD에 [장치를 등록하라고 요구할 때](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/multi-factor-authentication-end-user-first-time) 또는 Intune 회사 포털 앱을 설치하여 사용자의 장치를 관리 대상으로 등록할 때 앱을 설치해야 합니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

### <a name="android-devices"></a>Android 장치
조건부 액세스 정책을 배포하기 전에 또는 특정 인증 시도 중에 요구하는 경우 사용자가 [Intune 회사 포털 앱](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) 및 [Microsoft Authenticator 앱](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)을 설치하는 것이 좋습니다. 앱 설치 후 사용자에게 Azure AD에 등록하거나 사용자의 장치를 Intune에 등록할 것을 요구할 수 있습니다. 이는 구성된 조건부 액세스 정책에 따라 달라집니다.

또한 Intune MDM 정책에 의해 메일 계정을 관리 및 보호할 수 있도록 회사 소유 장치(COD)를 Android for Work 또는 Samsung Knox를 지원하는 OEM 및 버전에 대해 표준화하는 것이 좋습니다.

## <a name="security-guidelines"></a>보안 지침
이 섹션은 뒤의 섹션에 제공한 권장 사항을 구현할 때 따라야 하는 일반 보안 지침을 포함합니다.

### <a name="security-and-productivity-trade-offs"></a>보안과 생산성의 절충
보안과 생산성을 잘 절충해야 합니다. 이러한 절충에 대한 이해를 돕기 위해 보안-기능-유용성/사용 편의성(SFU) 보안 3원소가 널리 사용됩니다.

![보안과 생산성의 절충](./media/policies-configurations/security-triad.png)

제공된 권장 사항은 다음 SFU 보안 3원소 원칙을 기준으로 합니다.

* 대상 고객을 안다 - 작업 기능/보안 수준별로 유연하게
* 보안 정책을 적시에 적용하고 의미 있도록 함

### <a name="administrators-versus-users"></a>관리자 대 사용자
관리 계정을 가지고 있거나 일시적으로 관리 계정 권한을 받을 자격이 있는 모든 사용자를 포함하는 보안 그룹을 만드는 것이 좋습니다. 그런 다음 이러한 보안 그룹을 사용하여 Azure AD 및 Office 365 관리자 고유의 조건부 액세스 정책을 정의해야 합니다.  

제공된 정책 권장 사항은 계정과 연결된 권한을 고려합니다. [Office 365 관리자](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) 역할은 Office 365 서비스보다 훨신 더 많은 권한을 가지고 있습니다. 그러므로 이러한 계정에 대한 Microsoft의 정책 권장 사항은 일반 사용자 계정의 경우보다 더 엄격합니다. 관리자를 참조하는 모든 정책은 Office 365 관리 계정에 대해 권장되는 정책을 나타냅니다.

### <a name="reduce-the-number-of-accounts-with-persistent-admin-access"></a>영구 관리자 액세스를 가진 계정 수 줄이기
Azure AD Privileged Identity Management를 사용하여 영구 관리 계정 수를 줄입니다. 또한 Office 365 관리자가 관리용이 아닌 일반적 사용에 대해 별도의 사용자 게정을 두고 자신의 직무 기능과 연결된 작업을 완료하기 위해 필요한 경우에만 관리 계정을 사용하는 것이 좋습니다.

## <a name="tiers-of-security-and-protection"></a>보안 및 보호 계층
대부분의 조직은 보안 및 데이터 보호에 관한 구체적 요구 사항을 가지고 있습니다. 이러한 요구 사항은 산업 부문 및 조직 내의 직무 기능에 따라 달라집니다. 예를 들어 법무 부서 및 Office 365 관리자는 다른 업무 단위 사용자에게 필요하지 않은 자신의 메일 서신에 대한 추가 보안 및 정보 보호 제어가 필요할 수 있습니다.

또한 각 산업마다 자체의 전문화된 규정을 가지고 있습니다. 모든 가능한 보안 옵션 또는 산업 부문이나 직무 기능에 따른 권장 사항을 제공하는 것보다 요구의 세분성을 기반으로 적용할 수 있는 [기준, 중요 및 높은 규제](https://go.microsoft.com/fwlink/p/?linkid=841656) 세 계층의 보안 및 보호에 대한 권장 사항을 제공했습니다.  

**기준**. 본인의 데이터에 액세스하는 ID와 장치뿐만 아니라 데이터를 보호하기 위해서도 최소 표준을 설정하는 것이 좋습니다. 기준 권장 사항을 따르면 많은 조직의 요구를 충족하는 강력한 기본 보호를 제공할 수 있습니다.

**중요**. 일부 고객은 더 높은 수준으로 보호해야 하거나 모든 데이터를 이처럼 더 높은 수준에서 보호해야 하는 데이터의 하위 집합을 가지고 있습니다. Office 365 환경의 모든 또는 특정 데이터 집합에 대해 증가된 보호를 적용할 수 있습니다. 중요 데이터에 액세스하는 ID와 장치를 유사한 보안 수준으로 보호하는 것이 좋습니다.

**높은 규제**. 일부 조직에는 높은 수준의 대외비, 거래 비밀 또는 규제 대상 데이터인 아주 적은 양의 데이터가 있을 수 있습니다. Microsoft는 ID와 장치에 대한 추가된 보호를 포함하여 조직이 이러한 요구 사항을 충족하는 데 도움이 되는 기능을 제공합니다.

### <a name="default-protection-mechanism-recommendations"></a>기본 보호 메커니즘 권장 사항
다음 테이블은 이전에 정의한 각 보안 및 보호 계층에 대한 기본 보호 메커니즘 권장 사항을 포함합니다.

|보호 메커니즘|기준|중요|높은 규제|
|:-------------------|:-------|:--------|:---------------|
|**MFA 강제 적용**|중간 이상 로그인 위험에 대해|낮음 이상 로그인 위험에 대해|모든 새 세션에 대해|
|**암호 변경 강제 적용**|높은 위험 사용자의 경우|높은 위험 사용자의 경우|높은 위험 사용자의 경우|
|**Intune 응용 프로그램 보호 강제 적용**|예|예|예|
|**Intune 등록(COD)**|호환되거나 도메인에 가입된 장치 필요|호환되거나 도메인에 가입된 장치 필요|호환되거나 도메인에 가입된 장치 필요|

### <a name="device-ownership"></a>장치 소유권
위 테이블은 많은 조직이 작업 공간 전체에 걸쳐 모바일 생산성을 높이기 위해 개인 또는 BYOD(Bring Your Own Device)뿐만 아니라 회사 소유 장치(COD) 혼합도 지원하는 추세를 반영합니다. Intune 앱 보호 정책은 COD와 BYOD에 대해 모두 Outlook 모바일 앱과 다른 Office 모바일 앱에서 메일을 빼내지 못하도록 보호합니다.  

회사 소유 장치는 추가 보호와 제어를 적용하려면 Intune에 의해 관리하거나 도메인에 가입해야 합니다.  데이터 중요도에 따라 조직이 특정 사용자 모집단 또는 특정 앱에 대해 BYOD를 허용하지 않도록 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

 [일반 ID 및 장치 액세스 정책 배포](identity-access-policies.md)
