---
title: "보안 메일 권장 정책 - Microsoft 365 Enterprise | Microsoft Docs"
description: "메일 정책과 구성을 적용하는 방법에 관한 Microsoft 권장 정책을 설명합니다."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: b2650e0c792c32cb4bc43556be9efc30ed9609e3
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="policy-recommendations-for-securing-email"></a>메일을 보호하기 위한 정책 권장 사항

이 문서에서는 최신 인증 및 조건부 액세스를 지원하는 조직의 메일 및 메일 클라이언트를 보호하는 데 도움이 되는 권장 정책을 설명합니다. [일반 ID 및 액세스 권장 사항](identity-access-policies.md)에 추가되는 내용입니다.

다음 권장 사항은 요구의 세분성에 따라 적용할 수 있는 세 가지 메일 보안 및 보호 계층 **기준**, **중요** 및 **높은 규제**를 기준으로 합니다. [권장되는 보안 정책 및 구성 소개](microsoft-365-policies-configurations.md)에서 이러한 권장 사항을 참조하여 이러한 보안 계층, 권장되는 클라이언트 운영 체제에 대해 더 자세히 알아볼 수 있습니다.

>[!NOTE]
>이러한 권장 사항의 일부로 만드는 모든 보안 그룹은 Office 기능을 사용하도록 설정한 상태에서 만들어야 합니다. 이 지침은 SharePoint에서 문서를 보호할 때 AIP 배포를 위해 특히 중요합니다.
>
>![보안 그룹에 대해 활성화되는 Office 기능](./media/security-group.png)
>

## <a name="baseline"></a>기준
새 조건부 액세스 정책을 만들려면 관리자 자격 증명을 사용하여 Microsoft Azure Portal에 로그인합니다. 그런 다음 **Azure Active Directory > 보안 > 조건부 액세스**로 이동합니다.

다음 스크린 샷과 같이 새 정책을 추가할 수 있습니다(+추가).

![기준 CA 정책 만들기](./media/secure-email/baseline-ca-policy.png)

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

