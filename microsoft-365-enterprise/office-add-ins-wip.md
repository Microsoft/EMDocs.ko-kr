---
title: Microsoft Office 추가 기능-Microsoft 365 Enterprise를 실행 하는 엔터프라이즈 문서 보호 | Microsoft 문서
description: Office 추가 기능을 실행 하는 문서에서 엔터프라이즈 데이터를 보호 하기 위해 진행 중 및 Intune를 사용 하는 방법에 설명 합니다.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 5f43eba8b95b0eefaaef6e95bce6fd5d8c1f6695
ms.sourcegitcommit: a322bdd365c7d648c5241cf959dcd04b3815672d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>WIP 및 Intune을 사용하여 Office 추가 기능을 실행하는 문서의 엔터프라이즈 데이터 보호
여기서는 조직의 사용자가 Office 추가 기능을 사용하여 조직 데이터와 상호 작용할 때 일부 데이터가 누출될 수 있는 잠재적 위험을 소개합니다. 사용자가 Office 추가 기능을 실행할 때 WIP(Windows Information Protection) 및 Microsoft Intune을 사용하여 엔터프라이즈 데이터를 보호할 수 있습니다.

[WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) - 이전에 EDP(엔터프라이즈 데이터 보호)로 알려졌으며, 이를 사용하면 엔터프라이즈에서 지적 재산권 및 회사 데이터를 보호할 수 있습니다. 즉 환경이나 다른 앱을 변경하지 않고도 회사 소유의 장치와 직원이 업무를 위해 회사에 가져오는 개인 장치 모두에 있는 엔터프라이즈 앱 및 데이터가 실수로 누출되지 않도록 보호할 수 있습니다.

[Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) - 복잡한 모바일 환경을 관리하기 위한 다양한 도구 집합을 제공합니다. Intune에서 모바일 응용 프로그램 관리와 장치 관리 옵션을 결합하면 IT 관리자와 최종 사용자가 모바일 생산성을 원활하게 관리하고 보호할 수 있습니다.

Intune을 사용하여 [WIP 정책을 만들고 배포할 수 있습니다](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy). Intune을 사용하면 보호된 응용 프로그램과 WIP 보호 수준을 선택하고 네트워크에서 엔터프라이즈 데이터를 찾을 수 있습니다.

WIP 및 Intune을 사용하는 경우

-   데이터가 개인 장치에 다운로드되는 경우에도 엔터프라이즈에서 합리적인 기업 데이터 정책을 적용할 수 있습니다.

-   엔터프라이즈에서 상황별 정책 교육을 사용하여 관리되지 않는 앱과 서비스에 데이터가 실수로 공개되지 않도록 보호하는 방법을 사용자에게 알릴 수 있습니다.

-   최종 사용자가 일반적인 워크플로를 중단하지 않고 회사 데이터 정책을 준수할 수 있습니다.

-   최종 사용자가 업무와 개인 생산성 간에 원활하게 전환할 수 있습니다.

WIP 및 Intune은 백그라운드에서 자동으로 실행되며 사용자가 개인 및 엔터프라이즈 콘텐츠를 혼합하지 않으면 거의 표시되지 않습니다.

