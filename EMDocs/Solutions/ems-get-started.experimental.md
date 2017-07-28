---
title: "EMS(Enterprise Mobility + Security) 사용 시작 | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 11/10/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 9938ab0e-19b8-49a2-91b5-61d69eb3dc01
ms.reviewer: mhamerof
ms.suite: ems
ms.custom: advanced-threat-analytics,cloud-app-security,information-protection,microsoft-identity-manager,microsoft-intune,rights-management
ms.openlocfilehash: 7f82e8b0644765fc8cc14024cd65ef99733f1ecb
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="start-using-enterprise-mobility--security"></a>EMS(Enterprise Mobility + Security) 사용 시작

디지털 전환을 모색하는 조직은 새로운 위협과 도전으로부터 스스로를 보호해야 하는 한편, IT는 계속해서 효율을 추구하고 적은 노력으로 더 많은 성과를 달성해야 한다는 요구를 받고 있습니다. 또한 클라우드 우선 모바일 중심의 세계에서 사용자는 어느 위치에서 어떤 장치로든 생산성을 높일 수 있어야 합니다. EMS로 다음에 도움이 되는 전체적인 솔루션을 얻을 수 있습니다.

- **클라우드에서 ID + 액세스를 제어합니다**. 장치, 데이터 센터, 클라우드에서 ID 및 SSO를 중앙에서 관리합니다.
- **ID 기반의 보안을 이용합니다**. 오늘날의 고급 공격에 대한 포괄적이고 지능적인 보호를 제공합니다.
- **모바일 장치 + 앱을 관리합니다**. iOS, Android 및 Windows에서 앱과 데이터를 안전하게 관리합니다.
- **사용자 정보를 보호합니다**. 회사 데이터를 지능적으로 보호하고 보안 공동 작업을 사용하도록 설정합니다.

EMS를 통해 IT가 사람들이 선호하는 안전하고 경계 없는 생산성을 어떤 방식으로 확실하게 제공할 수 있는지에 대해 자세히 알아봅니다. 이러한 예제 시나리오는 온-프레미스에서 클라우드로 전환할 때 EMS를 시작하고, 클라우드 보안 및 보호를 활용하고, 마지막으로 클라우드에서 전체 서비스를 제공하는 데 도움이 됩니다.

## <a name="transition-from-on-premises-to-the-cloud"></a>온-프레미스에서 클라우드로 전환
EMS는 많은 비즈니스 요구에 따라서 그리고 해당 기능에 더 친숙해짐에 따라 사용할 수 있는 서비스와 기능으로 구성됩니다.

### <a name="establish-azure-ad-identity"></a>Azure AD ID 설정
모든 것은 클라우드 ID로 시작되므로 가장 먼저 해야 할 일은 조직의 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) 상태를 설정하는 것입니다. Microsoft의 플랫폼 및 보안 그래프를 사용하여 고급 위협으로부터 사용자 ID, 클라우드 앱 및 온-프레미스 환경을 보호할 수 있습니다.

클라우드에서 이를 완벽하게 수행할 수도 있고 [현재 Windows Server Active Directory 개체를 Azure Active Directory와 동기화](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)하여 온-프레미스 ID 관리에 대한 기존 투자를 활용할 수도 있습니다.


### <a name="protect-your-organization-at-the-front-door"></a>첫 번째 관문에서 조직 보호
과거에는 전형적인 보안 솔루션으로 회사를 충분히 보호할 수 있었습니다. 그렇지만 모바일 산업이 증가하면서 공격 가능 범위가 커지고, 클라우드로 전환하면서 다른 사용자, 장치, 앱 및 데이터와의 직원 상호 작용이 훨씬 더 복잡해졌습니다. 이제 회사를 진정으로 보호하기 위해서는 온-프레미스 및 클라우드에서 발생하는 모든 종류의 위협으로부터 보호하고, 이러한 위협을 감지하고 대처할 수 있는[전체적이고 혁신적인 보안 접근 방법](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-front-door)을 적용해야 합니다.

### <a name="start-managing-devices"></a>장치 관리 시작
오늘날에는 대부분 정보 근로자가 모바일을 사용하여 모바일 장치에서 나오는 생산성은 경쟁력을 갖추는 데 필수적입니다. 이러한 직원은 어디에서 언제든지 모든 회사 앱 및 데이터에 원활하게 액세스할 수 있어야 합니다. 회사 데이터가 안전하고 관리 비용은 적어야 합니다. IT는 회사 소유의 CYOD(Choose Your Own Device)부터 업무에 이용되는 개인 소유의 장치인 BYOD(Bring Your Own Device)까지 기업의 복잡한 장치를 관리해야 합니다.

