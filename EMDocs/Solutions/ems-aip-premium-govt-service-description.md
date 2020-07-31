---
title: Azure Information Protection Premium Government 서비스 설명
description: Azure Information Protection 프리미엄 정부 서비스 설명은 제공의 개요를 제공 하도록 설계 되었습니다.
keywords: ''
author: mlottner
ms.author: mlottner
manager: rkarlin
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.service: rights-management
ms-suite: ems
ms.openlocfilehash: e15a537fd0dfdfac2639adfaf5892d2b3e7eb8a9
ms.sourcegitcommit: 93d2f48c81b684cd54cb5b18110530521c44ae6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87389088"
---
# <a name="azure-information-protection-premium-government-service-description"></a>Azure Information Protection Premium Government 서비스 설명 

## <a name="how-to-use-this-service-description"></a>서비스 설명을 사용하는 방법 

Azure Information Protection 프리미엄 정부 서비스 설명은 GCC High 및 DoD 환경에서 제공 하는 기능에 대 한 개요를 제공 하도록 설계 되었으며, Azure Information Protection Premium 상용 제품에 비해 기능 변형을 다룹니다. GCC 및 GCC High 고객에 대 한 Azure Information Protection에 대 한 자세한 내용은 [미국 정부 및 Office 365 상호 운용성에 대 한 EMS 제품](ems-govt-service-description.md#ems-offers-for-us-government-and-office-365-interoperability)설명을 참조 하세요.

## <a name="azure-information-protection-premium-government-and-third-party-services"></a>Azure Information Protection Premium Government 및 타사 서비스 

일부 Azure Information Protection 프리미엄 서비스는 타사 응용 프로그램 및 서비스와 원활 하 게 작업할 수 있는 기능을 제공 합니다. 이러한 타사 응용 프로그램 및 서비스에는 Azure Information Protection 프리미엄 인프라 외부에 있는 타사 시스템에 조직의 고객 콘텐츠를 저장, 전송 및 처리 하는 작업이 포함 될 수 있으므로, 준수 및 데이터 보호 약정에 포함 되지 않습니다. 조직에 이러한 서비스를 적절 하 게 사용 하는 경우 타사에서 제공 하는 개인 정보 및 규정 준수 문을 검토 해야 합니다. 

## <a name="parity-with-azure-information-protection-premium-commercial-offerings"></a>Azure Information Protection Premium 상업용 제품과 동등 

Microsoft는 정부 Azure Information Protection 프리미엄 GCC High 및 DoD 고객에 게 모든 상업용 기능을 제공 하 고, 다음 누락 된 기능 목록에 대해 알고 있어야 합니다.  

7 월 2020을 비롯 하 여 Azure Information Protection 프리미엄 GCC High/DoD와 상용 제품 간의 알려진 기존 격차는 다음과 같습니다.

* 문서 추적 및 해지는 현재 사용할 수 없습니다. 

* 분류 및 레이블 지정 추가 기능은 Microsoft 365 Apps (버전 9126.1001 이상)에 대해서만 지원 됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다. 

* IRM (정보 Rights Management)은 Microsoft 365 앱 (버전 9126.1001 이상)에 대해서만 지원 됩니다. Office 2010, Office 2013 및 기타 Office 2016 버전은 지원되지 않습니다. 

* 현재 상용 클라우드의 사용자에 게 보호 된 문서와 전자 메일을 공유할 수 없습니다. 상용 클라우드의 Microsoft 365 Apps 사용자, 상용 클라우드의 Microsoft 365 없는 앱 사용자 및 개인용 RMS 라이선스가 있는 사용자를 포함 합니다. 

* SharePoint Online이 포함된 정보 권한 관리(IRM 보호된 사이트 및 라이브러리)는 현재 사용할 수 없습니다. 

* 현재 Rights Management 커넥터를 사용할 수 없습니다.

* AD RMS에 대한 모바일 디바이스 확장을 현재 사용할 수 없습니다.


## <a name="configuring-azure-information-protection-unified-labeling-solution-for-gcc-high-and-dod-customers"></a>GCC High 및 DoD 고객을 위한 통합 레이블 솔루션 Azure Information Protection 구성

> [!IMPORTANT]
> 7 월 2020 업데이트를 사용 하는 경우 통합 레이블 솔루션 Azure Information Protection의 모든 *새로운* GCC 상위 고객은 일반 메뉴와 스캐너 메뉴 기능을 모두 사용할 수 있습니다. 

이 섹션에서 제공 하는 구성 세부 정보는 GCC High 및 DoD 고객용 Azure Information Protection 통합 레이블 지정 솔루션에만 해당 됩니다. 기타 모든 구성 정보는 [GCC High 및 DoD 고객에 대 한 표준 구성 정보](#configuring-azure-information-protection-for-gcc-high-and-dod-customers)를 참조 하세요.


### <a name="aip-apps-configuration-unified-labeling-only"></a>AIP 앱 구성 (통합 레이블 전용)

통합 레이블 솔루션의 경우 Windows의 AIP 앱은 올바른 소 버린 클라우드를 가리키도록 특수 레지스트리 키가 필요 합니다. 설정에 올바른 값을 사용 해야 합니다.  

| 레지스트리 노드 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| Name | CloudEnvType |
| 값 | 0/1/2 |
| 형식 | REG_DWORD |
 

| 값  | 자세히  |
|---------|---------|
|상용  |  0 (기본값)     |
|GCC   |     1    |
|GCC High    |    2     |


 
- 레지스트리 키의 기본값은 0입니다. 
- 키가 비어 있거나 잘못 된 경우 예상 되는 동작은 로그에 대 한 인쇄 오류 이며 기본값 (0-상용) 처럼 동작 합니다. 
- 키가 없는 경우에는 기본 (0-상용)으로 동작 합니다.
- 제거한 후에는 레지스트리 키를 삭제 하지 않도록 해야 합니다. 

## <a name="configuring-azure-information-protection-for-gcc-high-and-dod-customers"></a>GCC High 및 DoD 고객용 Azure Information Protection 구성

다음 구성 세부 정보는 통합 레이블 지정 솔루션을 포함 하 여 GCC High 및 DoD 고객에 대 한 모든 Azure Information Protection 솔루션과 관련이 있습니다. 




### <a name="enable-rights-management-for-the-tenant"></a>테넌트에 대해 Rights Management 사용

암호화가 제대로 작동하려면 테넌트에 대해 Rights Management 서비스를 사용하도록 설정해야 합니다.

* Rights Management 서비스가 사용하도록 설정되어 있는지 확인
  * 관리자 권한으로 PowerShell 시작
  * AADRM 모듈이 설치되지 않은 경우 `Install-Module aadrm` 실행 
  * `Connect-aadrmservice -environmentname azureusgovernment` 사용을 통해 서비스 연결
  * `(Get-AadrmConfiguration).FunctionalState`를 실행하고 상태가 `Enabled`인지 확인
* 기능 상태가 `Disabled`인 경우 `Enable-Aadrm` 실행

### <a name="dns-configuration-for-encryption-windows"></a>암호화에 대한 DNS 구성(Windows)
암호화가 제대로 작동 하려면 Office 클라이언트 응용 프로그램에서 서비스의 GCC, GCC High/DoD 인스턴스 및 부트스트랩에 연결 해야 합니다. 클라이언트 응용 프로그램을 올바른 서비스 인스턴스로 리디렉션하려면 테 넌 트 관리자가 Azure RMS URL에 대 한 정보가 포함 된 DNS SRV 레코드를 구성 해야 합니다. DNS SRV 레코드가 없는 경우 클라이언트 응용 프로그램은 기본적으로 공용 클라우드 인스턴스에 연결을 시도 하 고 실패 합니다.

또한 사용자가 onmicrosoft.com username (예:)이 아닌 테 넌 트 소유의 도메인 (예:)을 기반으로 사용자 이름을 사용 하 여 로그인 하는 것으로 가정 합니다. joe@contoso.us joe@contoso.onmicrosoft.us 사용자 이름으로부터 도메인 이름은 올바른 서비스 인스턴스에 대한 DNS 리디렉션에 사용됩니다.

* Rights Management 서비스 ID 획득 
  * 관리자 권한으로 PowerShell 시작 
  * AADRM 모듈이 설치 되어 있지 않으면를 실행 합니다.`Install-Module aadrm`  
  * `Connect-aadrmservice -environmentname azureusgovernment` 사용을 통해 서비스 연결
  * `(Get-aadrmconfiguration).RightsManagementServiceId` 실행을 통해 Rights Management 서비스 ID 획득
* DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동 하 여 새 SRV 레코드를 추가 합니다.
  * Service = `_rmsredir` 
  * Protocol = `_http` 
  * Name = `_tcp` 
  * Target = `[GUID].rms.aadrm.us`(여기서 GUID는 Rights Management 서비스 ID) 
  * Port = `80` 
  * Priority, Weight, Seconds, TTL = 기본값 
* [Azure Portal](https://portal.azure.us/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)에 있는 테넌트와 사용자 지정 도메인을 연결합니다. 사용자 지정 도메인을 연결 하면 DNS에 항목이 추가 됩니다. 값을 추가한 후에는이를 확인 하는 데 몇 분 정도 걸릴 수 있습니다.   
* 해당 하는 전역 관리자 자격 증명을 사용 하 여 Office 관리 센터에 로그인 하 고 사용자 만들기를 위한 도메인 (예: contoso.us)을 추가 합니다. 확인 프로세스에서 일부 DNS 변경이 필요할 수 있습니다. 확인이 완료되면 사용자가 생성될 수 있습니다.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>암호화에 대한 DNS 구성(Mac, iOS, Android)
* DNS 공급자에 로그인 하 고 도메인에 대 한 DNS 설정으로 이동 하 여 새 SRV 레코드를 추가 합니다.
  * Service = `_rmsdisco` 
  * Protocol = `_http` 
  * Name = `_tcp` 
  * Target = `api.aadrm.us` 
  * Port = `80` 
  * Priority, Weight, Seconds, TTL = 기본값 

### <a name="label-migration"></a>레이블 마이그레이션

GCC High 고객은 PowerShell을 사용 하 여 모든 기존 레이블을 마이그레이션해야 합니다. 기존 AIP 마이그레이션 방법은 GCC High 고객에 게는 적용 **되지 않습니다** . 

[새 레이블](https://docs.microsoft.com/powershell/module/exchange/new-label?view=exchange-ps) cmdlet을 사용 하 여 기존 민감도 레이블을 마이그레이션합니다. 마이그레이션을 시작 하기 전에 [보안 & 준수 센터를 사용 하 여 cmdlet을 연결 하 고 실행 하는 방법에 대 한 지침](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps#connect-to-the-security--compliance-center) 을 따르세요. 

기존 민감도 레이블에 암호화가 있는 경우의 마이그레이션 예:

```powershell
New-Label -Name 'aipscopetest' -Tooltip 'aipscopetest' -Comment 'admin notes' -DisplayName 'aipscopetest' -Identity 'b342447b-eab9-ea11-8360-001a7dda7113' -EncryptionEnabled $true -EncryptionProtectionType 'template' -EncryptionTemplateId 'a32027d7-ea77-4ba8-b2a9-7101a4e44d89' -EncryptionAipTemplateScopes "['allcompany@labelaction.onmicrosoft.com','admin@labelaction.onmicrosoft.com']"
```

### <a name="aip-apps-configuration"></a>AIP 앱 구성

Windows의 AIP 앱은 특수 레지스트리 키를 GCC High/DoD에 대한 올바른 서비스 인스턴스로 가리켜야 합니다.  

| 레지스트리 노드 | HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP |
| --- | --- |
| Name | WebServiceUrl |
| 값 | https://api.informationprotection.azure.us |
| 형식 | REG_SZ (String) |


## <a name="firewalls-and-network-infrastructure"></a>방화벽 및 네트워크 인프라

특정 연결을 허용 하도록 구성 된 방화벽 또는 유사한 중개 네트워크 장치가 있는 경우 이러한 설정을 사용 하 여 Azure Information Protection에 대 한 원활한 통신을 보장 합니다.

- Azure Information Protection 클래식 클라이언트에서 레이블 및 레이블 정책을 다운로드 하도록 설정 하려면: HTTPS를 통한 URL **Api.informationprotection.azure.us** 허용 합니다.

- **Rms.aadrm.us** URL에 대 한 TLS 클라이언트-서비스 연결을 종료 하지 마세요 (예: 패킷 수준 검사 수행). 

다음 PowerShell 명령을 사용 하 여 Azure Rights Management 서비스에 도달 하기 전에 클라이언트 연결이 종료 되는지 여부를 확인할 수 있습니다.

```powershell
$request = [System.Net.HttpWebRequest]::Create("https://admin.aadrm.us/admin/admin.svc")
$request.GetResponse()
$request.ServicePoint.Certificate.Issuer
```


결과에는 발급 CA가 Microsoft CA에서 온 것으로 표시 됩니다 (예:) `CN=Microsoft Secure Server CA 2011, O=Microsoft Corporation, L=Redmond, S=Washington, C=US` . Microsoft에서 발급 하지 않은 발급 CA 이름이 표시 되는 경우 보안 클라이언트-서비스 연결이 종료 되어 방화벽에서 다시 구성 해야 할 수 있습니다.

## <a name="service-tags"></a>서비스 태그

다음 **서비스 태그**의 모든 포트에 대 한 액세스를 허용 해야 합니다.
*    **AzureInformationProtection**
*    **AzureActiveDirectory**
*    **AzureFrontDoor.Frontend**
