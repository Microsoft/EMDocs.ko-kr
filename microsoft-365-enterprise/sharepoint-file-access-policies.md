---
title: "권장되는 보안 문서 정책 - Microsoft 365 Enterprise | Microsoft Docs"
description: "SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다."
author: jeffgilb
manager: femila
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 8d38b1f9f899bcf61b1d35c8962a6829ce3d9a56
ms.sourcegitcommit: 0e0a15476e3bbd2d4ac6101c2cedd02e082ee25d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2017
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항
다음 권장 사항은 [일반적인 ID 및 액세스 정책 권장 사항](identity-access-policies.md) 및 [메일 보호 정책 권장 사항](secure-email-recommended-policies.md)에 *더하여* 제공됩니다. SharePoint Online 파일을 보호하려면 새로운 정책을 만들고 기존 정책을 여기에 설명한 대로 수정해야 합니다. 

다음 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 SharePoint 보안 및 보호 계층 **기준**, **중요** 및 **높은 규제**를 기준으로 합니다. [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.

>[!NOTE]
>이러한 권장 사항의 일부로 만드는 모든 보안 그룹은 Office 기능을 사용하도록 설정한 상태에서 만들어야 합니다. 이 지침은 SharePoint에서 문서를 보호할 때 AIP 배포를 위해 특히 중요합니다. 
>
>![보안 그룹에 대해 활성화되는 Office 기능](./media/security-group.png)
>

## <a name="baseline"></a>기준 

### <a name="medium-and-above-risk-requires-mfa"></a>중간 이상 위험의 경우 MFA 필요
[메일을 보호하기 위한 정책 권장 사항](secure-email-recommended-policies.md)을 적용할 때 만들어진 기존 CA 정책을 다음과 같이 변경:

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|할당|클라우드 앱|포함|앱 선택:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|모두 선택|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요
SharePoint Online에 대한 새 Intune 조건부 액세스 정책을 만들려면 사용자의 관리자 자격 증명을 사용하여 [Microsoft Management Portal](http://manage.microsoft.com)에 로그인하고 **정책** > **조건부 액세스** > **SharePoint Online 정책**으로 이동합니다.

![SharePoint Online 정책](./media/secure-docs/sharepoint-online-policy.png)

호환되거나 도메인에 가입된 장치를 요구하려면 Intune 관리 포털에서 SharePoint Online에 대해 명시적으로 조건부 액세스 정책을 설정해야 합니다.
| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|**응용 프로그램 액세스**|최신 인증을 사용하는 비즈니스용 OneDrive 및 기타 앱|모든 플랫폼|True|선택|
|     |     |Windows는 다음 요구 사항을 충족해야 함|장치가 도메인에 가입되어 있거나 호환되어야 함|선택됨(목록)|
|     |     |특정 플랫폼|False||
|     |SharePoint 및 비즈니스용 OneDrive에 대한 브라우저 액세스 |비즈니스용 OneDrive와 동일한 플랫폼에서 비규격 장치 차단|True|Check|
|**정책 배포**|대상이 지정된 그룹|이 정책의 대상으로 지정할 Active Directory 그룹 선택|     |     |
|     |     |모든 사용자|False|     |
|     |     |선택된 보안 그룹|True|선택|
|     |     |수정|대상 사용자를 포함하는 특정 보안 그룹을 선택합니다.|     |
|     |제외 그룹|이 정책에서 제외할 Active Directory 그룹을 선택합니다(대상이 지정된 그룹 목록의 멤 재정의).|     |     |    
|     |     |제외 사용자 없음|True|선택|
|     |     |선택된 보안 그룹|False|     |

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스

모바일 앱을 관리하려면 Intune 관리 포털에서 SharePoint Online에 대해 명시적으로 조건부 액세스 정책을 설정해야 합니다.

모바일 앱을 관리하려면 사용자의 관리자 자격 증명을 사용하여 Microsoft Azure Portal에 로그인한 다음 **Intune 앱 보호** > **설정** > **조건부 액세스** > **SharePoint Online**으로 이동합니다.

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|**앱 액세스**|허용되는 앱|앱 액세스 사용|Intune 앱 정책을 지원하는 앱 허용|선택됨(목록) – Intune 앱 정책에서 지원하는 앱/플랫폼 조합의 목록이 표시됩니다.|
|**사용자 액세스**|     |제한된 사용자 그룹|사용자 그룹 추가 – 대상 사용자를 포함하는 특정 보안 그룹을 선택합니다.|파일럿 사용자를 포함한 보안 그룹으로 시작합니다.|
|     |     |예외 사용자 그룹|예외 보안 그룹|     |

### <a name="apply-to"></a>적용 대상

파일럿 프로젝트가 완료된 후 이 정책을 조직의 모든 사용자에게 적용해야 합니다.

## <a name="sensitive"></a>중요 

### <a name="low-and-above-risk-requires-mfa"></a>낮음 이상 위험의 경우 MFA 필요

[메일을 보호하기 위한 정책 권장 사항](secure-email-recommended-policies.md)을 적용할 때 만들어진 기존 CA 정책을 다음과 같이 변경:

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|할당|클라우드 앱|포함|앱 선택:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|모두 선택|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요

(기준 지침 참조)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스

(기준 지침 참조)

## <a name="highly-regulated"></a>높은 규제 

### <a name="mfa-required"></a>MFA 필요

[메일을 보호하기 위한 정책 권장 사항](secure-email-recommended-policies.md)을 적용할 때 만들어진 기존 CA 정책을 다음과 같이 변경:

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|할당|클라우드 앱|포함|앱 선택:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|모두 선택|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요
(기준 지침 참조)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스
(기준 지침 참조)

## <a name="additional-configurations"></a>추가 구성
위의 정책에 더하여 최신 인증을 지원하지 않는 레거시 프로토콜을 잠그기도 해야 합니다.

### <a name="lock-down-legacy-protocols"></a>레거시 프로토콜 잠그기
조건부 액세스 정책은 Office 2016 및 지원되는 플랫폼 목록의 앱 등과 같은 최신 인증을 사용하여 브라우저 흐름 및 앱을 통한 액세스를 보호합니다. Office 2010 등의 이전 Office 데스크톱 응용 프로그램의 경우 조건부 액세스 정책이 적용되지 않습니다. 

[OneDrive 관리 포털을 사용하여](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08) 최신 인증을 사용하지 않는 이전의 앱을 차단할 수 있습니다. SharePoint 관리 PowerShell cmdlet을 사용하여 SharePoint 레거시 프로토콜을 사용하지 않도록 설정할 수도 있습니다. PowerShell을 사용하려면 [Set-SPOTenant cmdlet](https://technet.microsoft.com/library/fp161390.aspx)을 실행하고 **-LegacyAuthProtocolsEnabled**를 **$false**로 설정합니다.  설정한 후 레거시 프로토콜 지원이 비활성화되고 이전 클라이언트 응용 프로그램을 사용하는 모든 SharePoint 액세스가 차단됩니다.
                                                     
## <a name="next-steps"></a>다음 단계
[Microsoft 365 서비스에 대해 자세히 알아보기](index.md)
