---
title: US Government용 Enterprise Mobility + Security 서비스 설명
description: EMS GCC High 계획은 월간 구독이며 사용자별로 라이선스가 부여됩니다.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: f933eedb9c8bd5eca8f384b1b5801b774311f99f
ms.sourcegitcommit: 23d04d4ce0acb51b86b7702b9f0c3bb6b55b0043
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70936068"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>US Government용 Enterprise Mobility + Security 서비스 설명
Microsoft에서는 미국 공공 부문의 고유하면서 진화하고 있는 요구 사항에 대한 대응으로 미국 정부 커뮤니티 고객을 위해 Enterprise Mobility + Security(EMS) 요금제를 만들었습니다. 이 문서에서는 EMS 요금제에 관련된 기능을 간단히 설명합니다.

## <a name="how-to-use-this-service-description"></a>서비스 설명을 사용하는 방법
EMS의 EMS 서비스 설명은 해당 제품에 대 한 개요를 제공 하 고, (1) 다른 제품에 포함 된 서비스 및 기능, (2) 미국 정부 제품이 상업적와 어떻게 다른 지에 대 한 개요를 제공 합니다. 제품 및 (3) 현재 규정 준수 권한 부여.

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>EMS는 US Government에 대한 Office 365 상호 운용성을 제공합니다.

|EMS US Government 제품|호스팅된 서비스 위치|상호 운용 가능한 Office 365 정부 커뮤니티 클라우드 (GCC) 제품|
|-----------|-----------|-----------|
|GCC용 EMS</br>*E3 및 E5 모두에서 사용 가능**|Azure 상용 클라우드|Office 365 GCC|
|GCC High 및 DOD용 EMS</br>*E3 및 E5에서 사용 가능**|Azure Government 클라우드|Office 365 GCC High</br>Office 365 DOD|

> [!Note]
> *E5 제품은 현재 Microsoft Intune 외 Azure AD Premium 2와 Azure Information Protection P2로 제한됩니다. Microsoft Cloud App Security 및 Azure Advanced Threat Protection(ATP)은 현재 Office 365 GCC, GCC High 또는 DOD 고객용 제품에 포함되어 있지 않습니다. 그러나 GCC 고객은 EMS E5 SKU를 구매하여 Microsoft Cloud App Security 및 Azure ATP 상업용 제품의 추가 기능을 선택할 수 있습니다.  

## <a name="ems-for-us-office-365-gcc-customers"></a>미국 Office 365 GCC 고객용 EMS
Azure Active Directory P1/P2, Microsoft Intune, Azure Information Protection P1/P2는 Azure 상업용 환경에서 호스팅되며 Office 365 GCC 플랫폼과 상호 운용 가능합니다.  이러한 서비스는 FedRAMP-High 인증을 받았으며 모든 [GCC 규정 준수](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance) 특성을 충족합니다.