**회사 소유 장치를 발급**합니다. Intune은 Apple 장치 등록 프로그램 및 Samsung KNOX 모바일 보안 플랫폼을 포함하여 오늘날 시장에서 주요 회사 장치 관리 플랫폼으로 통합된 대량 프로비전 및 관리 솔루션을 제공함으로써 조직에서 [회사 소유의 장치를 발급](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices)하는 데 도움을 줄 수 있습니다. Intune을 사용하여 장치 구성을 중앙 집중적으로 제작하면 고도로 자동화할 수 있는 회사 장치를 프로비전할 수 있습니다.

열려 있지 않은 iPhone 상자를 직원에게 전달한다고 상상해 보세요. 직원은 iPhone을 켜고 자신을 인증해야 하는 회사 브랜드 설치 흐름을 진행합니다. iPhone은 보안 정책(하드 드라이브, 장치 PIN 등 암호화), 메일/Wi-Fi/VPN/인증서 프로필 및 앱의 기준 집합으로 원활하게 구성됩니다. 그런 다음 직원은 Intune 회사 포털 앱을 시작하여 사용할 수 있는 선택적 회사 앱에 액세스합니다.

**사용 제한된 공유 장치 솔루션을 사용 설정**합니다. 작업자는 모바일 기술을 점점 더 많이 사용하고 있습니다. 예를 들어 이제 공유 태블릿은 소매 대리점 직원에게 일상적입니다. 판매를 처리하거나 즉시 인벤토리를 확인하는 경우 태블릿은 고객 상호 작용에 큰 도움이 됩니다. 이 경우에 사용자 경험의 단순함이 중요합니다. 따라서 태블릿은 일반적으로 직원이 상호 작용할 수 있는 유일한 것이 단일 기간 업무 앱인 경우와 같이 사용이 제한된 모드에서 직원에게 전달됩니다. Intune을 사용하면 이 사용 제한 모드에서 실행되도록 구성할 수 있는 이러한 공유 iOS 및 Android 태블릿을 대량으로 프로비전 및 보호하고 중앙에서 관리할 수 있습니다.

