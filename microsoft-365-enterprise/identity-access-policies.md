---
title: "ID 및 장치 액세스 정책 개요 - Microsoft 365 Enterprise | Microsoft Docs"
description: "ID 및 장치 액세스 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 10/27/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 46a63151471a10b578ffaf3bddb27ddfcd5500a5
ms.sourcegitcommit: feb1e385af0bc2a2eba56e5c2d1e8b4ba8866126
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="general-identity-and-device-access-policy-recommendations"></a>일반적인 ID 및 장치 액세스 정책 권장 사항
이 문서에서는 Microsoft 365 Enterprise 보안을 유지할 수 있는 일반적인 권장 정책을 설명합니다. 조건부 액세스에 대한 기술적인 필수 구성 요소뿐만 아니라 사용자에게 최상의 SSO 환경을 제공하기 위해 Microsoft에서 권장하는 기본 플랫폼 클라이언트 구성에 대해서도 설명합니다.

이 지침은 새로 프로비전한 환경에 권장되는 정책을 배포하는 방법에 대해 설명합니다. 별도의 랩 환경에서 이러한 정책을 설정하면 프리 프로덕션 및 프로덕션 환경으로 롤아웃을 준비하기 전에 권장되는 정책을 이해하고 평가할 수 있습니다. 새로 프로비전한 환경은 클라우드 전용 또는 하이브리드일 수 있습니다.  

권장되는 정책을 성공적으로 배포하려면 Azure Portal에서 앞서 말한 필수 구성 요소에 맞는 조치를 취해야 합니다. 특히 다음을 수행해야 합니다.
* Azure ID 보호에서 위험 점수를 올바르게 생성할 수 있도록 명명된 네트워크 구성
* 모든 사용자에게 다단계 인증(MFA)에 맞게 등록하도록 요구
* 사용자가 직접 암호를 재설정할 수 있도록 암호 동기화 및 셀프 서비스 암호 재설정 구성

특정 사용자 그룹을 대상으로 특별한 Azure AD 및 Intune 정책을 만들 수 있습니다. 이전에 준비된 방법으로 정의한 정책을 롤아웃하는 것이 좋습니다. 이렇게 하면 정책을 기준으로 정책 및 지원 팀의 성능에 대해 증분 방식으로 유효성을 검사할 수 있습니다.


## <a name="prerequisites"></a>전제 조건