GCC 고객은 EMS E5 SKU를 구매하여 Microsoft Cloud App Security 및 Azure ATP 상업용 제품의 추가 기능을 선택할 수 있습니다.  위에서 설명한 것처럼 Microsoft Cloud App Security 및 Azure ATP는 Azure Commercial FedRAMP High Authorization to Operate(ATO)가 적용되는 상업용 제품이지만 CJIS 신원 조회, IRS 1075, 미국 정부 조회 대상 인원에 의한 고객 콘텐츠 액세스 같은 다른 [GCC 규정 준수](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc#us-government-community-compliance) 특성을 충족하지 못할 수 있습니다.  Microsoft 제품 및 서비스용 규정 준수 제품 목록은 [Microsoft 보안 센터](https://www.microsoft.com/en-us/trustcenter/compliance/complianceofferings)에서 찾을 수 있습니다.  

## <a name="ems-for-us-office-365-gcc-high-and-dod-customers"></a>미국 Office 365 GCC High 및 DOD 고객용 EMS
미국 GCC High 및 DOD 고객용 EMS 제품은 Microsoft [Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome) Cloud를 기반으로 하며 Office 365 GCC High 및 DOD 환경과 상호 운용되도록 설계되었습니다. Azure Active Directory P1/P2, Microsoft Intune 및 Azure Information Protection P1/P2는 이 제품에 대해 FedRAMP-High 인증을 받았습니다. (Microsoft에서는 FedRAMP-High 승인을 기다라는 동안 2019년에 Microsoft Cloud App Security와 Azure Advanced Threat Protection을 이 제품에 추가하는 것을 목표로 하고 있습니다.)

GCC High 고객은 다른 요구 사항 및 관리 요구 사항에 따라 Intune에 별도의 엔드포인트 세트를 사용할 수 있습니다. 다음은 미국 GCC High 고객이 사용할 수 있는 EMS 관리 포털의 목록입니다.

- Office 365 포털: https://portal.office365.us (사용자, 그룹 및 라이선스 관리용])
- Azure/Intune 관리 포털: https://portal.azure.us
- Intune 웹 회사 포털: https://portal.manage.microsoft.us

### <a name="parity-with-commercial"></a>상업용과 동등 
US Government 제품을 통해 정부 고객에게 모든 상업용 기능을 제공하는 것을 목표로 하고 있지만 강조하려는 일부 기능은 아직 Azure Government 환경에서 사용할 수 없습니다.  2019년 6월 현재 Azure Government의 EMS(GCC High 및 DOD 고객에게 제공)와 상업용 제품의 알려진 기존 차이는 다음과 같습니다.
- Microsoft Intune:
  - 독립 실행형 배포만 지원합니다. System Center Configuration Manager를 포함한 하이브리드 설정은 지원하지 않습니다.
  - 레거시 PC 관리(Intune 소프트웨어 에이전트 사용)를 지원하지 않습니다. Windows 10 관리는 최신 MDM 채널을 통해 지원됩니다.
  - 온-프레미스 Exchange Connector 지원 계획이 없습니다.
  - 공동 관리 지원은 Configuration Manager 버전 1906 이상에서 사용할 수 있습니다.
  - 지금은 정부 고객이 Windows Autopilot 및 Business Store 기능을 사용할 수 없습니다.
- Azure Information Protection:
  - 현재 Azure Government에서 사용할 수 없는 기능의 목록을 보려면 Azure Government 설명서 사이트 내의 [Azure Information Protection Premium](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) 페이지를 방문하세요.
- Azure Active Directory:
  - Azure Government에서 현재 사용할 수 없는 기능의 목록을 보려면 Azure Government 설명서 사이트의 [Azure Active Directory Premium](https://docs.microsoft.com/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2) 페이지를 방문하세요.

## <a name="customer-eligibility"></a>고객 자격
US Government 제품은 (1) 미국 연방, 주, 지방, 부족 정부 기관 및 (2) 정부 규정 및 요구 사항이 적용되는 데이터를 처리하는 기타 기관에서 서비스 사용이 요구 사항을 충족하고 자격에 대한 유효성 검사를 준수하는 경우에 사용할 수 있습니다. Microsoft의 자격 유효성 검사에는 정부가 규제하거나 통제하는 데이터 처리에 대한 확인이 포함됩니다. GCC, GCC High 및 DOD 고객용 EMS 요금제는 월간 구독이며 사용자별로 라이선스가 부여됩니다. EMS 자격에 대해 질문이 있는 기관은 해당 계정 팀에 문의해야 합니다.

## <a name="location-of-customer-data"></a>고객 데이터의 위치
US Government 고객용 EMS 서비스(GCC, GCC High, DOD)는 실제로 미국에 있는 데이터 센터에서 제공됩니다. 조직의 고객 데이터는 미국 내에 저장됩니다. 자세한 내용은 [Microsoft 보안 센터](https://products.office.com/en-us/where-is-your-data-located?ms.officeurl=datamaps&geo=All#office-ContentAreaHeadingTemplate-bkjgypc) 페이지에서 찾을 수 있습니다. Microsoft가 상업용 서비스인 Microsoft Cloud App Security와 관련된 미사용 고객 데이터를 저장하는 위치에 대한 자세한 내용은 [온라인 서비스 약관](https://www.microsoft.com/licensing/product-licensing/products)을 검토하세요. Microsoft에서 Azure ATP와 관련된 미사용 고객 데이터를 저장하는 위치에 대한 자세한 내용은 Azure ATP [제품 설명서](https://docs.microsoft.com/azure-advanced-threat-protection/atp-technical-faq#do-i-have-the-flexibility-to-select-where-to-store-my-data)를 검토하세요.

다양한 EMS 서비스는 특정 타사 애플리케이션 및 서비스와 원활하게 작동하는 기능을 제공합니다. 이러한 타사 애플리케이션 및 서비스에는 EMS 인프라 외부에 있기 때문에 당사의 준수 사항 및 데이터 보호 약정이 적용되지 않는 타사 시스템에 조직의 고객 데이터 또는 콘텐츠를 저장, 전송 및 처리하는 작업이 포함될 수 있습니다. 조직에 타사 애플리케이션 및 서비스를 사용하는 것이 적절한지 평가하는 경우에는 타사가 제공하는 개인 정보 보호 및 규정 준수 문서를 검토하는 것이 좋습니다.
