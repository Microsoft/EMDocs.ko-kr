---
title: 대규모 액세스 관리
description: 이 문서에서는 Enterprise Mobility + Security를 통해 Azure Active Directory 내의 도구를 활용하여 ID 액세스를 관리할 수 있는 조직의 역량을 강화하는 방법을 설명합니다.
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: conceptual
ms.prod: ''
ms.service: active-directory
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 3a4037d33b75b606629b00f441ba458f4562346f
ms.sourcegitcommit: 5934334420a8ca02c26ffb1d8f19c185a4c3a741
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75692377"
---
# <a name="manage-access-at-scale"></a>대규모 액세스 관리
Microsoft는 지금까지 많은 조직을 지원해 왔습니다. Microsoft는 어디서든 사용할 수 있는 ID뿐만 아니라 조직 내에서 IT를 자동화하고, 보호하고, 관리하는 다양한 도구도 제공합니다. 클라우드 컴퓨팅이 등장한 이후에도 사용자 암호 다시 설정에 관한 지원 센터 문의를 비롯하여 사용자 그룹 관리, 앱 요청 등의 다양한 IT 작업을 관리하고 제어해 달라는 요구는 여전합니다.

## <a name="how-enterprise-mobility--security-can-help-you"></a>EMS(Enterprise Mobility + Security)의 이점
EMS(Enterprise Mobility + Security)는 ID, 디바이스, 앱, 데이터 등의 4단계 보호 기능으로 디바이스뿐 아니라 그 이상에서 기업 데이터를 기본적으로 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS는 모바일 중심, 클라우드 중심 환경의 핵심 과제 중 하나인, 다음과 같은 이점을 주는 포괄적인 Azure AD(Azure Active Directory) 내 도구를 제공하는 문제를 해결해 줍니다.
- 고급 사용자 수명 주기 관리
- IT 오버헤드 감소 및 비용 절감
- ID 브리지 모니터링

## <a name="recommended-solution"></a>권장 솔루션
Azure AD Premium은 ID 액세스 관리를 통해 조직의 역량을 강화하기 위한 권장 솔루션입니다.

### <a name="advanced-user-lifecycle-management"></a>고급 사용자 수명 주기 관리
Azure AD는 동적 그룹 구성원 자격 규칙 및 앱 관리 기능을 활용하여 자동화된 고급 사용자 수명 주기 관리를 제공합니다. 자세한 내용은 다음과 같습니다.

- 온-프레미스 HR을 갖춘 조직의 경우 Microsoft Identity Manager가 Windows Server Active Directory에서 사용자 ID를 설정합니다.
- HR에 SaaS(Software as a Service)가 전달된 조직의 경우 Azure AD가 현재 Workday와 통합됩니다.
- Azure AD Connect는 Windows Server Active Directory와 Azure AD 간에 사용자 및 그룹을 동기화합니다.
- Azure AD는 Office 365 및 기타 Microsoft Online Services에 대해 그룹 기반의 자동화된 라이선스를 제공합니다.

![Azure AD Connect가 Windows Server Active Directory와 Azure Active Directory 간에 사용자 및 그룹을 동기화하는 방식을 보여 주는 그래픽](./media/manage-access-at-scale/manage-access-at-scale-fig1.png)

