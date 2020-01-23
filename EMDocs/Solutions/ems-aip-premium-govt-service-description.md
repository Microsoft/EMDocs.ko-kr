---
title: Azure Information Protection Premium Government 서비스 설명
description: Azure Information Protection 프리미엄 정부 서비스 설명은 제공의 개요를 제공 하도록 설계 되었습니다.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/12/2020
ms.topic: article
ms.prod: ''
ms.service: rights-management
ms-suite: ems
ms.openlocfilehash: bb5a22063ce8dfeaa1f2303b3c41827746a9f69f
ms.sourcegitcommit: cdf0b5b826aeaf0cf6c3a6cd180d44b9e13d543a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76549783"
---
# <a name="azure-information-protection-premium-government-service-description"></a>Azure Information Protection Premium Government 서비스 설명 

## <a name="how-to-use-this-service-description"></a>서비스 설명을 사용하는 방법 

Azure Information Protection 프리미엄 정부 서비스 설명은 GCC High 및 DoD 환경에서 제공 하는 기능에 대 한 개요를 제공 하 고 Azure Information Protection Premium 상용에 비해 기능 변형을 다룹니다. 제공품. GCC 고객의 Azure Information Protection에 대 한 자세한 내용은 [미국 정부 및 Office 365 상호 운용성에 대 한 EMS 제품](ems-govt-service-description.md#ems-offers-for-us-government-and-office-365-interoperability)설명을 참조 하세요.

## <a name="azure-information-protection-premium-government-and-third-party-services"></a>Azure Information Protection Premium Government 및 타사 서비스 

다양한 Azure Information Protection Premium 서비스는 타사 애플리케이션 및 서비스와 원활하게 작동하는 기능을 제공합니다. 이러한 타사 애플리케이션 및 서비스에는 Azure Information Protection Premium 인프라 외부에 있는 타사 시스템에 조직의 고객 콘텐츠를 저장, 전송 및 처리하는 작업이 포함될 수 있으므로 당사의 규정 준수 및 데이터 보호 약정이 적용되지 않습니다. 조직에 이러한 서비스를 사용하는 것이 적절한지 평가하는 경우에는 타사가 제공하는 개인 정보 보호 및 규정 준수 문서를 검토하는 것이 좋습니다. 

## <a name="parity-with-azure-information-protection-premium-commercial-offerings"></a>Azure Information Protection Premium 상업용 제품과 동등 

Azure Information Protection Premium GCC High 및 DoD 제품을 통해 정부 고객에게 모든 상업용 기능을 제공하는 것을 목표로 하고 있지만 몇 가지 기능이 누락되어 있음을 알려드리고자 합니다. 

다음은 Azure Information Protection Premium GCC High/DoD와 2019년 5월 상업용 제품 간의 차이이며 이미 알려진 사항입니다. 

* 문서 추적 및 해지 기능은 현재 사용할 수 없습니다. 

* 분류 및 레이블 지정 추가 기능은 Office 365 ProPlus(버전 9126.1001 이상)에만 지원됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다. 

* IRM(정보 권한 관리)은 Office 365 ProPlus(버전 9126.1001 이상)에만 지원됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다. 

* AD RMS(Active Directory Rights Management Services)에서 Azure Information Protection으로의 마이그레이션은 현재 사용할 수 없습니다. 

* 상용 클라우드에서 보호된 문서와 메일을 사용자와 공유하는 기능은 현재 사용할 수 없습니다. 여기에는 상용 클라우드의 Office 365 사용자, 상용 클라우드의 비 Office 365 사용자 및 개인용 RMS 라이선스를 가진 사용자가 포함됩니다. 

* SharePoint Online이 포함된 정보 권한 관리(IRM 보호된 사이트 및 라이브러리)는 현재 사용할 수 없습니다. 

* 현재 Rights Management 커넥터를 사용할 수 없습니다.

* AD RMS에 대한 모바일 디바이스 확장을 현재 사용할 수 없습니다.


## <a name="configuring-azure-information-protection-for-gcc-high-and-dod-customers"></a>GCC High 및 DoD 고객용 Azure Information Protection 구성

### <a name="enable-rights-management-for-the-tenant"></a>테넌트에 대해 Rights Management 사용
암호화가 제대로 작동하려면 테넌트에 대해 Rights Management 서비스를 사용하도록 설정해야 합니다.

* Rights Management 서비스가 사용하도록 설정되어 있는지 확인
  * 관리자 권한으로 PowerShell 시작
  * AADRM 모듈이 설치되지 않은 경우 `Install-Module aadrm` 실행 
  * `Connect-aadrmservice -environmentname azureusgovernment` 사용을 통해 서비스 연결
  * `(Get-AadrmConfiguration).FunctionalState`를 실행하고 상태가 `Enabled`인지 확인
* 기능 상태가 `Disabled`인 경우 `Enable-Aadrm` 실행

### <a name="dns-configuration-for-encryption-windows"></a>암호화에 대한 DNS 구성(Windows)
암호화가 제대로 작동하려면 Office 클라이언트 애플리케이션이 서비스의 GCC High/DoD 인스턴스로 연결된 다음, 부트스트랩되어야 합니다. 클라이언트 애플리케이션을 올바른 서비스 인스턴스로 리디렉션하려면 테넌트 관리자가 Azure RMS URL에 관한 정보를 사용하여 DNS SRV 레코드를 구성해야 합니다. DNS SRV 레코드가 없는 경우 클라이언트 애플리케이션은 기본적으로 퍼블릭 클라우드 인스턴스에 연결을 시도하고, 이는 실패합니다.

또한 사용자가 onmicrosoft 사용자 이름(예: joe@contoso.onmicrosoft.us)이 아닌 테넌트 소유 도메인 기반 사용자 이름(예: joe@contoso.us)을 사용하여 로그인하는 것으로 가정합니다. 사용자 이름으로부터 도메인 이름은 올바른 서비스 인스턴스에 대한 DNS 리디렉션에 사용됩니다.

* Rights Management 서비스 ID 획득 
  * 관리자 권한으로 PowerShell 시작 
  * AADRM 모듈이 설치되지 않은 경우 `Install-Module aadrm` 실행 
  * `Connect-aadrmservice -environmentname azureusgovernment` 사용을 통해 서비스 연결
  * `(Get-aadrmconfiguration).RightsManagementServiceId` 실행을 통해 Rights Management 서비스 ID 획득
* DNS 공급자에 로그인하고 도메인에 대한 DNS 설정으로 이동하여 새 SRV 레코드 추가
  * Service = `_rmsredir` 
  * Protocol = `_http` 
  * Name = `_tcp` 
  * Target = `[GUID].rms.aadrm.us`(여기서 GUID는 Rights Management 서비스 ID) 
  * Port = `80` 
  * Priority, Weight, Seconds, TTL = 기본값 
* [Azure Portal](https://portal.azure.us/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)에 있는 테넌트와 사용자 지정 도메인을 연결합니다. 이를 통해 DNS에 항목이 추가되고, 이는 DNS 설정에서 값을 추가한 이후 몇 분 뒤에 확인됩니다.  
* 해당 전역 관리자 자격 증명을 사용하여 Office 관리 센터에 로그인하고 사용자 생성을 위한 도메인(예: contoso.us)을 추가합니다. 확인 프로세스에서 일부 DNS 변경이 필요할 수 있습니다. 확인이 완료되면 사용자가 생성될 수 있습니다.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>암호화에 대한 DNS 구성(Mac, iOS, Android)
* DNS 공급자에 로그인하고 도메인에 대한 DNS 설정으로 이동하여 새 SRV 레코드 추가
  * Service = `_rmsdisco` 
  * Protocol = `_http` 
  * Name = `_tcp` 
  * Target = `api.aadrm.us` 
  * Port = `80` 
  * Priority, Weight, Seconds, TTL = 기본값 


### <a name="aip-apps-configuration"></a>AIP 앱 구성
Windows의 AIP 앱은 특수 레지스트리 키를 GCC High/DoD에 대한 올바른 서비스 인스턴스로 가리켜야 합니다.  

| 레지스트리 노드 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| 이름 | WebServiceUrl |
| Value | https://api.informationprotection.azure.us |
| 유형 | REG_SZ(문자열) |
