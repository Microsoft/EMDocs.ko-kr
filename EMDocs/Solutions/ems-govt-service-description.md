---
title: US Government용 Enterprise Mobility + Security 서비스 설명
description: EMS GCC High 계획은 월간 구독이며 사용자별로 라이선스가 부여됩니다.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/22/2019
ms.topic: article
ms.prod: ''
ms.service: ems
ms.suite: ems
ms.openlocfilehash: f6d8e2fd7056810740bdc4aeaa8c5520efe1d468
ms.sourcegitcommit: b433abeb9e3c1982aeb4b2d8835ecd9cbebe2b4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69979421"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>US Government용 Enterprise Mobility + Security 서비스 설명 
Microsoft에서는 미국 공공 부문의 고유하고 진화하는 요구 사항에 대한 대응으로 미국 정부 고객을 위해 Enterprise Mobility + Security 플랜을 만들었습니다. 이 문서에서는 EMS 계획에 지정된 기능에 대한 개요를 제공합니다.  

## <a name="how-to-use-this-service-description"></a>서비스 설명을 사용하는 방법 
EMS for US Government 서비스 설명은 당사 제품에 대한 개요 역할을 하도록 디자인되었으며 (1) 이 제품에 포함된 서비스와 기능, (2) Government 제품과 상업용 제품의 차이점과 (3) 현재 규정 준수 약정에 대해 다룹니다. 이 문서에서는 고유한 약정 및 EMS 상업용 제품 대비 차이점을 정의합니다.  

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>EMS는 US Government에 대한 Office 365 상호 운용성을 제공합니다. 

|EMS US Government 제품|호스티드 서비스 위치 |해당 Office 365 Government 제품|규정 준수 약정|
|-----------|-----------|-----------|
|GCC용 EMS</br>E3 및 E5 모두에서 사용 가능*|Azure 상용 클라우드|Office 365 GCC|FedRAMP-Moderate|
|GCC High용 EMS</br>E3 및 E5에서 사용 가능*|Azure Government 클라우드|Office 365 GCC High|FedRAMP-High| 

> [!Note]    
> E5는 이번에 Azure AD P2 및 Azure Information Protection P2로 제한됩니다.  Microsoft Cloud App Security 및 Azure Advanced Threat Protection은 현재 GCC 또는 GCC High 제품에 포함되어 있지 않습니다.  그러나 GCC 고객은 EMS E5 SKU를 구매하여 Microsoft Cloud App Security의 상업용 제품과 Azure ATP 제품(동일한 준수 표준을 충족하지 않음)을 추가하도록 선택할 수 있습니다.

Office 365는 현재 GCC, GCC High 및 DOD 환경에서 사용할 수 있습니다. 이러한 제품에 대해 자세히 알아보려면 [Office 365 Government 서비스 설명](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)을 참조하세요. 

## <a name="ems-for-gcc"></a>GCC용 EMS

EMS 상업용 제품은 Office 365 GCC와 완벽하게 상호 운용이 가능합니다.  Azure Active Directory P1/P2, Intune 및 Azure Information Protection P1/P2는 이 제품에 대해 인증된 FedRAMP-Moderate이며[GCC 기준](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)을 충족합니다.

## <a name="ems-for-gcc-high"></a>GCC High용 EMS

GCC High용 EMS 제품은 Microsoft Azure Government Cloud를 기반으로 하며 Office 365 GCC High 제품과 상호 운용되도록 디자인되었습니다. Azure Active Directory P1/P2, Intune 및 Azure Information Protection P1/P2는 이 제품에 대해 인증된 FedRAMP-High입니다. (Microsoft에서는 FedRAMP-High 승인을 기다라는 동안 2019년에 Microsoft Cloud App Security와 Azure Advanced Threat Protection을 이 제품에 추가하는 것을 목표로 하고 있습니다.)