### <a name="application-management"></a>애플리케이션 관리
매일 사용하는 각 앱에 대한 암호를 기억하고 싶은 사용자는 얼마나 될까요? [Single Sign-On](https://azure.microsoft.com/documentation/articles/active-directory-appssoaccess-whatis/)이 일반적인 문제를 해결합니다. 단일 사용자 계정 및 암호를 사용하여 여러 SaaS 애플리케이션에 로그인할 수 있습니다. Single Sign-On을 조직 내의 모든 애플리케이션에 자동으로 프로비전할 수 있습니다. 이 기능은 Office 365와 같은 Microsoft 클라우드 앱과 Salesforce, ServiceNow, Workday 같은 타사 앱에 사용할 수 있습니다.

Single Sign-On에 대한 자세한 정보는 다음과 같습니다.

 - 또한 클라우드에서 작동되므로 시간과 비용을 절약할 수 있습니다. 온-프레미스 솔루션을 사용하려면 경계 네트워크, 에지 서버 또는 기타 복잡한 인프라를 설정하고 유지 관리해야 합니다.
 - 방화벽을 통해 인바운드 연결을 열지 않아도 되므로 온-프레미스 솔루션에 비해 더 쉽게 설정하고 보안을 유지할 수 있습니다.
 - 뛰어난 보안을 제공합니다. Azure AD 앱 프록시를 사용하여 앱을 게시하면 Azure에서 권한 부여 제어 및 보안 분석을 활용할 수 있습니다. 즉, 앱을 변경하지 않고도 기존의 모든 앱에 대해 고급 보안 기능을 활용할 수 있습니다.
 - 사용자에게 일관된 인증 환경을 제공합니다. Single Sign-On은 하나의 암호를 사용하여 생산성을 발휘하는 데 필요한 모든 앱에 대한 사용자 액세스를 제공합니다.

### <a name="low-it-overhead-and-cost"></a>IT 오버헤드 감소 및 비용 절감
Azure AD Premium은 암호 재설정, 그룹 관리 및 앱 관리 기능을 위한 셀프 서비스를 제공하여 IT 부서 및 사용자의 생산성을 강화합니다. 사용자가 지원 센터 문의 전화를 할 필요가 없으며, 메일로 전송되거나 안전하지 않은 방식으로 통화 중에 공유되는 임시 암호를 얻기 위해 많은 정보를 제공할 필요도 없습니다.

암호 재설정에 대한 자세한 정보는 다음과 같습니다.

- 페더레이션, 암호 동기화 또는 클라우드 전용 사용자 계정이 사용됩니다. 또한 모든 온-프레미스 암호 정책이 적용됩니다.
- 모든 트래픽이 테넌트별 키를 사용하여 HTTPS를 통해 암호화됩니다.
- 사용자는 AD 암호를 업데이트하거나 실시간으로 자신의 AD 계정 잠금을 해제할 수 있습니다.
- 실시간 알림이 사용자 및 관리자에게 전송됩니다.

![Azure Active Directory가 온-프레미스 및 클라우드에서 작동되어 최종 사용자에게 셀프 서비스 암호 재설정 기능을 제공하는 방법을 보여 주는 그래픽.](./media/manage-access-at-scale/manage-access-at-scale-fig2.png)

### <a name="monitor-your-identity-bridge"></a>ID 브리지 모니터링
Azure AD Connect Health를 통해 조직은 온-프레미스 ID 인프라 및 동기화 서비스를 모니터링하고 이에 대한 정보를 얻을 수 있습니다. 또한 조직에서는 해당 핵심 ID 구성 요소에 대한 모니터링 기능을 제공함으로써 Office 365 및 Microsoft 온라인 서비스에 대한 신뢰할 수 있는 연결을 유지 관리할 수 있습니다. 이러한 구성 요소에는 AD FS(Active Directory Federation Services) 서버, Azure AD Connect 서버 및 Active Directory 도메인 컨트롤러(DC)가 포함됩니다.

Azure AD 상태에 대한 자세한 내용은 다음과 같습니다.

- Azure Portal을 통한 원클릭 감사 및 규정 준수
- 법정 및 조사: IT 관리자가 "누가 언제 어디서 무엇을 했는지"에 답변할 수 있도록 합니다.
- 활동 보고서: 감사, 로그인, 셀프 서비스 암호 재설정, 그룹 활동, 앱 활동, 앱 프로비전 등을 제공 합니다.
- 보안 보고서: ID 보호를 통해 보안 문제에 대한 완화 및 해결 방법을 제공합니다.

![조직이 AD FS 서버, Azure AD Connect 서버 및 Active Directory 도메인 컨트롤러와 같은 핵심 ID 구성 요소를 모니터링하도록 Azure AD Connect Health가 어떻게 도움을 줄 수 있는지를 보여 주는 그래픽](./media/manage-access-at-scale/manage-access-at-scale-fig3.png)

## <a name="how-to-implement-an-advanced-user-lifecycle-management"></a>고급 사용자 수명 주기 관리를 구현하는 방법
몇 가지 예제와 이 솔루션을 구현하기 위해 수행할 수 있는 단계를 살펴보겠습니다.

1. 실제 시나리오에서 조직은 전문가를 고용하고 해당 사용자를 마케팅 팀의 구성원으로 HR 시스템에 추가합니다.
2.  디렉터리 동기화를 통해 온-프레미스 Active Directory 인스턴스를 Azure AD에 이미 통합한 경우 온-프레미스 Azure AD Connect는 사용자 계정을 Azure AD와 동기화합니다.
3.  Azure AD에 사용자 계정이 표시되면 마케팅 사용자를 자동으로 할당하는 동적 그룹 구성원 관리 규칙을 만들 수 있습니다.
4.  마케팅 그룹이 자동으로 해당 사용자로 채워지면 그룹 기반의 선택적 라이선스를 사용할 수 있습니다. 이러한 종류의 라이선스는 Azure AD Premium 또는 Office 365 Enterprise E5와 같은 특정 라이선스 그룹에 사용자를 추가 하는 기능을 제공합니다.
    이 예제에서 해당 라이선스는 사용자가 작업 수행에 필요한 모든 Office 365 앱 액세스 권한과 기타 자동화된 작업을 수행하기 위한 Azure AD Premium 액세스 권한을 제공합니다.

직원이 퇴사할 경우에 HR 시스템에서 제거할 수 있습니다. 그러면 모든 애플리케이션 및 이전에 프로비전된 리소스에서 자동으로 액세스가 제거됩니다. 직원이 단지 다른 부서를 이동해야 하는 경우 해당 사용자가 마케팅 팀에서 제거된 후 새 부서의 동적 그룹으로 추가되었을 때 동적 그룹 구성원 자격 규칙이 마케팅 앱에서 액세스 권한을 자동으로 제거하고 다른 부서 앱에 대한 액세스 권한을 추가합니다.

## <a name="how-to-manage-cloud-and-on-premises-applications"></a>클라우드 및 온-프레미스 애플리케이션을 관리하는 방법
Azure AD를 사용하여 Microsoft 및 타사 SaaS 애플리케이션을 추가, 배포 및 관리하는 단계는 다음과 같습니다.
- [Azure AD를 앱에 통합](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/)에 대한 자세한 정보
- [SaaS 앱에 대해 Single Sign-On 사용](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/)에 대한 자세한 정보
- [앱에 대한 액세스 관리](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/)에 대한 자세한 정보

## <a name="how-to-implement-password-reset-self-service-portal"></a>암호 재설정 셀프 서비스 포털을 구현하는 방법
기본적으로 Azure AD에는 모든 관리자가 셀프 서비스 암호 재설정을 수행할 수 있도록 하는 무료 기능이 포함되어 있습니다.

Azure AD Premium을 사용할 경우 사용자에게 암호 재설정 셀프 서비스 포털 기능을 제공하여 IT 관리자 이상의 작업을 수행할 수 있습니다. 디렉터리 내의 모든 사용자에게 동일한 수준의 관리 기능을 확장하는 사용자 암호 재설정 정책을 빠르게 적용할 수 있습니다.

Azure AD 테넌트에서 [필수 구성 요소, 암호 셀프 서비스 포털을 사용하도록 설정하고 구성하는 방법](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)에 대해 자세히 알아보세요.

## <a name="how-to-use-azure-ad-connect-health"></a>Azure AD Connect Health를 사용하는 방법
[Azure AD Connect Health 설명서](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)를 확인하여 조직에서 이 기능을 사용하기 위해 사용할 수 있는 도구, 해당 기능 및 작업 단계를 알아볼 수 있습니다.

Azure AD Connect Health는 [Azure Portal](https://ms.portal.azure.com)에서 사용할 수 있으며 모니터링하려는 온-프레미스 도메인 컨트롤러에 상태 에이전트가 설치되어 있어야 합니다. [상태 에이전트를 설치하는 방법](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install)에 대한 자세한 정보

**도메인 컨트롤러** 대시보드는 환경의 상태 및 작업 상황에 대한 단일 뷰를 제공합니다. 따라서 관리자는 어떤 DC가 FSMO(Flexible Single Master Operation) 역할 소유자인지, 어떤 DC가 활성 경고인지, 어떤 DC가 글로벌 카탈로그인지 쉽게 파악할 수 있습니다. 다른 열에는 **PDC 연결 가능**, **GC 연결 가능** 및 **SYSVOL 상태**가 포함됩니다.

![선택한 도메인 컨트롤러에 대한 정보와 도메인 컨트롤러 대시보드를 보여 주는 스크린샷](./media/manage-access-at-scale/manage-access-at-scale-fig4.png)

또한 DC를 해당 도메인별로 그룹화할 수도 있고 관리자가 사이트별로 그룹화할 수도 있습니다.

![사이트별로 그룹화된 도메인 컨트롤러를 보여 주는 스크린 샷](./media/manage-access-at-scale/manage-access-at-scale-fig5.png)

**복제 상태** 대시보드에는 환경 내의 복제 토폴로지 모양과 각 명명 컨텍스트에 대한 마지막 복제 시도 관련 정보가 표시됩니다.

![마지막 복제 시도에 대한 정보가 표시되는 복제 상태 대시보드를 보여 주는 스크린샷.](./media/manage-access-at-scale/manage-access-at-scale-fig6.png)

경고 세부 정보에는 경고를 유발하는 문제에 대한 추가 정보, 필요한 수정 프로그램 및 추가 문제 해결 리소스에 대한 링크가 포함됩니다.

![지정된 경고에 대한 세부 정보를 보여 주는 스크린샷](./media/manage-access-at-scale/manage-access-at-scale-fig7.png)

AD Connect Health 성능 모니터링은 모니터링되는 DC의 성능을 서로 비교하고 여러 다른 메트릭을 비교하는 간편한 방법을 제공합니다.

![선택한 도메인 컨트롤러의 성능 모니터링을 보여 주는 스크린샷](./media/manage-access-at-scale/manage-access-at-scale-fig8.png)
