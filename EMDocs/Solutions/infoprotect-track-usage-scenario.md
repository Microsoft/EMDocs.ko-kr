---
title: "공유 데이터의 사용을 추적하고 데이터 남용에 대응 | Azure Rights Management"
description: "EMS(Enterprise Mobility + Security)를 사용하여 공유 데이터 사용을 추적하고 Azure Rights Management 기능을 활용하여 데이터 남용에 대응하는 방법을 설명하는 시나리오입니다."
author: yuridio
manager: swadhwa
ms.date: 12/7/2016
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c7e6e01a-5796-4bd7-a0c5-847ecfc08a1e
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02b0e611805ad2214b1b108b8c466590aad7999a
ms.openlocfilehash: c2004b77928386ed46d947b96b69c1cb85d2e6fb



---

# <a name="track-usage-of-shared-data-and-respond-to-data-abuse"></a>공유 데이터의 사용을 추적하고 데이터 남용에 대응

공유 데이터에 대한 가시성 유지 및 제어는 데이터 사용 또는 남용을 추적하는 데 중요합니다. 오늘날에는 데이터 공유가 더욱 광범위하게 이루어지고 있으며, 조직은 비즈니스 요구를 해결하기 위해 도메인 외부에서 데이터를 공유해야 합니다.

이 상황에서 사용자는 문서를 공유할 뿐만 아니라 누가 문서에 액세스하는지 모니터링하고 필요한 경우 액세스를 취소하는 것이 일반적인 시나리오입니다. IT 관리자는 권한 있는 사용자 그룹과 데이터를 공유할 때도 이와 유사한 환경을 원합니다. 즉 데이터 사용 또는 남용을 계속 제어하고 적절한 조치를 취할 수 있기를 원합니다. Enterprise Mobility + Security로 어떻게 이 시나리오를 해결할 수 있는지 자세히 알아보세요.

## <a name="how-can-enterprise-mobility-security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?
EMS(Enterprise Mobility + Security)는 ID, 장치, 앱, 데이터 등의 4단계 보호 기능으로 장치뿐 아니라 그 이상에서 기업 데이터를 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS를 사용하면 모바일과 클라우드를 선호하는 환경에서 주요 문제 중 하나를 해결하는 데 도움이 됩니다. 즉, 제어 상태를 유지하면서 문제에 신속히 대응하는 조치를 취하는 방법입니다. EMS를 사용하면 직원들이 조직 내외부에서 안전하게 공동 작업을 수행할 수 있습니다. EMS를 사용하면 문서 소유자 및 관리자가 다른 사용자와 공유하는 중요한 파일에 대한 활동을 추적할 수 있습니다. 받는 사람이 파일을 열거나, 무단 사용자의 파일 액세스가 거부되는 등과 같은 활동을 볼 수 있습니다. 파일을 어디에서 액세스했는지 지리적 위치도 볼 수 있습니다. 사용자도 클릭 한 번으로 공유 파일에 대한 액세스를 취소할 수 있습니다.

### <a name="recommended-solution"></a>권장 솔루션
Azure Rights Management를 통합하여 사용자가 보호된 문서를 어떻게 사용하는지 추적할 수 있습니다. 필요한 경우 공유를 중지하고 싶을 때 이러한 문서에 대한 액세스 권한을 취소할 수도 있습니다. 이 기능은 RMS 그룹, 보호된 항목 공유 옵션 및 사용 추적을 사용하여 Office 응용 프로그램 (Word, Excel, Outlook 및 PowerPoint)에 사용할 수 있습니다. Windows 시스템의 경우에는 파일 탐색기를 사용할 수도 있으며, 지원되는 다른 모든 장치에서 웹 브라우저를 사용하 여 사용량을 추적할 수 있습니다. 추적 및 해지는 다음 다이어그램에 표시된 것처럼 문서 수명 주기에서 모니터링 및 응답 단계의 일부입니다.

![Azure Rights Management에서 문서 수명 주기를 보여 주는 그래픽입니다.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig1.png)

Azure Information Protection을 이용하여 문서 사용을 더 간편하게 추적하는 방법에 대해 알아보려면 이 짧은 동영상을 보세요.

<iframe width="675" height="480" src="https://sec.ch9.ms/ch9/76ac/35499c0a-859c-4a3e-9a5c-fa4e5d0e76ac/AzureRMSDocumentTrackingandRevocation_high.mp4 " frameborder="0" allowfullscreen></iframe>

#### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
[내부적/외부적으로 중요한 데이터 공유](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data) 시나리오를 사용하여 이미 Azure Rights Management 및 클라이언트 응용 프로그램을 구성했다면 공유 데이터 사용량 추적 기능을 반드시 구성할 필요가 없습니다. 이제 문서를 추적하는 방법을 선택하기만 하면 됩니다. 사용할 수 있는 옵션은 다음과 같습니다.

1. Office를 사용하여 사용량 추적
- 브라우저를 사용하여 사용량 추적
- 공유 문서에 대한 액세스 취소

### <a name="how-to-track-usage-of-shared-data-and-respond-to-data-abuse"></a>공유 데이터의 사용을 추적하고 데이터 남용에 대응하는 방법
다음 섹션에서는 특정 시나리오에 따라 공유 데이터의 사용량을 추적하는 데 사용할 수 있는 옵션을 소개합니다.

#### <a name="scenario-1-track-usage-using-microsoft-office"></a>시나리오 1: Microsoft Office를 사용하여 사용량 추적
Office 응용 프로그램(Word, Excel 및 PowerPoint)을 사용하여 보호된 문서 사용에 관한 자세한 정보를 보려면 다음 그림에 표시된 것처럼 **보호된 항목 공유** 옵션을 선택한 다음 **사용 추적**을 클릭합니다.

![사용자가 Office 응용 프로그램에서 "사용 추적" 옵션을 설정하는 방법을 보여 주는 그래픽입니다.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig2.png)

이 기능에 대한 자세한 내용은 [RMS 공유 앱을 사용하는 경우 문서 추적 및 취소](https://docs.microsoft.com/information-protection/rms-client/sharing-app-track-revoke) 항목을 참조하세요.

#### <a name="scenario-2-track-usage-using-browser"></a>시나리오 2: 브라우저를 사용하여 사용량 추적
경우에 따라 사용자의 장치에 Office 응용 프로그램이 없을 수 있지만 문서 사용량을 모니터링해야 합니다. [지원 브라우저](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke)에서 [문서 추적 사이트](http://go.microsoft.com/fwlink/?LinkId=529562)로 이동한 후 자격 증명으로 로그인하고 추적하려는 문서를 선택하면 다음 화면에 표시된 것처럼 사용 통계가 표시됩니다.

![웹 브라우저에서 전체 문서 사용 통계를 보여 주는 그래픽입니다.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig3.png)

이 화면에서 보기의 수 및 이 파일이 공유된 개월 수에 대 한 액세스 거부 횟수를 확인할 수 있습니다. 각 타일에는 파일에 액세스한 사용자를 보여 주는 요약이 있지만 타일을 클릭하면 자세한 정보를 볼 수 있습니다. 이전 화면의 예제에서 거부된 액세스를 선택하면 다음과 같은 결과가 표시됩니다.

![웹 브라우저에서 문서에 대해 거부된 액세스 통계를 보여 주는 그래픽입니다.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig4.png)

#### <a name="scenario-3-revoke-access-to-shared-document"></a>시나리오 3: 공유 문서에 대한 액세스 취소

문서를 모니터링하는 동안 사용 현황은 사용자의 동작을 이해 하는 중요한 단계입니다. 문서를 모니터링하면서 확인하게 된 사실을 토대로 조치를 취할 때는 가장 큰 값이 사용됩니다. 예를 들어 사용 현황 보고서를 읽고 유효한 사용자가 이 문서에 액세스를 시도하는 동안 액세스가 거부되었다는 사실을 확인했습니다. 이 시점에서 이 문제를 해결하기 위한 정정 작업을 수행해야 합니다.

보안 사고에 대해 어떤 위치에서 응답하는지에 대한 시나리오도 있습니다. 예를 들어 널리 공유된 문서 중 하나에 회사의 기밀 정보가 들어 있다는 사실을 확인하고 HR은 IT 부서에게 이 문서에 대한 액세스를 취소할 것을 요청했습니다. [문서를 해지](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke)하는 경우 공유한 문서가 삭제되지는 않지만, 권한 있는 사용자가 이 문서를 더 이상 열 수 없게 됩니다. 액세스를 취소하려는 경우 사용 추적 페이지에 있는 **액세스 취소**를 클릭하면 다음 화면과 유사한 폼이 나타납니다.

![문서에 대한 액세스를 취소할 수 있는 액세스 취소 폼을 보여주는 그래픽입니다.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig5.png)

이 문서에 대한 액세스가 취소되었음을 받는 사람에게 알리는 옵션을 사용할 수 있으며, 이 문서가 취소된 이유에 대한 설명을 곁들일 수 있습니다.



<!--HONumber=Dec16_HO2-->


