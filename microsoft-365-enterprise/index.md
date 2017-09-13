---
title: "Microsoft 365 Enterprise 서비스 개요 | Microsoft Docs"
description: "이 콘텐츠는 Microsoft 365 Enterprise에 대한 개요와 엔터프라이즈 사용 권장을 제공합니다."
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: fd15e4215ec60a510cb5d6892b53f11f94fec84d
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2017
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 Enterprise 서비스 및 개념
Microsoft 365 Enterprise는 대규모 조직용으로 설계되었으며 Office 365 Enterprise, Windows 10 Enterprise 및 EMS를 통합합니다.

## <a name="microsoft-365-services-overview"></a>Microsoft 365 서비스 개요

이 단원에서는 Microsoft 365 Enterprise에 포함된 EMS 및 Office 365 서비스에 대한 개요를 제공하고 조직의 필요에 따라 가장 잘 활용하는 방법을 이해하는 데 필요한 핵심 개념도 소개합니다. 이러한 서비스는 Microsoft 클라우드 엔터프라이즈 관리자가 회사 직원의 ID와 장치를 보호할 뿐만 아니라 회사 데이터(전송 중인 데이터 및 미사용 데이터 둘 다) 자체에 대한 액세스도 제어할 수 있는 기능을 제공합니다.

