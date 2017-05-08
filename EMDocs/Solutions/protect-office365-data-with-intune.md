---
title: "Office 365 회사 데이터 보호 | Microsoft 문서"
description: "EMS와 Office 365는 사용자에게 뛰어난 생산성 표준을 제공하고 IT 직원에게 긴밀히 통합된 데이터 제어 기능을 제공하는 완전 관리형 모바일 생산성 솔루션을 제공합니다."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 1/23/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cc0d2e1f-9c34-4dcb-ac1f-2f355e9ebb7e
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: d7e15962a95135dbb16cb41e2643c602b87039cf
ms.contentlocale: ko-kr
ms.lasthandoff: 01/24/2017


---

# <a name="protect-office-365-company-data-with-intune"></a>Intune을 사용하여 Office 365 회사 데이터 보호
대부분 직원들이 모바일 장치에서 원하는 첫 번째 기능은 회사 메일 및 문서에 대한 액세스입니다. 또한 복잡한 단계를 거치거나 지원 센터에 문의하지 않고 설정을 진행할 수 있기 바랍니다. 반면, IT 부서는 골치 아프게 대규모의 온-프레미스 인프라를 유지 관리하지 않으면서 모든 위치에서 회사 데이터 보안을 유지하려고 합니다. EMS(Enterprise Mobility + Security)를 사용하면 직원들이 즐겨 사용하는 앱 및 장치로 직원 생산성을 유지할 수 있고 회사 데이터를 보호할 수 있습니다. 방법에 대해 계속 읽어보세요.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>EMS(Enterprise Mobility + Security)는 사용자에게 어떻게 도움을 줄 수 있나요?
EMS는 기본적으로 모든 사용자가 회사로 가져온 장치에서 Microsoft Office 메일, 파일 및 앱을 보호하도록 고안된 유일한 솔루션입니다. 내부에서 EMS는 ID, 장치, 앱 및 데이터를 아우르는 4계층의 보호를 제공함으로써 이동 중인 직원들에게 안전한 메일을 쉽게 전달할 수 있도록 합니다. EMS를 통해 직원들은 회사 메일 및 문서에 안전하고 원활하게 액세스할 수 있으며, Outlook, Word, Excel, PowerPoint 및 OneDrive와 같은 Office 모바일 앱을 통해 친숙한 메일 및 생산성 환경을 활용할 수 있습니다.

Office 365는 사용자 환경을 그대로 유지하면서 어디로 이동하든 해당 위치에서 작업을 수행하려는 직원을 위해 고안되었습니다. EMS와 Office 365는 사용자에게 뛰어난 생산성 표준을 제공하고 IT 직원에게 긴밀히 통합된 데이터 제어 기능을 제공하는 완전 관리형 모바일 생산성 솔루션을 제공합니다.

### <a name="recommended-solution"></a>권장 솔루션
Intune을 사용하여 회사 정보를 안전하게 유지하면서 직원들이 거의 어디에서 어떤 장치를 사용하든 회사 응용 프로그램, 데이터 및 리소스에 쉽게 액세스할 수 있도록 합니다. Intune은 작업을 보다 쉽게 진행하도록 지원하는 것 외에도 기존의 온-프레미스 솔루션보다 더 현대적이고 비용 효과적인 방법으로 회사 데이터를 보호할 수 있도록 합니다. Intune으로 Office 365 데이터를 보호할 경우 온-프레미스 인프라를 설치하고 유지 관리하거나 회사 방화벽을 열어 트래픽이 이동되도록 할 필요가 없습니다.

아래의 짧은 동영상을 통해 Intune 및 Office 365가 연동되어 직원이 iOS, Android, Windows 장치에서 안전하게 회사 데이터에 액세스할 수 있는 원활한 환경을 제공하는 방법을 확인하세요.

<iframe width="675" height="480" src="https://www.youtube.com/embed/To9zfl6-Z6Y" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
이 솔루션의 나머지 부분은 Intune으로 Office 365 회사 데이터를 보호하는 방법을 보여 주는 다음과 같은 섹션으로 구분됩니다.
- **모바일 장치 및 Windows PC를 관리 기능에 등록**. 이 섹션에서는 장치(iOS, Android, Android for Work 및 Windows PC)에 정책을 배포하여 Office 365 회사 데이터를 보호하도록 장치를 Intune의 관리 기능에 등록하는 방법을 설명합니다.
- **Office 365 서비스에 대한 보안 액세스** 이 섹션에서는 Intune 준수 정책과 Exchange Online 및 SharePoint Online Office 365 서비스에 대한 조건부 액세스를 관리하는 방법을 알아봅니다.
- **회사 데이터 보호** 이 섹션에서는 iOS 및 Android 장치에 대해 앱 보호를 사용하는 방법을 설명하고 Intune에서 장치로 관리되는 Windows 10 PC에서 WIP(Windows Information Protection) 정책을 활용하여 회사 앱 데이터를 보호하는 방법도 설명합니다.
- **선택적으로 회사 데이터 초기화** 이 섹션에서는 장치가 업무에 더 이상 필요하지 않거나 도난 또는 분실된 경우 장치에서 회사 앱 및 데이터를 제거하는 방법을 알아봅니다.


## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>모바일 장치 및 Windows PC를 관리 기능에 등록
Intune의 관리 기능에 장치 및 PC를 등록하면 관리되는 장치에 대해 구성한 모든 정책 및 액세스 프로필이 적용됩니다. 장치를 등록하기 전에 먼저 사용자에게 라이선스를 할당하고 모바일 장치 관리 권한을 설정하여 [Intune 서비스를 준비](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)하고, 사용자가 관리하려는 여러 다양한 장치 유형에 대한 다양한 등록 요구 사항을 충족해야 합니다. 작업을 시작한 후에도 사용자에게 신뢰할 수 있는 등록 및 지원 환경을 제공할 수 있도록 지원 정보 빛 회사별 브랜딩을 사용하여 [회사 포털을 사용자 지정](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal)해야 합니다.

Intune 서비스를 준비한 후 관리 기능에 장치를 등록하는 프로세스는 상당히 간단하지만 장치 종류별로 약간 다를 수 있습니다.
- **iOS 및 Mac 장치**. iPad, iPhone 또는 Mac OS X 장치를 등록하려면 APNs(Apple Push Notification service) 인증서를 구해야 합니다. [Intune에 APNs 인증서를 업로드](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)한 후에는 회사 포털 앱을 사용하여[iOS 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios)하고 회사 포털 웹 사이트를 사용하여 [Mac OS X 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x)할 수 있습니다.
- **Android 장치**. Android 장치를 등록하기 위해 Intune 서비스를 준비하는 데 필요한 작업은 없습니다. 사용자는 Google Play에서 제공되는 회사 포털 앱을 사용하여 관리 기능에 [Android 장치를 등록](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune)하기만 하면 됩니다.
-   **Android for Work**. 회사 프로필을 Intune에서 관리할 수 있는 Android 5.0 Lollipop 이상 장치에 대해 [Android for Work를 설정](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)하려면 조직에서 Google을 통해 Android for Work에 등록한 다음 Intune 관리 콘솔의 ADMIN 노드에서 Android for Work 설정을 구성해야 합니다.
- **Windows Phone 및 PC**. [등록 서버에 대해 DNS 별칭을 설정](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)하여 Windows 장치를 보다 쉽게 등록할 수 있습니다. 그렇지 않으면 회사 또는 학교 계정을 추가하여 [Windows 장치를 등록](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows)할 수 있습니다.

> [!TIP]
> Azure AD(Premium)에서 [자동 등록을 사용하도록 설정](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)면 사용자가 Windows 장치를 더 쉽게 등록할 수 있습니다. 이렇게 하는 경우 사용자가 회사 또는 학교 계정을 추가하여 개인 장치를 등록하거나 회사 소유 장치가 조직의 Azure AD에 연결할 때 장치가 Intune의 관리 기능에 자동으로 등록됩니다.

## <a name="secure-access-to-office-365-services"></a>Office 365 서비스에 대한 보안 액세스
사용자는 Office 365 모바일 앱을 사용하는 경우 모든 회사 메일 및 파일에 액세스할 수 있을 것이라고 예상하지만, 신뢰할 수 있는 장치만 회사 리소스에 연결되도록 해야 합니다. 이 작업을 수행하려면 Intune 조건부 액세스 정책을 사용하여 직원이 관리되는 정책 호환 장치에서만 Office 365 클라우드 서비스에 액세스하도록 할 수 있습니다.

조건부 액세스 정책이 제대로 작동하려면 먼저 [Intune 장치 준수 정책](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)을 정의해야 합니다. 이러한 종류의 Intune 정책은 처음 등록될 때와 그 이후에 주기적으로 장치를 검사하여 장치 설정이 원하는 대로 구성되어 있는지 확인합니다. 따라서 보안 요구 사항을 충족하는 장치만 회사 리소스에 액세스하도록 쉽게 관리할 수 있습니다. Intune 장치 준수 정책을 만들고 사용자에게 배포하여 장치의 규정 준수 요건을 직접 정의할 수 있습니다(예: 암호를 통해 잠금을 해제하도록 요구, 단순 암호 허용 또는 거부, 최소 암호 길이 지정, 무단 해제 사용 안 함).