[Office 추가 기능](https://dev.office.com/docs/add-ins/overview/office-add-ins)은 웹 기술을 기반으로 하여 빌드됩니다. 웹의 기능과 정보를 Office 응용 프로그램으로 가져옵니다. 추가 기능은 Office.js에서 사용할 수 있는 API를 통해 Office 응용 프로그램의 콘텐츠와 상호 작용합니다. Office 추가 기능의 핵심 개념은 다음과 같습니다.

-   **보안**: Office JavaScript 플랫폼 아키텍처를 사용하면 추가 기능 코드가 샌드박스를 작동하고 호스트 Office 응용 프로그램과 관련하여 별도의 프로세스로 실행됩니다. 이렇게 하면 추가 기능이 성능 표준에 충족되지 않거나 잠재적으로 악의적인 경우 플랫폼에서 사용자에게 알리고 경우에 따라 추가 기능이 사용되지 않도록 설정하여 수정 작업을 수행할 수 있습니다. 이 아키텍처는 Office 추가 기능을 지원하는 모든 플랫폼에서 작동합니다.

-   **복원력**: 추가 기능 플랫폼의 "외부 프로세스(out-of-process)" 특성으로 인해 추가 기능 자체가 호스트 Office 응용 프로그램의 성능이나 사용자 환경에 영향을 주지 않습니다. 이는 Office에서 사용자 작업에 빠르게 응답하는 데 매우 중요합니다.

-   **플랫폼 간**: 한 번만 작성하면 Office가 실행되는 모든 곳에서 실행됩니다. 추가 기능은 현재 Windows, Office Online, Mac 및 iPad에서 지원됩니다. Android 및 Universal 플랫폼의 추가 기능에 대한 지원은 곧 제공될 예정입니다.

Office 추가 기능은 문서 내에서 엔터프라이즈 및 잠재적으로 중요한 콘텐츠를 처리할 수 있습니다. 응용 프로그램 확장의 일부로 추가 기능은 호스트 응용 프로그램 정책에서 액세스 권한을 상속합니다. 예를 들어 WIP 설정에 따라 Word에서 엔터프라이즈 콘텐츠에 액세스하지 못하는 경우 추가 기능에서 Word 문서의 엔터프라이즈 콘텐츠에 액세스할 수 없게 됩니다.

추가 기능의 목표 중 하나는 최종 사용자의 모든 차단 문제를 제거하는 한편 엔터프라이즈 관리자에서 필요한 경우 추가 기능을 차단할 수 있게 하는 것입니다. 데이터 보호 사용과 관련된 Office 추가 기능의 기본 원칙은 다음과 같습니다.

-   IT 관리자가 추가 기능을 로드하지 않도록 차단하는 방법을 제공합니다.

-   추가 기능 엔터프라이즈를 준비하기 위해 관리자에게 필요한 작업을 최소화하거나 제거합니다.

-   추가 기능을 사용하는 동안 최종 사용자에 대한 프롬프트와 메시지를 최소화합니다.

-   문서와 추가 기능에 동일한 컨텍스트가 있는 경우 최종 사용자에 대한 프롬프트를 제거합니다.

## <a name="add-ins-and-wip"></a>추가 기능 및 WIP

사용자 환경에서 WIP를 사용하도록 설정하면 Office 추가 기능에 다음과 같은 시나리오를 적용할 수 있습니다.

-   Office 추가 기능은 문서 컨텍스트를 사용하여 활성화됩니다. Outlook의 경우 추가 기능 컨텍스트는 현재 활성 사서함을 기반으로 합니다. 추가 기능이 활성화되기 전에 추가 기능 권한이 신뢰 프롬프트에 명확하게 정의됩니다. 사용자가 추가 기능이 특정 문서에서 적절한지와 추가 기능을 실행할 수 있도록 허용할지를 결정합니다.

-   관리자가 그룹 정책을 사용하여 모든 Office 스토어 추가 기능 또는 모든 Office 추가 기능을 차단할 수 있습니다. 즉, 사용자는 [SharePoint 또는 Office 365 회사 카탈로그(영문)](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)에서 신뢰할 수 있는 추가 기능만 활성화할 수 있습니다.

-   관리자가 MDM(모바일 장치 관리)을 사용하여 방화벽 수준에서 추가 기능을 차단할 수 있습니다. 이 기능은 모바일 또는 BYOD(Bring Your Own Device) 시나리오에서 작동하지 않습니다.

-   추가 기능에서 엔터프라이즈 컨텍스트와 개인 컨텍스트 간에 복사-붙여넣기 작업을 적용합니다. 예를 들어 사용자가 엔터프라이즈 컨텍스트 추가 기능에서 복사하여 개인 문서에 붙여넣는 경우 컨텍스트 간에 기본 복사-붙여넣기 프롬프트가 표시됩니다.

다음 표에서는 WIP를 사용하도록 설정할 때 엔터프라이즈와 개인의 컨텍스트 및 문서에서 예상되는 추가 기능 동작을 나열하고 있습니다.

> [!NOTE]
> - 호스트 응용 프로그램 내부 및 외부의 잘라내기, 복사 및 붙여넣기 작업은 모든 시나리오에서 예상대로 작동합니다.
> - 추가 기능 서비스로의 데이터 전송은 모든 시나리오에서 보호되지 않습니다.

|**문서 또는 사서함 유형**|**개인 컨텍스트별 추가 기능**|**엔터프라이즈 컨텍스트별 추가 기능**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**개인**     |개인 컨텍스트별 추가 기능을 로드합니다.<br><br>회사 URL 탐색이 허용되지 않습니다(자체 앱 도메인에 있는 경우에도).<br><br>개인 URL 탐색이 허용됩니다.|추가 기능을 로드하거나 활성화하는 데 실패합니다.<br><br>문서의 컨텍스트가 상승하는 경우(예: 엔터프라이즈 위치에 저장함으로써)<br><br>- 회사 URL 탐색이 허용됩니다.<br><br>- 개인 URL 탐색이 허용됩니다.|
|**엔터프라이즈**   |엔터프라이즈 컨텍스트별 추가 기능을 로드합니다.<br><br>회사 URL 탐색이 허용됩니다.<br><br>개인 URL 탐색이 허용됩니다.|엔터프라이즈 컨텍스트별 추가 기능을 로드합니다.<br><br>회사 URL 탐색이 허용됩니다.<br><br>개인 URL 탐색이 허용됩니다.|
|**저장되지 않음**      |개인 컨텍스트별 추가 기능을 로드합니다.<br><br>회사 URL 탐색이 허용되지 않습니다(자체 앱 도메인에 있는 경우에도).<br><br>개인 URL 탐색이 허용됩니다.|엔터프라이즈 컨텍스트별 추가 기능을 로드하며, 문서는 자동으로 엔터프라이즈 컨텍스트로 변환됩니다. 즉 문서는 엔터프라이즈 위치에 저장해야 합니다.<br><br>회사 및 개인 URL 탐색이 허용됩니다.            |


## <a name="add-ins-and-intune"></a>추가 기능 및 Intune

iPad용 Office에서 Office 추가 기능은 현재 Word, Excel 및 PowerPoint에서 지원됩니다. Outlook은 현재 iOS(iPad 및 iPhone)에서 추가 기능을 지원합니다. Outlook 관리자는 기본적으로 추가 기능(개발자가 설치한 추가 기능 포함)을 해제하고 조직에서 승인한 특정 추가 기능만 사용하도록 설정할 수 있습니다. 다음 표에서는 Intune 앱 보호 도구를 사용하는 iOS용 Office 장치에서 실행되는 추가 기능에 대한 데이터 보호 시나리오 지원을 요약하고 있습니다.

> [!NOTE]
> Android 및 iOS 장치에서 실행되는 Outlook 추가 기능에 대한 자세한 내용은 [Outlook용 추가 기능에 대한 사용자 액세스 관리](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) 및 [Outlook용 추가 기능](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx)을 참조하세요.

|**문서 또는 사서함 유형**|**Intune 앱 보호가 포함된 iOS용 개인 콘텍스트별 추가 기능<sup>*</sup>**|**Intune 앱 보호가 포함된 iOS용 엔터프라이즈 컨텍스트별 추가 기능<sup>*</sup>**|
|:-----|:-----|:-----|
|**개인**|개인 문서의 Intune 앱 보호로부터 영향을 받지 않고 추가 기능을 사용할 수 있습니다.|개인 문서의 Intune 앱 보호로부터 영향을 받지 않고 추가 기능을 사용할 수 있습니다.|
|**엔터프라이즈**|개인 추가 기능을 활성화할 수 있습니다.<br><br>Intune 앱 보호 정책을 사용하여 장치의 추가 기능과 다른 응용 프로그램 간의 잘라내기, 복사, 붙여넣기 및 데이터 전송 시나리오를 보호할 수 있습니다.<br><br>추가 기능 서비스로의 데이터 전송은 보호되지 않습니다.|엔터프라이즈 추가 기능을 활성화할 수 있습니다. 관리자가 Office 관리 도구[(Office 365 중앙 집중식 배포)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f)를 통해 게시되는 추가 기능을 제어할 수 있습니다.<br><br>Intune 앱 보호 정책을 사용하여 장치의 추가 기능과 다른 응용 프로그램 간의 잘라내기, 복사, 붙여넣기 및 데이터 전송 시나리오를 보호할 수 있습니다.<br><br>추가 기능 서비스로의 데이터 전송은 보호되지 않습니다.|

>**<sup>*</sup>** 관리자는 [Office 365 중앙 집중식 배포](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f)를 사용하여 Word, Excel 및 PowerPoint 추가 기능을 Office 365 관리 센터 또는 PowerShell 스크립트를 사용하여 개별 사용자, 그룹 또는 조직에 직접 배포할 수 있습니다. 사용자가 Windows, Mac 또는 Office Online에서 Office 응용 프로그램을 열면 추가 기능이 해당 리본에 자동으로 설치됩니다.

## <a name="summary"></a>요약

Office 추가 기능에 대한 원칙을 고려할 때 WIP 및 Intune을 사용하면 관리자가 엔터프라이즈 데이터를 관리하고 최종 사용자에게 업무를 수행하는 데 필요한 도구를 제공할 수 있습니다. 이로 인해 회사 데이터가 조직 외부로 누출될 수 있습니다. Office JavaScript API는 현재 개발자가 Office 문서와 추가 기능 간에 전송되는 데이터 형식을 인식할 수 있는 방법을 제공하지 않습니다. 이렇게 하려면 개발자가 사용자에게 여러 가지 프롬프트를 표시해야 하며, 경우에 따라 개인 파일을 엔터프라이즈 파일로 잘못 표시하여 사용자 환경에 부정적인 영향을 줄 수 있으며 데이터 보호 원칙과 일치하지 않습니다.

Microsoft는 고객 데이터를 보호하기 위해 노력하고 있으며, Intune 및 WIP 기술을 개발하고 고객에게 더 나은 환경을 제공하기 위해 계속 투자하고 있습니다.

## <a name="learn-more"></a>자세한 정보

-   [WIP(Windows Information Protection)에 대한 일반 지침 및 모범 사례](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [Intune이란?](https://docs.microsoft.com/intune/introduction-intune)

-   [장치 등록 방법 개요](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [MDM 기관 변경](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [Windows 10용 앱 보호 정책 구성 준비](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