Exchange Online용 새 Intune 조건부액세스 정책을 만들려면 사용자의 관리자 자격 증명을 사용하여 [Microsoft 관리 포털(http://manage.microsoft.com)](http://manage.microsoft.com/)에 로그인한 다음 **정책 > 조건부 액세스 > Exchange Online 정책**으로 이동합니다.

![Exchange Online 정책](./media/secure-email/exchange-online-policy.png)

호환되거나 도메인에 가입된 장치를 요구하려면 Intune 관리 포털에서 Exchange Online에 대해 명시적으로 조건부 액세스 정책을 설정해야 합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**응용 프로그램 액세스**|Outlook 및 최신 인증을 사용하는 기타 앱|모든 플랫폼|True|선택|
|||Windows는 다음 요구 사항을 충족해야 함|장치가 도메인에 가입되어 있거나 호환되어야 함|선택됨(목록)|
|||선택한 플랫폼|False||
||Outlook Web Access(OWA)|Outlook과 동일한 플랫폼에서 호환되지 않는 장치 차단|True|Check|
||기본 인증을 사용하는 Exchange ActiveSync 앱|Microsoft Intune에서 지원하는 플랫폼에서 비규격 장치 차단|True|Check|
|||Microsoft Intune에서 지원하지 않는 플랫폼에서 다른 모든 장치 차단|True|Check|
|**정책 배포**|대상 그룹|이 정책의 대상으로 지정할 Active Directory 그룹 선택|||
|||모든 사용자|False||
|||선택된 보안 그룹|True|선택|
|||수정|대상 사용자를 포함하는 특정 보안 그룹 선택||
||제외 그룹|이 정책에서 제외할 Active Directory 그룹 선택(대상이 지정된 그룹 목록의 구성원 재정의)|||
|||제외 사용자 없음|True|선택|
|||선택된 보안 그룹|False|||

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Exchange Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스

모바일 앱을 관리하려면 Intune 관리 포털에서 Exchange Online에 대해 명시적으로 조건부 액세스 정책을 설정해야 합니다.

모바일 앱을 관리하려면 사용자의 관리자 자격 증명을 사용하여 Microsoft Azure Portal에 로그인한 다음 **Intune 앱 보호 > 설정 > 조건부 액세스 > Exchange Online**으로 이동합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**앱 액세스**|허용되는 앱|앱 액세스 사용|Intune 앱 정책을 지원하는 앱 허용|선택됨(목록) – Intune 앱 정책에서 지원하는 앱/플랫폼 조합의 목록 표시|
|**사용자 액세스**|허용되는 앱|제한된 사용자 그룹|사용자 그룹 추가 – 대상 사용자를 포함하는 특정 보안 그룹 선택|파일럿 사용자를 포함한 보안 그룹으로 시작|
|||예외 사용자 그룹|예외 보안 그룹|||

#### <a name="apply-to"></a>적용 대상

파일럿 프로젝트가 완료된 후 이 정책을 조직의 모든 사용자에게 적용해야 합니다.

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

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Exchange Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스

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
### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Exchange Online에 대한 모바일 응용 프로그램 관리용 조건부 액세스
(기준 지침 참조)
#### <a name="apply-to"></a>적용 대상
파일럿 프로젝트가 완료된 후 높은 규제를 받는다고 생각하는 메일에 대한 액세스 권한을 요구하는 조직의 사용자에게 이 정책을 적용해야 합니다.

### <a name="high-risk-users-policy"></a>높은 위험 사용자 정책
계정이 손상된 모든 높은 위험 사용자가 로그인할 때 암호 변경을 수행하게 하려면 다음 정책을 적용해야 합니다.

사용자의 관리자 자격 증명을 사용하여 [Microsoft Azure Portal(http://portal.azure.com)](http://portal.azure.com/)에 로그인한 다음 **Azure AD ID 보호 > 사용자 위험 정책**으로 이동합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**할당**|Users|포함|모든 사용자|선택|
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

![Intune 모바일 응용 프로그램 관리](./media/secure-email/intune-mobile-app-mgmt.png)

>[!NOTE]
>iOS와 Android 간에 앱 보호 정책 옵션에 약간의 차이가 있습니다. 아래 정책은 명시적으로 Android용입니다.
>

다음 테이블에서는 권장되는 Intune 앱 보호 정책 설정을 설명합니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**일반**|메일|Name|Android에 대한 보안 메일 정책|정책 이름 입력|
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

### <a name="intune-mobile-device-management"></a>Intune 모바일 장치 관리
사용자의 관리자 자격 증명을 사용하여 [Microsoft 관리 포털(http://manage.microsoft.com)](https://manage.microsoft.com/)에 로그인하여 다음 구성 및 준수 정책을 만듭니다.

#### <a name="ios-email-profile"></a>iOS 메일 프로필
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 구성 정책 > 추가 > iOS 메일 정책**에서 다음 구성 정책을 만듭니다.

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

#### <a name="ios-app-sharing-profile"></a>iOS 앱 공유 프로필
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 구성 정책 > 추가 > iOS 앱 공유 정책**에서 다음 구성 정책을 만듭니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**Security**|모두|모두|구성되지 않음||
|**클라우드**|모두|모두|구성되지 않음||
|**응용 프로그램**|브라우저|모두|구성되지 않음||
||앱|앱 설치 허용|구성되지 않음||
|||앱 스토어에 액세스하려면 암호 필요|구성되지 않음||
|||앱에서 모두 바로 구매|구성되지 않음||
|||다른 관리되는 앱에서 관리되는 문서 허용(iOS 8.0 이상)|아니요|선택됨 - 드롭다운|
|||다른 관리되는 앱에서 관리되지 않는 문서 허용|구성되지 않음||
|||비디오 회의 허용|구성되지 않음||
|||사용자가 새로운 엔터프라이즈 앱 작성자를 신뢰하도록 허용|구성되지 않음||
||게임|모두|구성되지 않음||
||미디어 콘텐츠|모두|구성되지 않음|||

#### <a name="android-email-profile"></a>Android 메일 프로필
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 구성 정책 > 추가 > Android 메일 정책**에서 다음 구성 정책을 만듭니다.

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
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 정책 구성 > 추가 > Android > 메일 프로필(Android for Work - Gmail)**에서 다음 구성 정책을 만듭니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**전자 메일 프로필**|Exchange Active Sync|호스트(#)| Outlook.office365.com|
|||계정 이름(#)|SecureEmailAccount|Admini 선택|
|||Username|사용자 계정 이름|선택됨 - 드롭다운|
|||전자 메일 주소|기본 SMTP 주소|선택됨 - 드롭다운|
|||인증 방법|사용자 이름 및 암호|선택됨 - 드롭다운|
||동기화 설정|동기화할 전자 메일의 일 수|2주|선택됨 - 드롭다운|
|||SSL 사용|True|Check|

#### <a name="android-for-work-app-sharing-profile"></a>Android for Work 앱 공유 프로필
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 구성 정책 > 추가 > Android for Work 앱 공유 정책**에서 다음 구성 정책을 만듭니다.

|Categories|유형|속성|값|참고|
|:---------|:---|:---------|:-----|:----|
|**Security**|암호|최소 암호 길이|구성되지 않음||
|||업무용 프로필을 삭제하기 전까지 허용되는 로그인 반복 오류 횟수|구성되지 않음||
|||장치가 잠기기 전까지 비활성 상태인 시간(분)|구성되지 않음||
|||암호 만료(일)|구성되지 않음||
|||암호 기록 기억|구성되지 않음||
|||모바일 장치의 잠금을 해제하는 데 암호 필요|구성되지 않음||
|||지문 잠금 해제 허용(Android 6.0 이상)|구성되지 않음||
|||Smart Lock 및 기타 신뢰 에이전트 허용(Android 6.0 이상)|구성되지 않음||
||업무용 프로필 설정|회사와 개인 프로필 간의 데이터 공유 허용|업무용 프로필의 앱에서 개인 프로필의 공유 요청을 처리할 수 있음|선택됨 - 드롭다운|
|||장치가 잠겼을 때 회사 프로필 알림 숨김(Android 6.0 이상)|구성되지 않음||
|||기본 앱 사용 권한 정책 설정(Android 6.0 이상)|구성되지 않음|||

#### <a name="device-compliance-policy"></a>장치 준수 정책
[Intune 관리 포털(https://manage.microsoft.com)](https://manage.microsoft.com/)의 **정책 > 준수 정책 > 추가**에서 다음 구성 정책을 만듭니다.

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