> [!IMPORTANT]
> 규정 준수 유효성을 검사하기 위한 준수 정책이 없으면 조건부 액세스 정책이 작동되지 않습니다.

[조건부 액세스 정책](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)을 사용하여 Dynamics CRM Online<sup>1</sup>, Exchange Online<sup>2</sup>, SharePoint Online<sup>2</sup> 및 비즈니스용 Skype Online<sup>1</sup>과 같은 Office 365 서비스에 대한 액세스를 보호할 수 있습니다. 다음 예제에서는 Exchange Online 및 SharePoint Online에 대해 조건부 액세스 정책이 구성됩니다.  

> <sup>1</sup> iOS 및 Android에만 해당

> <sup>2</sup> iOS, Android 및 Windows 장치

### <a name="secure-access-to-exchange-online"></a>Exchange Online에 대한 액세스 보호
Intune을 사용하면 사용자가 설정한 조건부 액세스 및 규정 준수 정책에 따라 회사의 Exchange Online 메일이 보호됩니다. 예를 들어 [Exchange Online 메일에 대한 액세스](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)를 강력한 암호를 사용하지 않고, 무단 해제되지 않고, 암호화되지 않는 장치로 제한할 수 있습니다.

Exchange Online으로 이동되도록 조건부 액세스 정책을 구성한 경우, 사용자가 Intune을 통해 관리되지 않는 장치를 사용하여 메일을 확인하려고 할 때 발생하는 현상은 다음과 같습니다.
1. 사용자는 관리되지 않는 Android 장치에서 기본 메일 앱을 사용하여 Exchange Online 회사 메일을 읽으려고 합니다. 장치는 Intune에 의해 관리되지 않아 규정 준수 정책을 준수하지 않으므로 메일에 대한 액세스가 거부됩니다.
2. 사용자에게 표시되는 유일한 메일은 사용자의 장치가 회사 정책을 준수하지 않으므로 메일에 액세스하기 위해 먼저 등록해야 한다고 설명하는 Intune 서비스 메일입니다.
3. 장치가 등록되고 회사 정책을 준수하는 것으로 확인되면 회사 메일에 대한 모든 액세스 권한이 복원됩니다.

![Exchange Online에서 조건부 액세스가 작동하는 방식을 보여 주는 이미지](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig1.png)

### <a name="secure-access-to-sharepoint-online"></a>SharePoint Online에 대한 액세스 보호
Intune에서는 조건부 액세스를 사용하여 [SharePoint Online 파일 액세스에 대해 보안을 유지](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)할 수 있습니다. 메일에 대한 액세스를 보호하는 것처럼, 액세스 허용을 위해 충족해야 하는 2가지 정책을 설정해야 합니다. 하나는 장치에서 회사 정책이 준수되도록 하는 장치 준수 정책이고, 다른 하나는 서비스 액세스를 위해 충족해야 하는 조건을 설정하는 조건부 액세스 정책입니다.

사용자가 관리되지 않는 장치를 사용하여 Intune 조건부 액세스 정책에 의해 보호되는 SharePoint Online 서비스에 연결하려고 하면 다음 현상이 발생합니다.
1.  사용자의 SharePoint Online 리소스 액세스가 거부되고, 대신 보안을 강화하라는 메시지와 Intune 관리에 장치를 등록하기 위한 링크가 표시됩니다.
2.  사용자가 액세스 거부 메시지에서 제공된 링크를 따라 장치를 등록합니다.
3.  장치가 등록되고 회사 정책을 준수하는 것으로 확인되면 회사 SharePoint Online 데이터에 대한 모든 액세스 권한이 복원됩니다.

![SharePoint Online에서 조건부 액세스가 작동하는 방식을 보여 주는 이미지](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig2.png)

## <a name="protect-company-data"></a>회사 데이터 보호
아시다시피 대부분의 직원은 개인 및 업무 둘 다의 용도로 모바일 장치를 사용하고 있습니다. 특히 현재, 소유 장치가 업무에 점점 더 많이 사용되면서 증가하면서 메일, 소셜 미디어 및 공용 클라우드처럼 기업의 관리 영역을 벗어나는 앱 및 서비스를 통해 실수로 데이터가 유출될 위험이 높아지고 있습니다. 예를 들어 직원이 자신의 개인 메일 계정에서 최신 엔지니어링 사진을 전송하거나, 제품 정보를 복사한 후 트윗에 붙여넣거나, 진행 중인 판매 보고서를 해당 공용 클라우드 저장소에 저장하는 경우가 있습니다. 따라서 직원 생산성을 유지하면서 의도적이거나 의도치 않은 회사 데이터 누출을 방지하기 위해 가능한 조치를 취해야 하는 어려움이 있습니다.