|서비스|설명|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD는 다단계 인증, 장치 등록, 셀프 서비스 암호 관리, 셀프 서비스 그룹 관리, 역할 기반 액세스 제어, 응용 프로그램 사용 모니터링, 다양한 감사, 보안 모니터링 및 경고 등 전체 ID 관리 기능을 제공합니다.|
|[Azure AD ID 보호](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|이 서비스를 사용하면 조직의 ID에 영향을 미치는 잠재적인 취약점을 검색하고 낮음, 보통 및 높음 로그인 위험 및 사용자 위험에 대해 조건부 액세스 정책을 통해 자동화된 응답을 구성할 수 있습니다.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|이 서비스를 사용하면 조직은 권한 있는 작업에 영구 액세스 권한이 있는 사용자 수를 최소화할 수 있습니다. Azure AD Privileged Identity Management는 적격 관리자 개념을 소개합니다. 적격 관리자는 매일이 아니라 가끔 권한 있는 액세스가 필요한 사용자여야 합니다. 역할은 사용자가 액세스를 필요로 할 때까지 비활성화 상태이다가 활성화 프로세스를 완료하면 미리 결정된 시간 동안 활성 관리자가 됩니다.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection은 EMS E5 제품의 일환으로 제공되는 클라우드 기반 솔루션으로 조직에서 문서와 메일을 분류하고 레이블을 지정하며 보호하는 데 도움이 됩니다. 이 기능은 규칙 및 조건을 정의하는 관리자는 자동으로, 사용자는 수동으로 수행할 수 있으며, 사용자가 권장 사항을 제공받은 경우에는 자동 또는 수동으로 수행할 수 있습니다. Azure Information Protection 레이블을 사용하여 문서와 전자 메일을 분류할 수 있습니다. 이 작업을 수행하면 데이터가 저장된 위치나 데이터를 공유한 사용자가 누구인지와 관계없이 항상 분류를 식별할 수 있게 됩니다. <br><br>Azure Information Protection 정책 설정은 [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)로 보호됩니다. 레이블이 적용되는 방법과 마찬가지로 Rights Management를 사용하여 적용된 보호 기능은 조직, 네트워크, 파일 서버, 응용 프로그램 내/외의 위치와 관계없이 문서와 메일에 계속 적용됩니다.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune은 직원이 회사 데이터를 보호하면서 생산성을 높일 수 있도록 하는 클라우드 기반 엔터프라이즈 이동성 관리(EMM) 서비스입니다. Intune은 ID 및 액세스 제어에 대해 Azure AD와 긴밀하게 통합되며 장치 및 응용 프로그램 관리에 사용됩니다. [Intune의 장치 관리](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) 기능은 Windows PC를 비롯하여 사용자의 장치를 구성하고 보호하는 데 사용됩니다. <br><br>Intune 장치 관리 기능은 사용자가 개인 휴대폰, 태블릿 또는 PC를 등록할 수 있는 [BYOD(Bring Your Own Device)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 등록과 자동 등록, 공유 장치 또는 사전 승인된 등록 요구 사항 구성 같은 관리 시나리오를 사용할 수 있는 [COD(회사 소유 장치)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 등록을 모두 지원합니다. 추가 보안을 위해 장치를 등록하려면 MFA가 필요할 수 있습니다. 관리로 등록되면 Intune은 장치 기능 및 설정을 구성하여 회사 리소스에 대해 보안 액세스를 사용할 수 있습니다.|


## <a name="important-concepts-to-understand"></a>이해해야 할 중요한 개념
숙지해야 할 핵심 개념 및 EMS 기능이 아래 표에 설명되어 있습니다.

|핵심 개념|설명|
|------------|-----------|
|[Azure MFA(Multi-Factor Authentication)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Microsoft의 2단계 인증 솔루션인 Azure MFA를 사용하면 간단한 로그인 프로세스에 대한 사용자의 요구를 충족하면서 데이터 및 응용 프로그램에 안전하게 액세스할 수 있습니다. 전화 통화, 문자 메시지 또는 모바일 앱 인증 등 다양한 인증 방법을 통해 강력한 인증을 제공합니다.|
|[Azure AD 조건부 액세스](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD의 이 기능을 사용하면 특정 조건에 따라 사용자의 환경에서 클라우드 앱에 대한 액세스에 컨트롤을 적용할 수 있습니다. 컨트롤을 사용하여 액세스에 대해 추가 요구 사항을 연결하거나 차단할 수 있습니다. 조건부 액세스 구현은 정책을 기반으로 합니다.|
|[Exchange Online DLP(데이터 손실 방지)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Exchange Online 계획 2 및 Office 365 구독의 고급 기능으로 사용할 수 있는 Exchange Online DLP(데이터 손실 방지) 정책을 사용하면 조직은 Office 365에서 중요한 정보를 식별, 모니터링 및 자동으로 보호할 수 있습니다.<br><br>Exchange Online DLP 정책을 사용하여 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive 등의 여러 위치에서 중요한 정보를 식별할 수 있습니다. 예를 들어 이러한 정책을 통해 중요한 정보를 포함하는 문서를 식별하거나 중요한 정보를 조직 외부의 사용자와 실수로 공유하는 것을 방지할 수 있습니다.|
|[Exchange 메일 흐름/전송 규칙](https://support.office.com/en-US/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|전송 규칙이라고도 하는 Exchange 메일 흐름 규칙은 조직을 통해 전달되는 메시지에서 특정 조건을 확인하고 메시지에 특정 조건을 적용합니다. 메일 흐름 규칙은 여러 메일 클라이언트에서 사용할 수 있는 받은 편지함 규칙과 비슷합니다. 메일 흐름 규칙과 Outlook 같은 클라이언트 응용 프로그램에 설정하는 규칙 간의 주요 차이점은 메시지가 배달된 후가 아니라 메시지를 전송 중일 때 메일 흐름 규칙이 메시지에 적용된다는 점입니다. 또한 메일 흐름 규칙에는 여러 유형의 메시지 정책을 구현하는 데 유연성을 제공하는 다양한 조건, 예외 및 동작이 포함됩니다.|
|[Intune 모바일 장치 관리](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune은 모바일 운영 체제에서 사용할 수 있는 프로토콜 또는 API를 사용하여 MDM(모바일 장치 관리)을 제공합니다. 여기에는 IT 팀에서 회사 서비스에 액세스하는 장치의 인벤토리를 관리할 수 있도록 장치를 관리에 등록, 회사 보안 및 상태 표준을 준수하도록 장치 구성, 회사 서비스에 액세스하기 위한 인증서 및 Wi-Fi/VPN 프로필 제공, 장치의 회사 표준 규정 준수에 대한 보고 및 측정, 관리되는 장치에서 회사 데이터 제거 같은 작업이 포함됩니다.|
|[Intune 앱 보호 정책](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Intune 앱 보호 정책은 장치를 관리에 등록하거나 등록하지 않고 모바일 앱에서 회사의 데이터를 보호하기 위해 사용할 수 있습니다. 실제로 사용자의 모바일 장치는 [Intune으로 Office 365 정보를 보호](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)하면서 Microsoft가 아닌 타사의 다른 MDM 솔루션으로 관리할 수 있습니다. 직원의 생산성을 유지하는 동시에 의도했거나 의도하지 않은 데이터 손실을 방지할 수도 있습니다. 앱 수준 정책을 구현하면 회사 리소스에 대한 액세스를 제한하고 IT 부서에서 데이터를 계속 관리하도록 할 수 있습니다.|
|[Azure AD 토큰 수명](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Azure AD(Active Directory)에서 발급한 토큰의 수명을 지정할 수 있습니다. 조직의 모든 앱, 다중 테넌트(여러 조직) 응용 프로그램 또는 조직의 특정 서비스 주체에 대해 토큰 수명을 설정할 수 있습니다.|
|Microsoft ID 브로커|Microsoft는 여러 공급업체의 응용 프로그램에서 자격 증명 브리징을 허용하는 모든 모바일 플랫폼용 응용 프로그램을 제공하고, 자격 증명의 유효성을 검사하는 단일 보안 위치를 필요로 하는 향상된 특별 기능을 허용합니다. 이러한 기능을 브로커라고 합니다. iOS 및 Android에서 이러한 브로커는 Microsoft Authenticator 및 Intune 회사 포털 앱을 통해 제공됩니다. Windows 10에서 이 기능은 운영 체제에 기본 제공된 계정 선택(기술적으로 웹 인증 브로커라고 함)에 의해 제공됩니다.|

## <a name="security-best-practices-and-recommendations"></a>보안 모범 사례 및 권장 사항
모든 고객 환경에 꼭 맞는 단일 권장 사항은 없지만 [권장 보안 정책 및 구성](microsoft-365-policies-configurations.md) 문서에서는 이해가 필요한 중요 보안 모범 사례 개념을 소개합니다. 또한 직원들의 보안과 생산성을 모두 유지하기 위해 Microsoft 클라우드 내에서 정책 및 구성을 적용하는 방법에 대한 일반적인 Microsoft 권장 사항에 대해서도 다룹니다.

### <a name="baseline-recommended-security-policies-and-configurations"></a>권장되는 보안 정책 및 구성
[일반 ID 및 장치에 액세스 정책 권장 사항](identity-access-policies.md)에서는 Microsoft 365 Enterprise를 보호하기 위한 일반적인 권장 사항에 대해 설명합니다. 조건부 액세스에 대한 기술적인 필수 구성 요소뿐만 아니라 사용자에게 최상의 SSO 환경을 제공하기 위해 Microsoft에서 권장하는 기본 플랫폼 클라이언트 구성에 대해서도 설명합니다.

### <a name="exchange-online-access-policies"></a>Exchange Online 액세스 정책
[이메일 보호를 위한 정책 권장 사항](secure-email-recommended-policies.md)에서는 최신 인증 및 조건부 액세스를 지원하는 조직의 메일 및 메일 클라이언트를 보호하는 데 도움이 되는 Microsoft 권장 사항을 제공합니다. [일반 ID 및 액세스 권장 사항](identity-access-policies.md)에 추가되는 내용입니다.

### <a name="sharepoint-online-access-policies"></a>SharePoint Online 액세스 정책
[일반 ID 및 액세스 권장 사항](identity-access-policies.md)과 [이메일 보호를 위한 정책 권장 사항](secure-email-recommended-policies.md)과 함께 [SharePoint Online 파일 액세스](sharepoint-file-access-policies.md)를 보호하기 위해 제공되는 권장 사항입니다. 이 문서에서는 Exchange Online 이메일과 SharePoint Online 파일 액세스를 모두 보호하기 위해, 만들어야 하는 새로운 정책과 기존 정책의 수정 방법을 설명합니다.

## <a name="learn-more"></a>자세한 정보
[Microsoft 365 Enterprise 제품 페이지](https://www.microsoft.com/microsoft-365/enterprise)
