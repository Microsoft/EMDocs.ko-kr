---
title: 수천 개의 응용 프로그램, 하나의 ID
description: 이 문서에서는 Enterprise Mobility + Security를 통해 Azure Active Directory 내의 도구를 활용하여 업계의 모든 웹 기반 응용 프로그램에 걸쳐 작동하는 단일 ID를 제공할 수 있는 방법을 설명합니다.
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.assetid: dd879a14-919e-431b-89b9-c035c83a6899
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: d702935274f7a798018a61188a90b2186d6af831
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196670"
---
# <a name="thousands-of-apps-one-identity"></a>수천 개의 응용 프로그램, 하나의 ID
Azure AD(Azure Active Directory)는 클라우드 리소스와 온-프레미스 리소스 모두에 액세스하는 SaaS(Software as a Service) 응용 프로그램 사용자에게 공통 ID를 제공하여 사용자의 생산성을 개선합니다.

Azure AD는 Box, Twitter, ServiceNow, DocuSign, Workday 등 오늘날 널리 사용되는 대부분의 SaaS 응용 프로그램과 통합됩니다. 안전하고 신뢰할 수 있는 방식으로 모든 디바이스에서 SSO(Single Sign-On) 인증, ID 및 보안 응용 프로그램 액세스 관리를 지원합니다.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?
EMS(Enterprise Mobility + Security)는 ID, 디바이스, 앱, 데이터 등의 4단계 보호 기능으로 디바이스뿐 아니라 그 이상에서 기업 데이터를 기본적으로 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS는 모바일 우선, 클라우드 우선 세계의 핵심 과제 중 하나인, 업계의 모든 웹 기반 응용 프로그램에 걸쳐 작동하는 단일 ID 제공 문제를 해결하도록 도와줍니다.
- 클라우드에 연결된 원활한 인증 환경
- 1000개의 사전 통합 응용 프로그램 또는 사용자 고유 응용 프로그램에 대한 Single Sign-On
- 온-프레미스 응용 프로그램에 대한 보안 원격 액세스
- 클라우드로의 전환 지원


## <a name="recommended-solution"></a>권장 솔루션
Azure AD는 조직이 기존 도구에 대한 기존 투자를 바탕으로 안전하고 생산적인 방식으로 어디에서든 필요한 모든 것에 액세스할 수 있도록 하는 클라우드 ID 및 액세스 관리 솔루션입니다.
### <a name="access-to-single-sign-on-applications"></a>Single Sign-On 응용 프로그램 액세스

Single Sign-On 이전에는 IT 관리자가 조직에서 지원해야 하는 모든 응용 프로그램에 대한 여러 사용자 및 암호를 관리해야 했습니다.

- 사용자가 각 응용 프로그램에 사용자 이름 및 암호를 입력함
- 사용자가 너무 많은 암호를 관리함
- 암호 다시 사용이 일반적임
- 액세스 취소가 매우 어려움

최근 조사에 따르면, 확인된 데이터 위반의 63%가 취약한 암호, 기본 암호 또는 도난당한 암호와 관련이 있습니다.

Single Sign-On을 사용하면 단일 사용자 계정으로 한 번만 로그인하여 업무에 필요한 모든 응용 프로그램 및 리소스에 액세스할 수 있습니다. 로그인한 후에는 두 번째 인증(예: 암호 입력) 없이 필요한 모든 응용 프로그램에 액세스할 수 있습니다.

Azure AD는 다음 세 가지 유형의 Single Sign-On 인증을 지원합니다.

- **Microsoft Azure AD Single Sign-on:** 이 옵션은 페더레이션된 로그온을 사용하여 사용자가 Azure AD에서 사용자 계정 정보를 통해 Salesforce와 같은 타사 응용 프로그램에 자동으로 로그인할 수 있도록 해줍니다.
- **암호 Single Sign-On:** 사용자가 타사 사용자 계정 정보를 사용하여 Azure AD를 통해 타사 SaaS 응용 프로그램에 자동으로 로그인할 수 있도록 해줍니다.
- **기존 Single Sign-on:** 이 옵션은 ADFS(Active Directory Federation Services) 또는 다른 타사 Single Sign-On 공급자를 통한 타사 SaaS Single Sign-On을 지원합니다.

### <a name="how-single-sign-on-works"></a>Single Sign-On 작동 방식
Azure AD는 다음 표준 프로토콜 중 하나를 지원하는 응용 프로그램에서 Single Sign-On을 지원합니다.
- SAML 2.0
- OAuth 2.0/OpenID Connect
- WS-Federation

응용 프로그램은 Azure AD를 해당 ID 공급자로 사용하도록 구성됩니다. 구성된 후에는 더 이상 사용자 이름/암호를 직접 입력할 필요가 없으며, 대신 인증을 위해 ID 공급자로 리디렉션됩니다.

![Azure AD와 여러 응용 프로그램 간에 설정된 트러스트를 보여 주는 그래픽](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig1.png)


### <a name="do-i-still-need-azure-active-directory-federation-services-adfs"></a>Azure ADFS(Active Directory Federation Services)가 여전히 필요합니까?
예. ADFS가 Azure AD에 연결되면 도메인에 가입된 컴퓨터에서 원활한 Single Sign-On이 제공됩니다.
- 사용자에게 웹 기반 로그인 페이지가 표시되지 않습니다.
- 개별 응용 프로그램 트러스트가 Azure AD에서 관리됩니다.

![Azure Active Directory Federation Services를 Azure AD에 연결하여 여러 응용 프로그램에 대한 원활한 Single Sign-On을 제공하는 방법을 보여 주는 그래픽](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig2.png)

