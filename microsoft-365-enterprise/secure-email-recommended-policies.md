---
title: "보안 메일 권장 정책 - Microsoft 365 Enterprise | Microsoft Docs"
description: "메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: c86f8f86d134d77e45ab7a59564b9f0d4821ed38
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-email"></a>메일을 보호하기 위한 정책 권장 사항

이 문서에서는 최신 인증 및 조건부 액세스를 지원하는 조직의 메일 및 메일 클라이언트를 보호하는 데 도움이 되는 권장 정책을 설명합니다. [일반 ID 및 액세스 권장 사항](identity-access-policies.md)에 추가되는 내용입니다.

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
새 조건부 액세스 정책을 만들려면 

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. 아래 스크린샷에 표시된 대로 **새 정책**을 선택합니다.

![기준 CA 정책 만들기](./media/secure-email/CA-EXO-policy-1.png)

다음 테이블에서는 각 보호 수준에 요구되는 정책을 표현하는 데 필요한 적합한 설정을 설명합니다.

### <a name="medium-and-above-risk-requires-mfa"></a>중간 이상 위험의 경우 MFA 필요

다음 테이블에서는 이 정책에 맞게 구현하기 위한 조건부 액세스 정책 설정을 설명합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**할당**|사용자 및 그룹|포함|사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작합니다.|
|||제외|예외 보안 그룹; 서비스 계정(앱 ID)|필요에 따라 일시적으로 수정한 멤버 자격|
||클라우드 앱|포함|앱 선택 - Office 365 Exchange Online 선택||
||조건|구성됨|예|사용자 환경 및 요구에 맞게 구성|
||로그인 위험|위험 수준|높음, 중간|모두 선택|
|**액세스 제어**|권한 부여|액세스 허가|True|선택|
|||MFA 필요|True|Check|
|||호환 장치 필요|False||
|||도메인에 가입된 장치 필요|False||
|||선택된 컨트롤이 모두 필요함|True|선택|
|**정책 사용**|||켜짐|조건부 액세스 정책 배포|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요

Exchange Online에 대해 조건부 액세스 정책을 만들려면,

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다. 정상적으로 로그인되면 Azure 대시보드가 표시됩니다.

2. 왼쪽 메뉴에서 **Azure Active Directory**를 선택합니다.

3. **보안** 섹션 아래에서 **조건부 액세스**를 선택합니다.

4. **새 정책**을 선택합니다.

5. 정책 이름을 입력한 다음 정책을 적용할 **사용자 및 그룹**을 선택합니다.

6. **클라우드 앱**을 선택합니다.

7. **앱 선택**을 선택하고, **클라우드 앱** 목록에서 **Office 365 Exchange Online**을 선택하고 **선택**을 클릭합니다. **Office 365 Exchange Online** 앱을 선택한 후 **완료**를 클릭합니다.

8. **액세스 제어** 섹션에서 **권한 부여**를 선택합니다.

9. **액세스 권한 부여**를 선택하고 **준수 상태로 표시된 장치 필요** 및 **도메인 조인 필요(하이브리드 Azure AD)**를 둘 다 선택한 후 **선택**을 선택합니다.