GCC High 고객은 다른 요구 사항 및 관리 요구 사항에 따라 Intune에 별도의 엔드포인트 세트를 사용할 수 있습니다.  다음은 EMS 고객이 사용할 수 있는 관리 포털의 목록입니다.
* Office 365 Portal: [https://portal.office365.us](https://portal.office365.us)(사용자, 그룹 및 라이선스 관리용])
* Azure / Intune 관리 포털: [https://portal.azure.us](https://portal.azure.us)
* Intune 웹 회사 포털: [https://portal.manage.microsoft.us](https://portal.manage.microsoft.us)

다음과 같은 고유한 기능에서 GCC High용 EMS 혜택을 사용하는 조직은 다음과 같습니다.
* 조직의 콘텐츠가 Microsoft 상업용 EMS 서비스의 콘텐츠와 물리적으로 분리됩니다.
* 조직의 콘텐츠는 미국 내에 저장됩니다.
* 사용자의 콘텐츠가 포함된 Microsoft 시스템에 대한 액세스는 선별된 Microsoft 담당자로 제한됩니다.
* EMS GCC High는 미국 공공 부문 고객에게 필요한 공통 인증 및 인가를 준수합니다.

## <a name="customer-eligibility"></a>고객 자격 
EMS Government는 (1) 미국 연방, 주, 지방, 부족 정부 기관 및 (2) 정부 규정 및 요구 사항을 충족하는 데이터를 처리하는 기타 기관에서 EMS 사용이 이러한 요구 사항을 충족하는 데 적합하고 자격에 대한 유효성 검사를 준수하는 경우에 사용할 수 있습니다. Microsoft의 자격 유효성 검사에는 정부가 규제하거나 통제하는 데이터 처리에 대한 확인이 포함됩니다. GCC 및 GCC High용 EMS 플랜은 월간 구독이며 사용자별로 라이선스가 부여됩니다. EMS 자격에 대해 질문이 있는 엔터티는 해당 계정 팀에 문의해야 합니다.  

## <a name="location-of-customer-data"></a>고객 데이터의 위치 
US Government용 EMS 서비스는 실제로 미국에 있는 데이터 센터에서 제공됩니다. 모든 콘텐츠는 실제로 미국에만 있는 데이터 센터에 안전하게 저장됩니다.  

다양한 EMS 서비스는 특정 타사 애플리케이션 및 서비스와 원활하게 작동하는 기능을 제공합니다. 이러한 타사 애플리케이션 및 서비스에는 EMS 인프라 외부에 있기 때문에 당사의 준수 사항 및 데이터 보호 약정이 적용되지 않는 타사 시스템에 조직의 고객 콘텐츠를 저장, 전송 및 처리하는 작업이 포함될 수 있습니다. 조직에 타사 애플리케이션 및 서비스를 사용하는 것이 적절한지 평가하는 경우에는 타사가 제공하는 개인 정보 보호 및 규정 준수 문서를 검토하는 것이 좋습니다.

## <a name="parity-with-ems-commercial-offerings"></a>EMS 상업용 제품을 사용하는 패리티 
US Government용 EMS 제품을 통해 정부 고객에게 모든 상업용 기능을 제공하는 것을 목표로 하고 있지만 강조하려는 일부 기능은 아직 사용할 수 없습니다.  
    
EMS GCC High와 2019년 2월 상업용 제품 간의 이미 알려진 기존 차이는 다음과 같습니다.  

- Microsoft Intune:

  - 독립 실행형 배포만 지원합니다. System Center Configuration Manager를 포함한 하이브리드 설정은 지원하지 않습니다.

  - 레거시 PC 관리(Intune 에이전트 사용)를 지원하지 않습니다. Windows 10 관리는 최신 MDM 채널을 통해 지원됩니다.

  - 온-프레미스 Exchange Connector를 지원하지 않습니다.

  - 공동 관리 지원은 Configuration Manager 버전 1906 이상에서 사용할 수 있습니다.

  - 계획이 진행 중이지만 지금은 정부 고객이 Windows Autopilot 및 Business Store 기능을 사용할 수 없습니다.

  - 일부 Office 365 모바일 앱은 정부 고객에게 제공되지 않습니다.  [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap)에서 세부 정보를 확인할 수 있습니다.

  - 지금은 Mobile Threat Detection 및 Telecom Expense Management 파트너 솔루션이 정부 고객에게 제공되지 않습니다.

- Azure Information Protection:

  - 현재 사용할 수 없는 기능에 대한 목록이 필요하면 Azure Government 문서 사이트 내의 [Azure Information Protection Premium 페이지](ems-aip-premium-govt-service-description.md)를 방문해 보세요.

- Azure Active Directory:

  - Azure Government에서 현재 사용할 수 없는 기능에 대한 목록이 필요하면 Azure Government 문서 사이트의 [Azure Active Directory Premium 페이지](/azure/azure-government/documentation-government-services-securityandidentity#azure-active-directory-premium-p1-and-p2)를 방문해 보세요.