### <a name="what-if-an-app-doesnt-support-federated-single-sign-on"></a>응용 프로그램이 페더레이션된 Single Sign-On을 지원하지 않으면 어떻게 됩니까?
SAML/OpenID를 지원하지 않고 Web Form에 사용자 이름 및 암호를 입력하는 기능만 지원하는 응용 프로그램에는 암호 기반 SSO가 최상의 솔루션입니다.
- 응용 프로그램별 자격 증명 집합을 정의하고 Azure AD에 저장할 수 있습니다.
- 공유 액세스를 위해 사용자 또는 그룹에 자격 증명을 할당할 수 있습니다.

### <a name="user-account-provisioning"></a>사용자 계정 프로비전
사용자 계정 프로비전은 응용 프로그램의 로컬 사용자 프로필 저장소에서 사용자 계정 레코드를 생성, 업데이트 및/또는 비활성화하는 작업입니다. 대부분의 SaaS 응용 프로그램 저장소는 사용자의 역할 및 사용 권한을 자체 로컬 사용자 프로필 저장소에 저장합니다.

Azure AD 프로비전 서비스는 사용자를 추가, 업데이트 및 비활성화할 수 있도록 응용 프로그램별로 제공되는 soap/rest 사용자 관리 API에 연결됩니다. 이 서비스는 그룹 동기화를 지원하며, 응용 프로그램에서 Azure AD로 프로필/역할을 가져올 수도 있습니다.

![Azure AD 프로비전 서비스를 soap/rest 사용자 관리 API에 연결하는 방법을 보여 주는 그래픽](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig3.png)

### <a name="the-end-user-experience"></a>최종 사용자 환경
응용 프로그램 액세스 패널은 iOS, Android, Mac 및 Windows를 사용하여 액세스할 수 있는 장치 간 및 브라우저 간 포털입니다. 액세스 패널에 연결하려면 Azure AD에 한 번 인증합니다. 그러면 해당 사용자가 액세스할 수 있는 응용 프로그램 목록이 표시되며, 이 목록에서 한 번의 클릭으로 응용 프로그램을 시작할 수 있습니다. 관리자가 SSO에 대해 응용 프로그램을 구성한 경우 사용자는 다시 인증하지 않고도 응용 프로그램에 액세스할 수 있습니다. Single Sign-On이 인증을 자동으로 해결합니다.

### <a name="bring-your-own-apps"></a>사용자 고유 응용 프로그램 가져오기
Azure AD 응용 프로그램 갤러리에는 조직에 추가할 수 있는 수천 개의 응용 프로그램이 있지만 타사 응용 프로그램을 찾을 수 없는 경우 조직에서 사용할 수 있도록 해당 응용 프로그램을 사용자 지정 응용 프로그램으로 추가할 수 있습니다.

Azure 응용 프로그램 갤러리에 나열되어 있는지 여부에 상관없이 사용자 이름 및 암호 기반 인증 메커니즘을 사용하는 거의 모든 웹 기반 응용 프로그램을 등록할 수 있습니다.

![Azure AD 응용 프로그램 갤러리를 사용하여 조직의 응용 프로그램을 추가하는 방법을 보여 주는 스크린샷](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig4.png)

### <a name="secure-remote-access-to-on-premises-apps"></a>온-프레미스 응용 프로그램에 대한 보안 원격 액세스
[Azure AD 응용 프로그램 프록시](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-enable/)는 온-프레미스에서 호스트되는 웹 응용 프로그램에 대한 SSO(Single Sign-On) 및 보안 원격 액세스를 제공합니다. 여기에는 SharePoint 사이트, Outlook Web Access 또는 다른 모든 LOB 웹 응용 프로그램이 포함될 수 있습니다. 이러한 온-프레미스 웹 응용 프로그램은 O365에서 사용되는 동일한 ID 및 제어 플랫폼인 Azure AD와 통합됩니다.

이 경우 최종 사용자는 네트워크 인프라를 변경하거나 VPN 없이도 O365 및 기타 Azure AD와 통합된 SaaS 응용 프로그램과 동일한 방식으로 온-프레미스 응용 프로그램에 액세스할 수 있습니다.

## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
다음 단계에서는 앞에서 설명한 각 Azure AD 기능을 구현하는 방법을 설명합니다. 각 링크는 조직에서 구현할 여러 지침/단계 집합이 포함된 다양한 문서 집합을 나타냅니다.
1. [응용 프로그램 프록시에서 Single Sign-On 사용](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-sso-using-kcd/)
2. [온-프레미스 응용 프로그램에 대한 보안 원격 액세스 제공](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-get-started/)
   - [Azure AD 응용 프로그램 프록시에서 사용자 지정 도메인 사용](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-custom-domains/)
   - [응용 프로그램 프록시에서 클레임 인식 응용 프로그램 사용](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-claims-aware-apps/)
   - [응용 프로그램 프록시를 사용하여 게시한 앱에 대한 조건부 액세스 사용](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-conditional-access/)
3. [Azure AD로 사용자 고유 앱 가져오기](https://blogs.technet.microsoft.com/enterprisemobility/2015/06/17/bring-your-own-app-with-azure-ad-self-service-saml-configuration-now-in-preview/)

## <a name="additional-resources"></a>추가 리소스
- **Azure.com의 앱 갤러리**
  - https://azure.microsoft.com/marketplace/active-directory/
- **SaaS 응용 프로그램 목록**(통합 기능 포함)
  - https://aadappgallery.azurewebsites.net/Default.aspx?Microsoft_Integrated_Synchronization=on
- **SaaS 응용 프로그램 자습서**
  - https://azure.microsoft.com/documentation/articles/active-directory-saas-tutorial-list/