10. **만들기**를 클릭하여 Exchange Online 조건부 액세스 정책을 만듭니다.

    > [!NOTE]
    > Azure의 Intune에서부터, Azure Active Directory 워크로드에서 모든 조건부 액세스 정책을 만들어야 합니다. Intune은 편의를 위해 포털에서 Azure AD 조건부 액세스 정책 워크로드에 대한 링크를 제공합니다.

    > [!IMPORTANT]
    > Intune 클래식 포털에서 이전에 만든 조건부 액세스 정책을 Azure Portal의 Intune으로 마이그레이션하는 데 도움이 필요한 경우 [Intune 클래식 포털에서 Azure Portal로 조건부 액세스 정책 다시 할당](https://docs.microsoft.com/intune/conditional-access-intune-reassign) 항목을 참조하세요. 

### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online에 대한 앱 기반 조건부 액세스

Azure Portal에서 Intune의 Exchange Online에 대한 앱 기반 조건부 액세스 정책을 설정하여 보안 계층을 하나 이상 추가할 수 있습니다. Exchange Online에 대한 앱 기반 조건부 액세스를 적용하는 경우 사용자가 회사 메일에 액세스하기 위해 특정 앱(예: Microsoft Outlook 앱)을 사용해야 합니다.

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
다음 테이블에서는 낮음 이상 위험 정책에 맞게 구현하기 위한 조건부 액세스 정책 설정을 설명합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**할당**|사용자 및 그룹|포함|사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작|
|||제외|예외 보안 그룹; 서비스 계정(앱 ID)|필요에 따라 일시적으로 수정한 멤버 자격|
||클라우드 앱|포함|앱 선택 - Office 365 Exchange Online 선택||
||조건|구성됨|예|사용자 환경 및 요구에 맞게 구성|
||로그인 위험|구성됨|예|사용자 환경 및 요구에 맞게 구성|
|||위험 수준|낮음, 중간, 높음|세 항목 모두 선택|
|**액세스 제어**|권한 부여|액세스 허가|True|선택|
|||MFA 필요|True|Check|
|||호환 장치 필요|False||
|||도메인에 가입된 장치 필요|False||
|||선택된 컨트롤이 모두 필요함|True|선택|
|**정책 사용**|||켜짐|조건부 액세스 정책 배포|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요
(기준 지침 참조)

### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online에 대한 앱 기반 조건부 액세스

(기준 지침 참조)

#### <a name="apply-to"></a>적용 대상

파일럿 프로젝트가 완료된 후 중요하다고 생각하는 메일에 대한 액세스 권한을 요구하는 조직의 사용자에게 이 정책을 적용해야 합니다.

## <a name="highly-regulated"></a>높은 규제
### <a name="mfa-required"></a>MFA 필요

다음 테이블에서는 높은 규제를 받는 정책에 맞게 구현하기 위한 조건부 액세스 정책 설정을 설명합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**할당**|사용자 및 그룹|포함|사용자 및 그룹 선택 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작|
|||제외|예외 보안 그룹; 서비스 계정(앱 ID)|필요에 따라 일시적으로 수정한 멤버 자격|
||클라우드 앱|포함|앱 선택 - Office 365 Exchange Online 선택||
|**액세스 제어**|권한 부여|액세스 허가|True|선택|
|||MFA 필요|True|Check|
|||호환 장치 필요|False|Check|
|||도메인에 가입된 장치 필요|False||
|||선택된 컨트롤이 모두 필요함|True|선택|
|**정책 사용**|||켜짐|조건부 액세스 정책 배포|

### <a name="require-a-compliant-or-domain-joined-device"></a>호환되거나 도메인에 가입된 장치 필요
(기준 지침 참조)
### <a name="app-based-conditional-access-for-exchange-online"></a>Exchange Online에 대한 앱 기반 조건부 액세스
(기준 지침 참조)
#### <a name="apply-to"></a>적용 대상
파일럿 프로젝트가 완료된 후 높은 규제를 받는다고 생각하는 메일에 대한 액세스 권한을 요구하는 조직의 사용자에게 이 정책을 적용해야 합니다.

### <a name="high-risk-users-policy"></a>높은 위험 사용자 정책
계정이 손상된 모든 높은 위험 사용자가 로그인할 때 암호 변경을 수행하게 하려면 다음 정책을 적용해야 합니다.

사용자의 관리자 자격 증명을 사용하여 [Microsoft Azure Portal(http://portal.azure.com)](http://portal.azure.com/)에 로그인한 다음 **Azure AD ID 보호 > 사용자 위험 정책**으로 이동합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**할당**|사용자|포함|모든 사용자|선택|
|||제외|없음||
||조건|사용자 위험|높은|선택|
|**컨트롤**|액세스|액세스 허용|True|선택|
||액세스|암호 변경 필요|True|Check|
|**검토**|해당 없음|해당 없음|해당 없음|해당 없음|
|**정책 강제 적용**|||켜짐|정책 강제 적용 시작|


## <a name="additional-configurations"></a>추가 구성
위의 정책 외에도 이 섹션에서 설명한 다음 모바일 응용 프로그램 및 장치 관리 설정을 구성해야 합니다.

### <a name="intune-mobile-application-management"></a>Intune 모바일 응용 프로그램 관리

각 보안 및 데이터 보호 계층에 대해 앞서 언급한 정책 권장 사항에 의해 메일이 보호되도록 하려면 Azure Portal 내에서 Intune 앱 보호 정책을 만들어야 합니다.

새 앱 보호 정책을 만들려면 사용자의 관리자 자격 증명을 사용하여 Microsoft Azure Portal에 로그인한 다음 **Intune 앱 보호 > 앱 정책**으로 이동합니다.

다음 스크린 샷과 같이 새 정책을 추가합니다(+추가).

![Intune 모바일 응용 프로그램 관리](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>iOS와 Android 간에 앱 보호 정책 옵션에 약간의 차이가 있습니다. 아래 정책은 명시적으로 Android용입니다.
>

다음 테이블에서는 권장되는 Intune 앱 보호 정책 설정을 설명합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**일반**|메일|이름|Android에 대한 보안 메일 정책|정책 이름 입력|
|||설명||정책을 설명하는 텍스트 입력|
|||플랫폼|Android|iOS와 Android 간에 앱 보호 정책 옵션에 약간의 차이가 있음; 이 정책은 명시적으로 Android용임|
|**앱**|응용 프로그램|앱|Outlook|선택됨(목록)|
|**설정**|데이터 재배치|Android 백업 차단|예|iOS의 경우 iTunes 및 iCloud를 명시적으로 호출|
||||앱이 다른 앱으로 데이터를 전송하도록 허용|정책 관리 앱||
|||앱에서 다른 앱의 데이터를 받을 수 있도록 허용|정책 관리 앱||
|||"다른 이름으로 저장" 차단|예||
|||다른 앱에서 잘라내기, 복사 및 붙여넣기 제한|정책 관리 앱||
|||Managed Browser에서 표시할 수 있는 웹 콘텐츠 제한|아니요||
|||앱 데이터 암호화|예|iOS의 경우 옵션 선택: 장치가 잠긴 경우|
|||연락처 동기화 사용 안 함|아니요||
||액세스|액세스 시 PIN 필요|예||
|||PIN 다시 설정까지의 입력 시도 횟수|3||
|||단순한 PIN 허용|아니요||
|||PIN 길이|6||
|||PIN 대신 지문 허용|예||
|||액세스 시 회사 자격 증명 필요|아니요||
|||관리되는 앱이 무단 해제 또는 루팅된 장치를 실행하지 못하도록 차단|예||
|||액세스 요구 사항을 다시 확인할 시간(분)|30||
|||오프라인 유예 기간|720||
|||앱 데이터가 초기화되기 전의 오프라인 간격(일)|90||
|||화면 캡처 및 Android Assistant 차단|아니요|iOS의 경우 이 옵션을 사용할 수 없음|

완료되면 반드시 “만들기"를 클릭하십시오. 위 단계를 반복하고 선택한 플랫폼(드롭다운)을 iOS로 바꿉니다. 그러면 앱 정책 두 개가 생성되므로 정책을 만든 다음 정책에 그룹을 할당하고 배포합니다.

- 자세한 내용은 [앱 보호 정책을 만들고 할당하는 방법](https://docs.microsoft.com/intune/app-protection-policies)을 참조하세요.

### <a name="intune-mobile-device-management"></a>Intune 모바일 장치 관리
Intune 자격 증명으로 [Azure Portal의 Intune](https://portal.azure.com)에 로그인하여 다음 장치 구성 프로필 및 장치 정책 준수를 만듭니다.

#### <a name="ios-email-profile"></a>iOS 메일 프로필
[Azure Portal의 Intune](https://portal.azure.com)의 **[장치 구성] > [프로필] > [프로필 만들기] > [플랫폼(iOS)] > [프로필 유형(이메일)]**에서 다음 장치 구성 프로필을 만들 수 있습니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**전자 메일 프로필**|Exchange Active Sync|호스트(#)|Outlook.office365.com||
|||계정 이름(#)|SecureEmailAccount|Admini 선택|
|||Username|사용자 계정 이름|선택됨 - 드롭다운|
|||전자 메일 주소|기본 SMTP 주소|선택됨 - 드롭다운|
|||인증 방법|사용자 이름 및 암호|선택됨 - 드롭다운|
|||S/MIME 사용|False||
||동기화 설정|동기화할 전자 메일의 일 수|2주|선택됨 - 드롭다운|
|||SSL 사용|True|Check|
|||메시지를 다른 전자 메일 계정으로 이동하도록 허용|False||
|||타사 응용 프로그램에서 메일을 전송할 수 있음|True||
|||최근에 사용한 전자 메일 주소를 동기화합니다.|True|Check|

#### <a name="android-email-profile"></a>Android 메일 프로필
[Azure Portal의 Intune](https://portal.azure.com)의 **[장치 구성] > [프로필] > [프로필 만들기] > [플랫폼(Android)] > [프로필 유형(이메일)]**에서 다음 장치 구성 프로필을 만들 수 있습니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**전자 메일 프로필**|Exchange Active Sync|호스트(#)| Outlook.office365.com|
|||계정 이름(#)|SecureEmailAccount|Admini 선택|
|||Username|사용자 계정 이름|선택됨 - 드롭다운|
|||전자 메일 주소|기본 SMTP 주소|선택됨 - 드롭다운|
|||인증 방법|사용자 이름 및 암호|선택됨 - 드롭다운|
|||S/MIME 사용|False||
||동기화 설정|동기화할 전자 메일의 일 수|2주|선택됨 - 드롭다운|
|||동기화 일정|구성되지 않음|선택됨 - 드롭다운|
|||SSL 사용|True|Check|
|||동기화할 콘텐츠 형식|||
|||메일|True|확인(잠김)|
|||연락처|True|Check|
|||일정|True|Check|
|||태스크|True|Check|
|||참고|True|Check|

#### <a name="android-for-work-email-profile"></a>Android for Work 메일 프로필
[Azure Portal의 Intune](https://portal.azure.com)의 **[장치 구성] > [프로필] > [프로필 만들기] > [플랫폼(Android for Work)] > [프로필 유형(이메일)]**에서 다음 장치 구성 프로필을 만들 수 있습니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**전자 메일 프로필**|Exchange Active Sync|호스트(#)| Outlook.office365.com|
|||계정 이름(#)|SecureEmailAccount|Admini 선택|
|||Username|사용자 계정 이름|선택됨 - 드롭다운|
|||전자 메일 주소|기본 SMTP 주소|선택됨 - 드롭다운|
|||인증 방법|사용자 이름 및 암호|선택됨 - 드롭다운|
||동기화 설정|동기화할 전자 메일의 일 수|2주|선택됨 - 드롭다운|
|||SSL 사용|True|Check|

#### <a name="device-compliance-policy"></a>장치 준수 정책
[Azure Portal의 Intune](https://portal.azure.com)의 **[장치 정책 준수] > [정책] > [정책 만들기] > [플랫폼(iOS, Android 또는 기타)] > [설정]**에서 다음 장치 정책 준수를 만들 수 있습니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**시스템 보안**|암호|모바일 장치의 잠금을 해제하는 데 암호 필요(...)|예|선택됨 - 드롭다운|
|||단순 암호 허용(...)|아니요|선택됨 - 드롭다운|
|||최소 암호 길이(...)|6|선택됨 - 목록|
||고급 암호 설정|모두|구성되지 않음||
||암호화|모바일 장치 암호화 필요(...)|예|선택됨 - 드롭다운|
||전자 메일 프로필|Intune에서 메일 계정을 관리해야 함(iOS 8.0 이상)|예| 선택됨 - 드롭다운|
|||선택(#)||iOS의 경우 메일 구성 정책을 선택해야 함: iOS 메일 정책(위의 구성 정책 참조)|
|**장치 상태**|Windows 장치 상태 증명|장치가 정상으로 보고되어야 함(Windows 10 Desktop 및 Mobile 이상)|예||
||장치 보안 설정|모두|구성되지 않음||
||장치 위협 방지|모두|구성되지 않음||
||탈옥|장치는 무단 해제 또는 루팅되지 않아야 함(iOS 8.0 이상, Android 4.0 이상)|예||
|**장치 속성**|운영 체제 버전|모두|구성되지 않음|||

위의 모든 정책을 배포하는 것으로 간주하려면 사용자 그룹에서 이들을 대상으로 설정해야 합니다. 정책을 만들거나(저장 시) 나중에 정책 섹션에서 배포 관리를 선택하여 이 작업을 수행할 수 있습니다(추가와 같은 수준).

## <a name="remediating-medium-or-high-risk-access-events"></a>중간 또는 높음 위험 액세스 이벤트 해결
사용자가 이전에는 필요하지 않았던 MFA를 수행할 것으로 예상된다고 보고하는 경우 지원 부서가 위험 관점에서 그 상태를 검토할 수 있습니다.  

전역 관리자 또는 보안 관리자 역할을 가진 조직 내의 사용자는 Azure AD ID 보호를 사용하여 계산된 위험 점수에 기여한 위험한 이벤트를 검토할 수 있습니다. 의심스러운 것으로 표시된 일부 이벤트를 식별했지만 유효한 것으로 확인된 경우(직원이 휴가 중일 때 생소한 장소에서 로그인하는 경우 등) 관리자는 해당 이벤트가 더 이상 위험 점수에 기여하지 않도록 이벤트를 확인할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[SharePoint 사이트 및 파일을 보호하기 위한 정책 권장 사항 알아보기](sharepoint-file-access-policies.md)