이 문서의 나머지 부분에서 설명하는 정책을 구현하기 전에 조직이 충족해야 하는 몇 가지 필수 구성 요소가 있습니다.
* [명명된 네트워크 구성](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD ID 보호는 모든 사용 가능한 세션 데이터를 수집하고 분석하여 위험 점수를 생성합니다. 네트워크에 대한 조직의 공용 IP 범위를 Azure AD 명명된 네트워크 구성에 지정하는 것이 좋습니다. 이러한 범위에서 시작하는 트래픽에는 감소된 위험 점수를 지정하므로 회사 환경 외부에서 오는 트래픽은 더 높은 위험 점수로 처리됩니다.
* [다단계 인증(MFA)을 사용하여 모든 사용자 등록](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-manage-users-and-devices). Azure AD ID 보호에서는 Azure MFA를 사용하여 추가 보안 확인을 수행하도록 합니다. 모든 사용자가 Azure MFA에 미리 등록하도록 요구하는 것이 좋습니다.
* [도메이에 가입된 Windows 컴퓨터에 대해 자동 장치 등록 사용](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). 조건부 액세스를 통해 서비스에 연결하는 장치가 도메인에 가입되거나 호환되는 장치가 되도록 할 수 있습니다. Windows 컴퓨터에서 이 기능을 지원하려면 Azure AD를 사용하여 장치를 등록해야 합니다.  이 문서에서는 자동 장치 등록을 구성하는 방법에 대해 설명합니다.  참고로 AD FS는 요구 사항입니다.
* **사용자의 지원 팀 준비**. MFA를 완료할 수 없는 사용자에 대한 계획을 시행합니다. 이러한 사용자를 정책 제외 그룹에 추가하거나 이들에 대한 새 MFA 정보를 등록하면 됩니다. 이러한 보안에 중요한 변경을 하기 전에 실제 사용자가 요청을 하도록 해야 합니다. 사용자의 관리자에 대해 승인을 통해 도움을 주도록 요구하는 것이 효과적인 단계입니다.
* [온-프레미스 AD에 대한 암호 쓰기 저장 구성](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). 암호 쓰기 저장을 사용하여 Azure AD는 높은 계정 손상 위험이 검색된 경우 사용자가 자신의 온-프레미스 암호를 변경하도록 요구할 수 있습니다. Azure AD Connect를 둘 중의 한 가지 방법으로 사용하여 이 기능을 활성화할 수 있습니다. Azure AD Connect 설정 마법사의 선택적 기능 화면에서 암호 쓰기 저장을 사용하도록 설정하거나 Windows PowerShell을 통해 사용하도록 설정할 수 있습니다.  
* [최신 인증 사용](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) 및 [레거시 끝점 보호](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-supported-apps).  조건부 액세스는 최신 인증을 사용하는 모바일 및 데스크톱 응용 프로그램에서 모두 작동합니다. 응용 프로그램이 레거시 인증 프로토콜을 사용하는 경우 적용하는 조건과 상관없이 액세스 권한을 획득할 수 있습니다. 조건부 액세스 규칙 및 다른 응용 프로그램 진입점을 보호하기 위해 실행해야 하는 단계를 사용할 수 있는 응용 프로그램을 알고 있어야 합니다.
* Rights Management를 사용하도록 설정하여 [Azure Information Protection 활성화](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1)t. 메일에 Azure Information Protection을 사용하여 메일 분류를 시작합니다. 빠른 시작 자습서에 따라 정책을 사용자 지정하고 게시합니다.  

### <a name="recommended-email-clients"></a>권장되는 메일 클라이언트
다음 메일 클라이언트는 최신 인증 및 조건부 액세스를 지원합니다. Azure Information Protection은 일부 클라이언트의 경우 아직 사용할 수 없습니다.

|플랫폼|클라이언트|버전/참고|Azure Information Protection|
|:-------|:-----|:------------|:--------------------|
|**Windows**|Outlook|2016, 2013 [최신 인증 사용](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)|예|
|**iOS**|Outlook|[최신](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|아니요|
|**Android**|Outlook|[최신](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|아니요|
|**macOS**|공개 미리 보기||아니요|
|**Linux**|지원되지 않음||아니요|

Azure Information Protection의 보호된 문서에 액세스하려면 추가 소프트웨어가 필요할 수 있습니다. Azure Information Protection을 사용하여 보호된 문서를 만들고 보려면 [지원되는 소프트웨어 및 문서 형식](https://docs.microsoft.com/information-protection/get-started/requirements-applications)을 사용해야 합니다.


### <a name="recommended-client-platforms-when-securing-documents"></a>문서를 보호할 때 권장되는 클라이언트 플랫폼
보안 문서 정책을 적용한 경우 다음 클라이언트를 권장합니다.

|플랫폼|Word/Excel/PowerPoint|OneNote|OneDrive 앱|SharePoint 앱|OneDrive 동기화 클라이언트|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 8.1|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows 10|지원됨|지원됨|해당 없음|해당 없음|미리 보기<sup>*</sup>|
|Windows Phone 10|지원되지 않음|지원되지 않음|지원됨|지원됨|해당 없음|
|Android|지원됨|지원됨|지원됨|지원됨|해당 없음|
|iOS|지원됨|지원됨|지원됨|지원됨|해당 없음|
|macOS|공개 미리 보기|공개 미리 보기|해당 없음|해당 없음|지원되지 않음|
|Linux|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|지원되지 않음|

<sup>*</sup> [OneDrive 동기화 클라이언트 미리 보기](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)에 대해 자세히 알아보기.

> [!NOTE]
> 다음 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 메일 보안 및 보호 계층 **기준**, **중요** 및 **높은 규제**를 기준으로 합니다. [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.


## <a name="baseline"></a>기준
이 섹션에서는 데이터, ID 및 장치 보호의 기준 계층에 대한 권장 사항을 설명합니다. 이러한 권장 사항은 많은 조직의 기본 보호 요구를 충족할 것입니다.

>[!NOTE]
>아래 정책은 가산적이며 서로를 기반으로 합니다. 각 섹션에서는 각 계층에 적용되는 추가 사항만 설명합니다.
>

### <a name="conditional-access-policy-settings"></a>조건부 액세스 정책 설정

#### <a name="identity-protection"></a>ID 보호
앞의 섹션에서 설명하였듯이 사용자에게 SSO(Single Sign-On) 경험을 제공할 수 있습니다. [위험 이벤트](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events)를 기반으로 필요한 경우에만 개입하면 됩니다.  

* **중간 이상** 로그인 위험을 기반으로 MFA 요구
* **높은** 위험 사용자에 대해 보안 암호 변경 요구

>[!IMPORTANT]
>이 정책 권장 사항을 위해 [암호 동기화](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) 및 [셀프 서비스 암호 재설정](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)이 필요합니다.
>

#### <a name="data-loss-prevention"></a>데이터 손실 방지
장치 및 앱 관리 정책의 목표는 장치를 분실하거나 도난당한 경우 데이터 손실을 방지하는 것입니다. PIN에 의해 데이터 액세스를 보호하고 장치에서 데이터를 암호화하고 장치가 손상되지 않도록 하면 됩니다.

|정책 권장 사항|설명|
|:--------------------|:----------|
|**사용자 PC 관리 요구**|사용자에게 자신의 Windows PC를 Active Directory 도메인에 가입하거나 Microsoft Intune 또는 System Center Configuration Manager를 사용하여 자신의 PC를 관리 대상으로 등록하도록 요구합니다.|
|**도메인에 가입된 PC에 대해 그룹 정책 개체(GPO) 또는 구성 관리자 정책을 통해 보안 설정 적용**|관리되는 PC를 BitLocker, 바이러스 백신 및 방화벽을 사용하도록 구성하는 정책을 배포합니다.|
|**사용자 모바일 장치 관리 요구**|메일에 액세스하는 데 사용하는 사용자 장치를 Intune에 의해 관리하거나 **또는** 회사 메일을 Outlook Mobile 같은 Intune 앱 보호 정책에 의해 보호되는 모바일 메일 앱을 통해서만 액세스하도록 요구합니다.|
|**관리되는 장치에 대한 Intune 장치 준수 정책 적용**|관리되는 회사 모바일 장치 및 Intune 관리되는 PC에 대해 최소 길이 6의 PIN, 장치 암호화, 문제 없는 장치(무단 해제되거나 루팅되지 않은, 상태 증명 전달)를 요구하고 사용 가능한 경우 Lookout 또는 SkyCure 등 타사 MTP에서 **낮은** 위험으로 결정된 장치를 요구하는 Intune 장치 준수 정책을 적용합니다.|
|**관리되지 않는 장치에서 실행하는 관리되는 앱에 대해 Intune 앱 보호 정책 적용**|관리되지 않는 개인 모바일 장치에서 실행하는 관리되는 앱에 대해 최소 길이 6의 PIN, 장치 암호화, 그리고 장치가 문제 없음(무단 해제되거나 루팅되지 않은, 상태 증명 전달)을 요구하는 Intune 앱 보호 정책을 적용합니다.|

### <a name="user-impact"></a>사용자 영향

대부분의 조직의 경우, 메일에 액세스하기 위해 Office 365에 로그인할 것으로 예상되는 시기와 조건에 대한 사용자 기대치를 설정할 수 있어야 합니다.  

사용자는 일반적으로 다음과 같은 상황을 제외하고 SSO(Single Sign-On)를 사용하는 것이 좋습니다.
* Exchange Online에 대한 인증 토큰을 요청하는 경우:
  * 사용자에 대해 **중간 이상** 로그인 위험이 검색되었는데 사용자가 현재 세션에서 아직 MFA를 수행하지 않은 경우마다 MFA를 요구할 수 있습니다.  
  * 사용자에 대해 Intune 앱 보호 SDK를 지원하는 메일 앱을 사용하거나 Intune 호환 또는 AD 도메인에 가입된 장치에서 메일에 액세스하도록 요구합니다.
* 위험에 처한 사용자가 로그인하고 성공적으로 MFA를 완료한 경우 암호 변경을 요구합니다.

## <a name="sensitive"></a>중요
이 섹션에서는 데이터, ID 및 장치 보호의 중요 계층에 대한 권장 사항을 설명합니다. 이 권장 사항은 더 높은 수준으로 보호해야 하거나 모든 데이터를 이처럼 더 높은 수준에서 보호해야 하는 데이터의 하위 집합을 가지고 있는 고객에게 적용됩니다.

Office 365 환경의 모든 또는 특정 데이터 집합에 대해 증가된 보호를 적용할 수 있습니다. 예를 들어 데이터 손실을 방지하기 위해 중요 데이터를 보호되는 앱 간에만 공유하도록 하는 정책을 적용할 수 있습니다. 중요 데이터에 액세스하는 ID와 장치를 유사한 보안 수준으로 보호하는 것이 좋습니다.

### <a name="conditional-access-policy-settings"></a>조건부 액세스 정책 설정
#### <a name="identity-protection"></a>ID 보호

앞의 섹션에서 설명하였듯이 사용자에게 SSO(Single Sign-On) 경험을 제공할 수 있습니다. [위험 이벤트](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events)를 기반으로 필요한 경우에만 개입하면 됩니다.   

* **낮음 이상** 위험에 대해 MFA 요구
* 높은 위험 사용자에 대해 보안 암호 변경 요구

>[!IMPORTANT]
>이 정책 권장 사항을 위해 [암호 동기화](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) 및 [셀프 서비스 암호 재설정](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)이 필요합니다.
>

#### <a name="data-loss-prevention"></a>데이터 손실 방지

이러한 장치 및 앱 관리 정책의 목표는 장치를 분실하거나 도난당한 경우 데이터 손실을 방지하는 것입니다. PIN에 의해 데이터 액세스를 보호하고 장치에서 데이터를 암호화하고 장치가 손상되지 않도록 하면 됩니다.

|정책 권장 사항|설명|
|:--------------------|:----------|
|**사용자 PC 관리 요구**|메일 액세스를 허용하기 전에 사용자에 대해 자신의 PC를 Active Directory 도메인에 가입하거나 Intune 또는 구성 관리자를 사용하여 자신의 PC를 관리 대상으로 등록하고 해당 장치가 정책을 준수하도록 할 것을 요구합니다.|
|**도메인에 가입된 PC에 대해 그룹 정책 개체(GPO) 또는 구성 관리자 정책을 통해 보안 설정 적용**|관리되는 PC를 BitLocker, 바이러스 백신 및 방화벽을 사용하도록 구성하는 정책을 배포합니다.|
|**사용자 모바일 장치 관리 요구**|메일에 액세스하는 데 사용하는 사용자 장치를 Intune에 의해 관리하거나 **또는** 회사 메일을 Outlook Mobile 같은 Intune 앱 보호 정책에 의해 보호되는 모바일 메일 앱을 통해서만 액세스하도록 요구합니다.|
|**관리되는 장치에 대한 Intune 장치 준수 정책 적용**|관리되는 회사 모바일 장치 및 Intune 관리되는 PC에 대해 최소 길이 6의 PIN, 장치 암호화, 문제 없는 장치(무단 해제되거나 루팅되지 않은, 상태 증명 전달)를 요구하고 사용 가능한 경우 Lookout 또는 SkyCure 등 타사 MTP에서 **낮은** 위험으로 결정된 장치를 요구하는 Intune 장치 준수 정책을 적용합니다.|
|**관리되지 않는 장치에서 실행하는 관리되는 앱에 대해 Intune 앱 보호 정책 적용**|관리되지 않는 개인 모바일 장치에서 실행하는 관리되는 앱에 대해 최소 길이 6의 PIN, 장치 암호화, 그리고 장치가 문제 없음(무단 해제되거나 루팅되지 않은, 상태 증명 전달)을 요구하는 Intune 앱 보호 정책을 적용합니다.|

### <a name="user-impact"></a>사용자 영향
대부분의 조직의 경우, Office 365 메일에 로그인할 것으로 예상되는 시기와 조건에 맞게 사용자에 대한 기대치를 설정할 수 있어야 합니다.

사용자는 일반적으로 다음과 같은 상황을 제외하고 SSO(Single Sign-On)를 사용하는 것이 좋습니다.
* Exchange Online에 대한 인증 토큰을 요청하는 경우:
  * 사용자에 대해 **낮음 이상** 로그인 위험이 검색되었는데 사용자가 현재 세션에서 아직 MFA를 수행하지 않은 경우마다 MFA를 요구합니다.  
  * 사용자에 대해 Intune 앱 보호 SDK를 지원하는 메일 앱을 사용하거나 Intune 호환 또는 AD 도메인에 가입된 장치에서 메일에 액세스하도록 요구합니다.
* 위험에 처한 사용자가 로그인하고 성공적으로 MFA를 완료한 경우 암호 변경을 요구합니다.

## <a name="highly-regulated"></a>높은 규제
이 섹션에서는 데이터, ID 및 장치 보호의 높은 규제 계층에 대한 권장 사항을 설명합니다. 이러한 권장 사항은 높은 수준의 대외비, 거래 비밀 또는 규제 대상 데이터인 아주 적은 양의 데이터가 있는 고객에 대한 것입니다. Microsoft는 ID와 장치에 대한 추가된 보호를 포함하여 조직이 이러한 요구 사항을 충족하는 데 도움이 되는 기능을 제공합니다.

### <a name="conditional-access-policy-settings"></a>조건부 액세스 정책 설정
#### <a name="identity-protection"></a>ID 보호

높은 규제 계층의 경우 모든 새 세션에 대해 MFA를 강제 적용하는 것이 좋습니다.
* 모든 새 세션에 대해 MFA 요구
* **높은** 위험 사용자에 대해 보안 암호 변경 요구

>[!IMPORTANT]
>이 정책 권장 사항을 위해 [암호 동기화](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) 및 [셀프 서비스 암호 재설정](https://docs.microsoft.com/azure/active-directory/active-directory-passwords)이 필요합니다.
>

#### <a name="data-loss-prevention"></a>데이터 손실 방지
이러한 장치 및 앱 관리 정책의 목표는 장치를 분실하거나 도난당한 경우 데이터 손실을 방지하는 것입니다. PIN에 의해 데이터 액세스를 보호하고 장치에서 데이터를 암호화하고 장치가 손상되지 않도록 하면 됩니다.

높은 규제 계층의 경우 Intune 앱 보호 정책을 지원하는 앱에 대해 Intune 호환 또는 도메인에 가입된 장치에서만 실행할 것을 요구하는 것이 좋습니다.

|정책 권장 사항|설명|
|:--------------------|:----------|
|**사용자 PC 관리 요구**|메일 액세스를 허용하기 전에 사용자에 대해 자신의 Windows PC를 Active Directory 도메인에 가입하거나 **또는** Intune 또는 구성 관리자를 사용하여 자신의 PC를 관리 대상으로 등록하고 해당 장치가 정책을 준수하도록 할 것을 요구합니다.|
|**도메인에 가입된 PC에 대해 그룹 정책 개체(GPO) 또는 구성 관리자 정책을 통해 보안 설정 적용**|관리되는 PC를 BitLocker, 바이러스 백신 및 방화벽을 사용하도록 구성하는 정책을 배포합니다.|
|**사용자 모바일 장치 관리 요구**|Office 365 메일 및 파일에 액세스하는 데 사용하는 장치를 Intune에 의해 관리하거나 회사 메일을 Outlook Mobile 같은 Intune 앱 보호 정책에 의해 보호되는 모바일 메일 앱을 통해서만 액세스하도록 요구합니다.|
|**관리되는 장치에 대한 Intune 장치 준수 정책 적용**|관리되는 회사 모바일 장치 및 Intune 관리되는 PC에 대해 최소 길이 6의 PIN, 장치 암호화, 문제 없는 장치(무단 해제되거나 루팅되지 않은, 상태 증명 전달)를 요구하고 사용 가능한 경우 Lookout 또는 SkyCure 등 타사 MTP에서 낮은 위험으로 결정된 장치를 요구하는 Intune 장치 준수 정책을 적용합니다.|

### <a name="user-impact"></a>사용자 영향
대부분의 조직의 경우, Office 365 파일에 로그인할 것으로 예상되는 시기와 조건에 맞게 사용자에 대한 기대치를 설정할 수 있어야 합니다.

* 높은 규제로 구성된 사용자는 세션이 완료된 후 MFA를 사용하여 다시 인증을 받아야 합니다.
* 위험에 처한 사용자가 로그인하면 성공적으로 MFA를 완료한 후 암호 변경을 요구합니다.
* Exchange Online에 대한 인증 토큰을 요청하는 경우:
  * 사용자에 대해 새 세션을 시작할 때마다 MFA를 수행할 것을 요구합니다.  
  * 사용자는 Intune 앱 보호 SDK를 지원하는 메일 앱을 사용해야 함
  * 사용자는 Intune 호환 또는 AD 도메인에 가입된 장치에서 메일에 액세스해야 합니다.

## <a name="next-steps"></a>다음 단계

[메일을 보호하기 위한 정책 권장 사항에 대해 알아보기](secure-email-recommended-policies.md)