**조직 내 BYOD 프로그램 사용 설정**. BYOD는 하드웨어 비용 절감 또는 직원에 대한 모바일 생산성 선택 항목을 증가하는 수단으로 조직 사이에 널리 사용되고 있습니다. 기업이 회사 소유 장치를 사용하는 기존 모델에서 변화를 추구할 때는 [BYOD 프로그램을 실행하는 방법을 결정](https://docs.microsoft.com/enterprise-mobility-security/solutions/byod-design-considerations-guide)하여 직원들이 일부 업무 작업에 개인 장치를 사용할 수 있게 해야 합니다.

요즘 모든 사람들이 개인 전화를 갖고 있으므로 하나 더 갖고 다니더라도 좋을 것입니다. 가장 큰 문제는 직원이 관리에 자신의 개인 장치를 등록하도록 유도하는 것입니다. IT 부서가 자신의 장치를 사용하여 무엇을 보고 수행하는지 우려하기 때문입니다. 장치 등록이 유용한 옵션이 아닌 경우 Intune은 단순히 [회사 데이터를 포함하는 앱을 관리](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)하는 대체 BYOD 접근 방식을 제공합니다. Intune은 의심스러운 앱이 회사 및 개인 데이터에 액세스하더라도 Office 모바일 앱의 경우와 마찬가지로 회사 데이터를 보호합니다.

**비즈니스, 최종 사용자 및 IT 요구에 따라 Windows 10 배포 및 관리 전략을 수립합니다**. Windows 10은 Windows 7 및 Windows 8.1에 도입된 기술을 토대로 새로운 배포 기능, 시나리오 및 도구를 제공하는 동시에 운영 체제를 최신 상태로 유지하는 서비스 개념으로 새 Windows를 소개합니다. 또한 이러한 변경을 위해서는 [기존의 배포 프로세스에 대해 다시 생각해 보아야 합니다](https://technet.microsoft.com/itpro/windows/plan/windows-10-deployment-considerations).

Windows 10을 배포한 후에는 Intune을 사용하여 최종 사용자의 생산성 및 비즈니스 요구에 맞게 [Windows 10 PC를 가장 잘 관리하는 방법도 결정해야 합니다](https://docs.microsoft.com/intune/get-started/choose-how-to-manage-devices). 두 가지 선택: Windows 10 PC와 모바일 장치를 등록하거나 Intune 소프트웨어 클라이언트를 설치하여 장치를 컴퓨터로 관리하는 것입니다.

### <a name="manage-and-protect-company-data"></a>회사 데이터 관리 및 보호
오늘날에는 대부분 정보 근로자가 모바일을 사용하여 모바일 장치에서 나오는 생산성은 경쟁력을 갖추는 데 필수적입니다. 이러한 직원들은 언제 어디서나 모든 회사 앱과 데이터에 대해 원활하게 액세스할 수 있어야 하며, EMS는 온-프레미스 또는 클라우드에서 이를 쉽게 수행할 수 있도록 합니다.

**온-프레미스 회사 데이터를 보호**합니다. 대부분의 엔터프라이즈 이동성 전략은 인터넷에서 모바일 장치를 사용하는 직원이 메일에 안전하게 액세스할 수 있도록 하는 계획으로 시작되지만, 모바일 장치에서 액세스하는 [온-프레미스 회사 데이터에 안전하게 액세스](https://docs.microsoft.com/enterprise-mobility-security/solutions/conditional-access-intune-exchange)할 수도 있어야 합니다. 예를 들어 대부분의 조직에는 해당 회사 네트워크에서 호스팅되는 온-프레미스 데이터 및 Microsoft Exchange와 같은 앱 서버가 있습니다. Intune 및 Microsoft EMS(Enterprise Mobility + Security)는 회사 네트워크 경계에 다른 게이트웨이 컴퓨터를 배포하지 않고도 Intune을 사용하여 장치를 등록할 때까지 어떤 모바일 앱도 메일에 액세스할 수 없도록 하는 Exchange Server에 고유하게 통합된 조건부 액세스 솔루션을 제공합니다.

전자 메일 이외에도 Intune에서는 기간 업무 앱 서버의 줄과 같은 온-프레미스 데이터에 대한 보안 액세스가 필요한 모바일 앱에 대한 액세스를 지원합니다. 일반적으로 Microsoft Azure AD 응용 프로그램 프록시와 같은 경계에서 표준 VPN 게이트웨이 또는 프록시와 결합된 액세스 제어에 Intune 관리 인증서를 사용하여 수행합니다. 이러한 경우에 회사 데이터에 액세스하는 유일한 방법은 관리에 장치를 등록하는 것입니다. 일단 장치를 등록하면 Intune은 회사 데이터를 액세스하는 장치에서 회사 정책을 준수하도록 보장합니다.

**Office 365 회사 데이터를 보호합니다**. [Office 365(메일, 문서, 인스턴트 메시지 등)](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-office365-data-with-intune)에서 회사 데이터를 보호하는 작업은 사용자에도 쉽고 원활합니다. Intune 및 Microsoft Enterprise Mobility + Security는 사용자, 앱 또는 장치가 회사의 규정 준수 요구 사항(다단계 인증 수행, Intune을 사용하여 등록, 관리되는 앱 사용, 지원되는 OS 버전, 장치 PIN, 사용자 위험 프로필 저하 등)을 충족하지 않는 경우 Office 365 데이터를 액세스할 수 없도록 하는 고유하고 통합된 조건부 액세스 솔루션을 제공합니다. 해당하는 앱 스토어의 Office 모바일 앱은 Intune을 통해 구성할 수 있는 데이터 제약 정책을 사용할 준비가 되었습니다. 이렇게 하면 IT 팀에서 관리하지 않는 앱(예: 네이티브 메일 앱) 및 저장소 위치(예: Dropbox)와 데이터를 공유하지 않도록 방지합니다. 이 기능은 모두 Office 365 및 EMS에 빌드됩니다. 이 값을 가져오기 위해 추가 인프라를 배포할 필요가 없습니다.

**Office 365에 대한 액세스를 보호하고 관리되지 않는 장치에서 데이터를 보호합니다**. 일반적인 Office 365 배포 방법은 장치를 관리에 등록하는 것이지만 항상 그래야 하는 것은 아닙니다. 사용자가 단순히 회사 메일 및 문서에 액세스해야 하면 개인적으로 소유하는 장치인 경우가 많습니다. 이 경우 사용자는 Office 모바일 앱([앱 제한 정책을 적용한](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune))을 사용해야 하고 장치 등록을 건너뛸 수 있습니다.

## <a name="leverage-cloud-security-and-protection"></a>클라우드 보안 및 보호 활용
EMS는 이 모바일 우선, 클라우드 우선의 시대에 보안 문제에 대한 전체적 접근법을 제공하는 ID 기반의 솔루션을 제공합니다. EMS를 사용하면 공유 조직 데이터를 보호할 뿐만 아니라 피해가 발생하기 전에 보안 침해를 식별할 수도 있습니다.

### <a name="securely-share-data"></a>데이터를 안전하게 공유
오늘날 조직 경계를 너머 여러 장치를 통해 정보 공유가 진행되고 있습니다. 기업은 어떤 데이터에 보호가 필요하고 어떤 데이터가 그렇지 않은지를 식별해야 합니다. 이러한 과제를 해결하기 위해 [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)을 사용하여 [민감한 데이터를 분류, 레이블 지정 및 보호](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario)함으로써 중요한 회사 데이터가 손상되지 않도록 하면서 사용자는 업무를 완료하는 데 중요한 정보를 안전하게 공유할 수 있습니다.

Azure Information Protection을 사용하여 조직에서는 데이터 생성 또는 수정 시에 데이터를 분류하고 레이블을 지정하고 보호할 수 있습니다. 사용자는 Azure Information Protection을 사용하여 다음을 수행할 수 있습니다.
- 민감도를 기준으로 데이터를 분류하고 수동 또는 자동으로 레이블 추가
- 암호화, 인증 및 사용 권한을 사용하여 데이터 보호
- 최종 사용자를 위한 직관적이고 비침입성 환경 설정

### <a name="identify-and-protect-against-threats"></a>위협을 식별하고 손상되지 않도록 보호
<!-- Detect advanced threats on-premises and in the cloud (ATA, Azure AD, Cloud App Security) -->
점점 더 많은 기업이 보안 위반 추정을 원칙으로 삼고 있습니다. EMS는 조직이 온-프레미스에서는 [Microsoft 고급 위협 분석](http://www.microsoft.com/ata)을 통해서 그리고 클라우드에서는 [Azure Active Directory](http://www.microsoft.com/identity) 및 [Cloud App Security](http://www.microsoft.com/cloudappsecurity)를 통해서 혁신적인 행동 분석과 변칙 감지 기술을 사용하여 공격자를 식별하는 데 도움을 줍니다. 위협 인텔리전스는 클라우드의 방대한 데이터 집합 및 기계 학습에 의해 이루어지는 Microsoft Intelligent 보안 그래프로 강화됩니다.

고급 위협 분석은 사용자, 장치 및 리소스의 동작을 지속적으로 학습하고 빠르게 발전하는 기업에서 변화를 반영하도록 조정합니다. 전술이 보다 정교해지면 고급 위협 분석으로 동작 분석 정보를 이용하여 조정 및 대응할 수 있습니다.

## <a name="full-service-it-from-the-cloud"></a>클라우드에서 전체 서비스 IT
조직이 디지털 전환을 완료하면 클라우드의 전체 서비스 IT는 일상적인 비즈니스가 될 것입니다. 성숙한 클라우드 구현이 이루어진 회사는 장기간의 종단 간 ID 및 데이터 보호 시나리오를 가능하게 하기 위해 EMS가 제공하는 기능을 활용할 방법을 모색하게 됩니다.

### <a name="identity-management-from-hire-to-retire"></a>고용에서 퇴직까지의 ID 관리
Microsoft는 10여년 동안 클라우드 기반 ID의 보안을 유지해 왔으며, Azure Active Directory를 통해 이러한 보호 시스템을 엔터프라이즈 고객에게 제공함으로써 향상된 보안과 관리 기능으로 사용자와 관리자의 책임을 유지하도록 지원하고 있습니다.

**수천 개의 앱, 하나의 ID**. 수많은 클라우드 앱에 대한 SSO 및 웹앱에 대한 액세스를 통해 Azure Active Directory Premium을 온-프레미스로 실행할 수 있습니다. 사용하기 편하게 구축된 Azure Active Directory 관리 도구를 사용하면 공동 작업이 가능하고 전체적인 ID 보호 및 적응 액세스 제어를 이용할 수 있습니다.

Azure AD는 조직이 어디에서나 필요한 모든 것에 액세스할 수 있도록 하는 클라우드 ID 및 액세스 관리 솔루션입니다. Azure AD(Azure Active Directory)는 클라우드 리소스와 온-프레미스 리소스 모두에 액세스하는 [SaaS(Software as a Service) 앱 사용자에게 공통 ID를 제공](https://docs.microsoft.com/enterprise-mobility-security/solutions/thousands-apps-one-identity)하여 사용자의 생산성을 개선합니다.

**경계 없이 비즈니스를 지원합니다**. 조직에서는 [모든 장치 및 모든 위치에서 조직의 모든 데이터 및 앱에 액세스할 수 있는 직원의 역량을 강화해야 합니다](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-business-without-borders). 사용자는 서로 협력하고 파트너와 공동 작업을 수행해야 하며 고객과 연결해야 합니다.

이 새로운 세계에는 기존 도구로 완화할 수 없는 문제 및 고급 위협이 도사립니다. 새로운 경계가 사용자일 때는 네트워크만 보호하는 것은 소용 없습니다. 이 환경에서 보호되고 생산성을 유지하는 열쇠는 강력한 ID 솔루션입니다.

**대규모 액세스 관리**. Azure AD는 동적 그룹 구성원 자격 규칙 및 앱 관리 기능을 활용하여 자동화된 [고급 사용자 수명 주기 관리](https://docs.microsoft.com/enterprise-mobility-security/solutions/manage-access-at-scale)를 제공합니다.

Azure AD Premium은 어디서든 사용할 수 있는 ID뿐만 아니라 조직 내에서 IT를 자동화하고, 보호하고, 관리하는 다양한 도구도 제공합니다. 클라우드 컴퓨팅이 등장한 이후에도 사용자 암호 다시 설정에 관한 지원 센터 문의를 비롯하여 사용자 그룹 관리, 응용 프로그램 요청 등의 다양한 IT 작업을 관리하고 제어해 달라는 요구는 여전합니다.

**클라우드 기반 보호**. Azure AD ID 보호는 조직의 ID에 영향을 주는 [위험 이벤트 및 잠재적 취약성에 대한 통합 보기](https://docs.microsoft.com/enterprise-mobility-security/solutions/cloud-powered-protection)를 제공하는 보안 서비스입니다.

Azure Active Directory ID 보호는 독보적입니다. 기계 학습을 사용하여 매일 10TB 이상의 동작 및 상황별 데이터를 분석함으로써 의심스러운 활동에 대한 가시성을 제공하고 필요한 경우 즉각적인 조치를 취할 수 있도록 해줍니다.

또한 Azure AD 조건부 액세스 규칙을 통해 고객은 장치 준수 또는 네트워크 위치와 같은 특성에 따라 온라인 서비스에 대한 액세스를 제어할 수 있습니다. 다음과 같이 구별할 수 있습니다.
- Azure AD MFA 기반 조건부 액세스
- Azure AD 위치 기반 조건부 액세스
- Azure AD 장치 기반 조건부 액세스

### <a name="protect-shared-files-and-saas-apps-with-policies-and-tracking"></a>정책 및 추적을 사용하여 공유 파일 및 SaaS 앱 보호
EMS는 고급 회사 데이터 보호를 비즈니스의 리듬에 맞게 통합함으로써 고의적 및 실수로 인한 데이터 손실로부터 회사 정보를 쉽게 보호할 수 있도록 합니다.

**내부 및 외부에서 중요한 데이터를 공유합니다**. 많은 데이터 위반이 사이버 공격으로 인해 발생하지만 전문가들은 그보다 훨씬 많은 데이터 위반이 사람의 실수, 즉 직원이 중요한 비즈니스 데이터를 실수로 유출한 결과에서 비롯된다는 점에 동의합니다. [올바른 보안 정보 및 데이터 손실 방지 프로토콜을 갖추고 있다면](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data) 이러한 종류의 위반을 거의 모두 방지할 수 있습니다.

EMS를 사용하면 IT 관리자가 Azure Rights Management 정책 템플릿을 사용하여 사용 현황을 메일로 보낼 수 있습니다. 사용 권한은 온라인 및 오프라인뿐 아니라 조직 방화벽의 내부 및 외부에서도 보호가 이루어지도록 메시지 자체에 연결됩니다.

**공유 데이터의 사용을 추적하고 데이터 남용에 대응합니다**. [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)은 클라우드 기반 솔루션으로 조직에서 문서와 메일을 분류하고 레이블을 지정하며 보호하는 데 도움이 됩니다. 이 기능은 규칙 및 조건을 정의하는 관리자는 자동으로, 사용자는 수동으로 수행할 수 있으며, 사용자가 권장 사항을 제공받은 경우에는 자동 또는 수동으로 수행할 수 있습니다.

Azure Information Protection 레이블을 사용하여 문서와 전자 메일을 분류할 수 있습니다. 이 작업을 수행하면 데이터가 저장된 위치나 데이터를 공유한 사용자가 누구인지와 관계없이 항상 분류를 식별할 수 있게 됩니다. 영구 레이블로는 머리글, 바닥글, 워터마크 등의 시각적 표시가 있습니다. 다른 서비스(예: 데이터 손실 방지 솔루션)에서 분류를 식별하고 적절한 조치를 취할 수 있도록 파일 및 전자 메일 머리글에 메타데이터가 일반 텍스트로 추가됩니다.

**유연한 배포 및 키 관리 옵션을 이용하여 원하는 방식으로 데이터를 관리합니다**. Microsoft에서 테넌트 키(기본값)를 관리하는 대신 조직에 적용되는 특정 규정을 준수하도록 [자체 Azure Information Protection을 테넌트 키를 관리](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key)하려고 할 수 있습니다. 자체 테넌트 키를 관리하는 것을 BYOK(bring your own key)라고도 합니다.

**직원용 SaaS 응용 프로그램을 사용 권한 부여 및 관리합니다**. [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 통해 앱에 권한을 부여/취소하고, DLP(데이터 손실 방지)를 적용하고, 사용 권한 및 공유를 제어하고, 사용자 지정 보고서 및 경고를 생성할 수 있습니다.

 클라우드 앱 보안은 조직이 활동에 대한 향상된 가시성으로 제어를 유지하는 동시에 클라우드 앱의 약속을 완전히 활용하는 데 도움이 되는 포괄적인 솔루션입니다. 또한 클라우드 응용 프로그램에서 중요한 데이터의 보호를 강화합니다. Shadow IT를 찾는 데 유용한 도구를 사용하여 위험 평가, 정책 적용, 활동 조사 및 위협을 중지합니다. 조직은 중요한 데이터의 제어를 유지하는 동시에 안전하게 클라우드로 이동할 수 있습니다.

**사용자의 실수로부터 데이터를 보호합니다**. 이동성 및 클라우드로의 전환은 직원 생산성을 크게 향상시켰지만 온-프레미스와 클라우드 모두에서 사용자, 장치, 앱 및 데이터 간의 복잡한 상호 작용으로 인해 IT 팀에 새로운 과제를 안겨 주었습니다. 조직에서 이러한 전환을 수용하지 않을 수도 있지만 직원들은 이미 전환한 상태입니다. 이러한 구성 요소 간의 상호 작용 및 공격 벡터의 정교성이 증가함에 따라 보안은 여전히 기업의 가장 중요한 과제입니다. IT 직원들은 회사 데이터의 가시성, 제어 및 보호를 유지 관리하기 위해 노력하고 있습니다.

클라우드 앱 보안을 사용하면 사용자 및 데이터 작업을 자세히 볼 수 있으므로 중요한 회사 데이터 작업을 할 때 [사용자가 잘못된 선택을 하는 경우 회사 데이터를 보호](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)할 수 있습니다. 또한 Office 365를 비롯한 클라우드 앱에 대한 가시성 및 제어를 제공합니다. Azure Information Protection을 통해 영구적 데이터 보호에 분류 및 레이블 지정 기능을 결합하여 내부적 및 외부적으로 안전한 파일 공유를 가능하게 합니다.

### <a name="learn-more"></a>자세한 정보

[Microsoft Enterprise Mobility + Security 페이지 방문](http://go.microsoft.com/fwlink/?LinkId=816837)

[EMS(Enterprise Mobility + Security)에 대해 알아보기](learn-about-ems.md)

[EMS 무료 사용](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-trial)