조건부 액세스 정책을 사용하면 규정을 준수하는 장치 및 사용자만 메일에 액세스하도록 할 수 있지만, 첨부된 파일과 메일 자체를 보호할 수 있는가의 문제는 여전히 남아 있습니다. 콘텐츠를 다른 위치로 복사, 이동, 저장하지 못하게 하거나 다른 사용자와 공유하지 못하게 하려면 어떻게 해야 할까요? Intune은 iOS 및 Android 장치에 MAM(모바일 응용 프로그램 관리) 정책을 사용하고, Windows 10 PC 및 모바일 장치에 WIP(Windows Information Protection)를 사용하여 이 문제를 해결합니다.  

### <a name="mam-for-managed-ios-and-android-mobile-devices"></a>관리되는 iOS 및 Android 모바일 장치에 대한 MAM
Intune MAM(모바일 앱 관리) 정책을 사용하여 사용자의 iOS 및 Android 장치를 통해 액세스되는 회사 데이터를 보호할 수 있습니다. 이러한 앱 수준 정책을 구현하여 직원이 회사 데이터를 사용하고 공유하는 방식을 제어할 수 있습니다.

> [!TIP]
> Intune MAM 정책은 사용자에게 Intune 라이선스가 할당되어 있다면 MDM(모바일 장치 관리) 솔루션과는 별도로 사용할 수 있습니다. 즉, 장치를 Intune 관리에 등록하든 하지 않든, Microsoft 이외의 MDM 서비스로 장치를 관리하든, 회사 데이터를 보호할 수 있습니다.

관리자는 [Azure 관리 포털에서 Intune MAM 앱 정책 설정을 구성](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)합니다. MAM 정책에 포함된 2가지 유형의 설정은 *데이터 재배치* 및 *액세스* 설정입니다. 데이터 재배치 정책은 보호되는 앱의 데이터를 사용하는 방법을 정의합니다. 예를 들어 "다른 이름으로 저장"이나 잘라내기, 복사, 붙여넣기 기능을 방지할 수 있습니다. 액세스 정책 설정은 직원이 앱을 사용하는 데 필요하다고 생각되는 장치 보안 수준을 결정합니다. 이러한 설정을 사용할 경우 추가 앱 PIN을 요구하거나 앱이 무단 해제되었거나 루팅된 장치에서 실행되지 않도록 할 수 있습니다.

다음 스크린샷은 Intune MAM 정책을 사용하여 앱을 보호하는 몇 가지 방법을 보여 줍니다. 이 예제에서는 앱에 액세스하기 위해 PIN이 요구되고(액세스 설정) 관리되지 않는 앱에 회사 정보를 붙여넣지 못하게 하여(데이터 재배치 설정) 회사 데이터를 보호합니다.

1.  관리되는 앱(이 예제에서 iOS용 Yammer)가 처음으로 시작되면 사용자는 앱에 액세스하기 위해 PIN을 만들도록 요구됩니다. 그런 다음 앱이 시작될 때마다 해당 PIN을 입력해야 합니다.
2.  사용자는 Yammer 대화와 같은 회사 데이터를 복사한 후 관리되는 다른 앱에 붙여 넣을 수 있습니다.
3.  그러나 사용자가 해당 콘텐츠를 문자 메시지(또는 다른 관리되지 않는 앱)에 붙여 넣으려고 하면 붙여넣기 기능을 사용할 수 없습니다.  

![MAM 정책의 작동 방식을 보여 주는 이미지](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig3.png)

### <a name="windows-information-protection-wip-for-managed-windows-10-pcs-and-mobile-devices"></a>관리되는 Windows 10 PC 및 모바일 장치에 대한 WIP(Windows Information Protection)
Intune의 WIP 정책은 관리되는 Windows 10 장치에서 잠재적인 데이터 손실이 발생하지 않도록 보호합니다. 무엇보다도 이러한 정책은 직원 환경을 방해하지 않고, 네트워크 환경 또는 다른 앱을 변경하지 않고도 작동합니다.

