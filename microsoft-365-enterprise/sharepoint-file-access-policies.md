---
title: "권장되는 보안 문서 정책 - Microsoft 365 Enterprise | Microsoft Docs"
description: "SharePoint 파일 액세스를 보호하는 방법에 관한 Microsoft 권장 정책을 설명합니다."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 3eabab5a19c99fe97d56ed3d802c026c0b0bc6ef
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항
다음 권장 사항은 [일반적인 ID 및 액세스 정책 권장 사항](identity-access-policies.md) 및 [메일 보호 정책 권장 사항](secure-email-recommended-policies.md)에 *더하여* 제공됩니다. SharePoint Online 파일을 보호하려면 새로운 정책을 만들고 기존 정책을 여기에 설명한 대로 수정해야 합니다.

다음 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 메일 보안 및 보호 계층을 기준으로 합니다.

- **기준**: 본인의 데이터에 액세스하는 ID와 장치뿐만 아니라 데이터를 보호하기 위해서도 최소 표준을 설정하는 것이 좋습니다. Microsoft에서는 많은 조직의 요구를 충족하는 강력한 기본 보호를 제공합니다. 일부 조직에서는 기본 요구 사항을 충족하기 위해 추가 기능이 필요합니다.
- **중요**: 일부 고객은 높은 수준에서 보호해야 하는 데이터 하위 집합을 포함하고 있습니다. Office 365 환경의 특정 데이터 집합에 대해 증가된 보호를 적용할 수 있습니다. 중요 데이터에 액세스하는 ID와 장치를 유사한 보안 수준으로 보호하는 것이 좋습니다. 
- **높은 규제**: 일부 조직에는 높은 수준의 대외비, 거래 비밀 또는 규제 대상 데이터인 아주 적은 양의 데이터가 있을 수 있습니다. Microsoft는 ID와 장치에 대한 추가된 보호를 포함하여 조직이 이러한 요구 사항을 충족하는 데 도움이 되는 기능을 제공합니다.

자세한 내용은 [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md) 항목을 참조하세요.

> [!IMPORTANT]
> 이러한 권장 사항의 일부로 만드는 모든 보안 그룹은 Office 기능을 사용하도록 설정한 상태에서 만들어야 합니다. 이 지침은 SharePoint에서 문서를 보호할 때 AIP(Azure Information Protection) 배포를 위해 특히 중요합니다.
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

Exchange Online에 대해 조건부 액세스 정책을 만들려면,

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱 선택**을 선택하고, **클라우드 앱** 목록에서 **Office 365 SharePoint Online**을 선택하고 **선택**을 클릭합니다. **Office 365 SharePoint Online** 앱을 선택한 후 **완료**를 클릭합니다.

8. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

9. **액세스 권한 부여**를 선택하고 **준수 상태로 표시된 장치 필요** 및 **도메인 조인 필요(하이브리드 Azure AD)**를 둘 다 선택한 후 **선택**을 선택합니다.

10. **만들기**를 클릭하여 Exchange Online 조건부 액세스 정책을 만듭니다.

    > [!NOTE]
    > Azure의 Intune에서부터, Azure Active Directory 워크로드에서 모든 조건부 액세스 정책을 만들어야 합니다. Intune은 편의를 위해 포털에서 Azure AD 조건부 액세스 정책 워크로드에 대한 링크를 제공합니다.

    > [!IMPORTANT]
    > Intune 클래식 포털에서 이전에 만든 조건부 액세스 정책을 Azure Portal의 Intune으로 마이그레이션하는 데 도움이 필요한 경우 [Intune 클래식 포털에서 Azure Portal로 조건부 액세스 정책 다시 할당](https://docs.microsoft.com/intune/conditional-access-intune-reassign) 항목을 참조하세요. 

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 앱 기반 조건부 액세스

Azure Portal에서 Intune의 SharePoint Online에 대한 앱 기반 조건부 액세스 정책을 설정하여 보안 계층을 하나 이상 추가할 수 있습니다. SharePoint Online에 대한 앱 기반 조건부 액세스를 적용하는 경우 사용자가 회사 리소스에 액세스하기 위해 이 앱만 사용해야 합니다.

앱 기반 조건부 액세스 정책을 추가하려면,

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 Intune 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.

2. 왼쪽 메뉴에서 **추가 서비스**를 선택한 다음 "**Intune**"을 입력합니다.

3. **Intune 앱 보호**를 선택합니다.

4. **Intune 모바일 응용 프로그램 관리** 블레이드에서 **모든 설정**을 선택합니다.

5. **조건부 액세스** 섹션에서 **Exchange Online**을 선택합니다.

6. **Intune 앱 정책을 지원하는 앱 허용**을 선택한 후 앱(E.g. Microsoft Outlook)을 선택합니다.

7. **제한된 사용자 그룹**을 선택하고 **그룹 선택**을 클릭하고 정책을 적용할 사용자 또는 그룹을 선택한 후 **선택**을 클릭합니다.

## <a name="sensitive"></a>중요

### <a name="low-and-above-risk-requires-mfa"></a>낮음 이상 위험의 경우 MFA 필요

[메일을 보호하기 위한 정책 권장 사항](secure-email-recommended-policies.md)을 적용할 때 만들어진 기존 CA 정책을 다음과 같이 변경:

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|할당|클라우드 앱|포함|앱 선택:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|모두 선택|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요

(기준 지침 참조)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 앱 기반 조건부 액세스

(기준 지침 참조)

## <a name="highly-regulated"></a>높은 규제

### <a name="mfa-required"></a>MFA 필요

[메일을 보호하기 위한 정책 권장 사항](secure-email-recommended-policies.md)을 적용할 때 만들어진 기존 CA 정책을 다음과 같이 변경:

| Category|유형|속성|값|참고|
|:-----|:-----|:-----|:-----|:-----|
|할당|클라우드 앱|포함|앱 선택:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|모두 선택|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요
(기준 지침 참조)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>SharePoint Online에 대한 앱 기반 조건부 액세스
(기준 지침 참조)

## <a name="additional-configurations"></a>추가 구성
위의 정책에 더하여 최신 인증을 지원하지 않는 레거시 프로토콜을 잠그기도 해야 합니다.

### <a name="lock-down-legacy-protocols"></a>레거시 프로토콜 잠그기
조건부 액세스 정책은 Office 2016 및 지원되는 플랫폼 목록의 앱 등과 같은 최신 인증을 사용하여 브라우저 흐름 및 앱을 통한 액세스를 보호합니다. Office 2010 등의 이전 Office 데스크톱 응용 프로그램의 경우 조건부 액세스 정책이 적용되지 않습니다.

[OneDrive 관리 포털을 사용하여](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08) 최신 인증을 사용하지 않는 이전의 앱을 차단할 수 있습니다. SharePoint 관리 PowerShell cmdlet을 사용하여 SharePoint 레거시 프로토콜을 사용하지 않도록 설정할 수도 있습니다. PowerShell을 사용하려면 [Set-SPOTenant cmdlet](https://technet.microsoft.com/library/fp161390.aspx)을 실행하고 **-LegacyAuthProtocolsEnabled**를 **$false**로 설정합니다.  설정한 후 레거시 프로토콜 지원이 비활성화되고 이전 클라이언트 응용 프로그램을 사용하는 모든 SharePoint 액세스가 차단됩니다.

## <a name="next-steps"></a>다음 단계
[Microsoft 365 서비스에 대해 자세히 알아보기](index.md)