작동 원리는 다음과 같습니다. 엔터프라이즈 데이터가 엔터프라이즈 원본에서 관리되는 Windows 장치에 로드된 이후에 또는 직원이 데이터를 업무용(개인용 아님)으로 표시하는 경우에 자동으로 암호화됩니다. 엔터프라이즈 데이터가 디스크에 기록되면 WIP에서는 Windows에서 제공하는 EFS(파일 시스템 암호화)를 사용하여 데이터를 보호한 후 엔터프라이즈 ID에 연결합니다. Intune WIP 정책을 설정할 때 회사 데이터를 액세스하고 수정하도록 허용되는 신뢰할 수 있는 앱 목록을 정의합니다. 다음으로, AppLocker 기능은 운영 체제에서 백그라운드로 작동하면서 실행될 수 있는 앱과 회사 데이터가 액세스 및 공유될 수 있는 방법을 제어합니다. 허용되는 앱은 Windows에서 회사 데이터에 대한 액세스를 허용하는 목록에 포함되어 있으므로 회사 데이터를 열기 위해 수정될 필요가 없습니다.

> [!TIP]
> WIP 정책에 따라 앱 및 회사 데이터가 보호되는 동안 최종 사용자의 장치에 있는 시작 메뉴에는 허용되는 각 앱 이름과 "관리"가 표시됩니다. 앱 바로 가기와 저장된 파일에도 표준 앱 아이콘 외에 WIP 서류 가방 아이콘이 표시됩니다.
<img src="..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig4.png" alt="Image showing how WIP policies affect the Start Menu and files" style="width:376px;height:112x;">

[WIP 구성 정책 설정](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies)을 사용하여 Intune 관리자 콘솔 내에서 다른 수준의 제어 및 감사를 설정할 수 있습니다. 데이터 보호 수준 범위는 **자동**(WIP 활동만 로그)에서 보호된 앱의 콘텐츠 공유를 완전히 금지하는 **차단**까지입니다. **재정의**는 경고를 나타내면서 보호되지 않는 앱과 회사 데이터를 공유할 수 있도록 하지만 나중에 검토할 수 있도록 이러한 모든 작업을 로깅하는 중간 수준의 설정입니다.

다음은 Intune WIP 정책으로 관리되는 Windows 10 장치의 회사 데이터를 보호하는 방법입니다.
1.  새 WIP 정책이 생성되고 Intune 관리자 콘솔에서 사용자에게 배포됩니다.
2.  이 예제에서 Microsoft Word에 대한 AppLocker 정보는 허용 앱 목록에 Word 2016을 추가하는 데 사용되고, 정책 제한 수준은 재정의로 설정된 후 정책이 사용자에게 배포됩니다.
3.  사용자는 보호되는 Word 2016 문서에서 복사한 회사 데이터를 보호되지 않는 새 메모장 인스턴스에 붙여 넣으려고 합니다. 작업을 업무용에서 개인용 분류로 변경할 예정인지와 작업을 추적되도록 할 것인지를 묻는 메시지가 바로 표시됩니다.

![WIP 정책의 작동 방식을 보여 주는 이미지](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig5.png)

## <a name="selectively-wipe-company-data"></a>선택적으로 회사 데이터 초기화
장치가 더 이상 작업에 필요하지 않거나, 용도 변경 중이거나, 유실된 경우 장치에서 회사 앱과 데이터를 제거해야 합니다. 이를 위해, Intune의 선택적 초기화 및 전체 초기화 기능을 사용할 수 있습니다. 사용자는 Intune 회사 포털에서 관리 기능에 등록한 개인 소유의 장치를 원격으로 초기화할 수 있습니다.

장치를 공장 기본 설정으로 복원하고 사용자 데이터 및 설정을 제거하는 [전체 초기화](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe)를 수행하기보다는 [선택적 초기화](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) 기능을 사용하여 사용자의 개인 데이터를 그대로 유지하면서 장치에서 회사 데이터만 제거할 수 있습니다.

장치의 선택적 초기화는 장치 이름을 마우스 오른쪽 단추로 클릭하고, **사용 중지/초기화**를 선택한 후 **선택적으로 장치를 초기화합니다.**를 선택하여 쉽게 수행할 수 있습니다.

![Intune 콘솔의 선택적 초기화 옵션 이미지](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig6.png)

시작되면 장치가 즉시 선택적 초기화 프로세스를 시작하여 관리 기능에서 제거됩니다. 프로세스가 완료되면 모든 회사 데이터가 삭제되고 장치 이름이 Intune 관리자 콘솔에서 제거되면서 장치 관리 수명 주기가 완료됩니다.

### <a name="learn-more"></a>자세한 정보
[EMS(Enterprise Mobility + Security) 사용 시작](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

