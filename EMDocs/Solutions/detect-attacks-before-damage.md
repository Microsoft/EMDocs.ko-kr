---
title: 손상을 입기 전에 공격 감지 | Microsoft 문서
description: Enterprise Mobility + Security를 통해 Advanced Threats Analytics, Cloud App Security, Azure Active Directory Premium을 활용하여 공격으로 인한 손상이 발생하기 전에 해당 공격으로부터 기업 데이터를 보호할 수 있는 방법을 설명하는 시나리오입니다.
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.assetid: de0a7e70-008b-45c1-bba8-f033b1f62194
ms.reviewer: v-craic
ms.suite: ems
ms.custom: advanced-threat-analytics, cloud-app-security
ms.openlocfilehash: 26276999420e809a041f36214890539e49b59079
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196749"
---
# <a name="detect-attacks-before-they-cause-damage"></a>손상을 입기 전에 공격 감지
보안 상태가 강력하더라도 심각한 손상이 발생하기 전에 위협을 식별할 수 있으려면 가동 중인 고급 검색 시스템이 필요합니다. 조직에서는 온-프레미스와 클라우드에서 의심스러운 활동을 검색할 수 있도록 Microsoft 보안 인텔리전스를 원활하게 활용할 수 있습니다.

강력한 검색 시스템은 심도있는 가시성과 지속적인 동작 통계를 통해 의심스러운 활동을 발견하고 위협을 파악해야 합니다. 이렇게 하면 IT에서 검색된 공격에 대한 즉각적인 조치를 수행하고 강력한 지원을 통해 복구 작업을 간소화합니다.


## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?
Microsoft Enterprise Mobility + Security를 사용하면 IT에서는 온-프레미스와 클라우드에서 혁신적인 행동 분석과 변칙 감지 기술을 사용하여 조직에서 공격자를 식별할 수 있습니다.  시스템에서 알려진 악의적인 공격 및 알려진 보안 취약성을 감지하도록 IT를 지원하게 됩니다.

## <a name="recommended-solution"></a>권장 솔루션
이 시나리오에 대한 요구 사항을 해결하기 위해 EMS에서는 [Advanced Threats Analytics](https://docs.microsoft.com/advanced-threat-analytics/), [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 및 [Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)을 사용합니다. 이러한 기술에 구현하여 조직은 다음을 수행할 수 있게 됩니다.

- 기계 학습을 활용한 혁신적인 행동 분석과 변칙 감지 기술을 사용하여 비정상적인 동작을 검색하거나 식별
- 알려진 악의적인 공격(예: Pass-the-Hash, Pass-the-Ticket) 및 알려진 보안 취약성 검색
- 매우 명확한 공격 정보와, 이와 관련된 공격 정보에 집중
- 보안 위반을 나타낼 수 있는 잘못된 부분과 정책 위반 식별

다음 다이어그램에서는 이 시나리오와 관련된 기능과 리소스 보호를 위해 이러한 기능이 사용되는 방식을 요약해서 보여 줍니다.

![각 제품 솔루션의 기능 및 공격으로부터 보호하기 위해 작동하는 방법을 보여 주는 그래픽.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig1.png)

# <a name="how-to-detect-attacks-before-they-cause-damage"></a>손상을 입기 전에 공격을 검색하는 방법
일반적으로 보안과 관련된 투자는 보호에만 중점을 두었습니다. 그러나 이제는 강력한 감지 및 대응 기능을 갖추는 것이 필수적입니다. IT 조직은 위협을 보호, 감지하고, 이에 대응하는 방법을 살펴보는 방법에 중점을 두어야 합니다.

![위협을 보호, 감지하고, 이에 대응하는 지속적인 프로세스를 보여 주는 그래픽](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig2.png)

IT는 온-프레미스 또는 클라우드에서 ID, 데이터, 응용 프로그램, 장치 및 인프라를 적절하게 보호하는 방법을 확인해야 합니다.  이렇게 하려면 센서부터 데이터 센터에 이르기까지 모든 끝점을 고려하는 보안 방식으로 접근해야 합니다. 과거에는 IT 관리자가 위협을 인식하기 위해 맬웨어 서명에 의존했습니다.

기존 IT 보안 도구는 사용자 자격 증명을 도난당했을 때 정교한 사이버 보안 공격에 대해 제한된 보호를 제공합니다. 초기 설정부터 규칙 만들기, 미세 조정은 번거로운 작업으로 몇 년이 걸릴 수 있습니다. 여러분은 매일 거짓 긍정으로 가득 찬 보고서를 여러 개 받습니다. 대부분의 경우 이 정보를 검토하는 리소스가 없으며, 있더라도 답변을 받지 못할 수도 있습니다. 이 도구는 경계를 보호하도록 설계되어 공격자가 액세스하지 못하도록 합니다. 오늘날의 복잡한 사이버 보안 공격에는 다른 접근 방법이 필요합니다.

이 새로운 사이버 보안 공격 선상에서 현재 위협을 완화하기 위해 IT는 동작 분석 및 기계 학습을 활용하는 혁신적인 위협 검색 솔루션을 필요로 합니다.  ATA 및 Cloud App Security를 활용하여 온-프레미스와 클라우드에서 공격을 검색함으로써 IT는 심각한 손상이 발생하기 전에 사고에 신속하게 대응할 수 있습니다.

ATA를 설치 하기 전에 먼저 일반적인 고려 사항을 확인하려면 온-프레미스에서 ATA를 구현하기 전에 [ATA 용량 계획](https://docs.microsoft.com/advanced-threat-analytics/plan-design/ata-capacity-planning)과 [ATA 필수 구성 요소](https://docs.microsoft.com/advanced-threat-analytics/plan-design/ata-prerequisites)를 읽어보세요. [사전 설치 검사 목록](https://docs.microsoft.com/advanced-threat-analytics/deploy-use/preinstall-ata)을 사용하여 인프라에서 ATA를 받을 준비가 되어 있는지 검증합니다. 계획 및 유효성 검사 단계를 완료하면 [ATA를 배포](https://docs.microsoft.com/advanced-threat-analytics/deploy-use/install-ata-step1)할 준비가 됩니다. ATA가 사용자 환경에 배포되면 구성이 최소화되어 즉시 사용 중인 환경에 대해 학습을 시작하고 알려진 악의적인 공격이 발견되면 경고를 트리거합니다. 1단계에 따라 [ATA](https://docs.microsoft.com/advanced-threat-analytics/understand-explore/what-is-ata)를 사용하여 온-프레미스에서 의심스러운 활동을 식별해 보세요.

클라우드 앱에 대한 위협을 검색하기 위해 이 시나리오에서는 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 사용합니다. Cloud App Security 설치를 위해 [일반 설치 지침](https://docs.microsoft.com/cloud-app-security/general-setup)을 따르고, Cloud App Security 클라우드 앱 카탈로그에 대한 트래픽 로그를 분석을 위해 [클라우드 검색](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) 옵션을 사용해야 합니다. 2단계에서는 Cloud App Security를 사용하여 위협 및 규정 준수 위반을 검색합니다.

## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
다음 단계에 따라 [Advanced Threats Analytics](https://docs.microsoft.com/advanced-threat-analytics/) 및 [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)를 구현할 수 있습니다.

- 1단계: Microsoft ATA(Advanced Threat Analytics)를 사용하여 온-프레미스에서 의심스러운 활동 검색
- 2단계: Cloud App Security를 사용하여 클라우드 앱에 대한 위협 및 규정 준수 위반 검색  

### <a name="step-1-using-ata-to-detect-suspicious-activity"></a>1단계: ATA를 사용하여 의심스러운 활동 검색
기존의 보안 도구를 통한 지속적인 보고를 받고 이 중 중요하고 관련 있는 경고를 찾는 것은 부담스러울 수 있습니다. 대신 ATA는 사용이 쉽고, 드릴다운이 간단하고, 소셜 미디어 피드와 유사한 보고서 양식을 제공하여 IT에서 가장 중요한 것을 빠르게 집중할 수 있도록 지원합니다. 이 데이터 수를 타임라인으로 나타내면 누가 어떤 정보에 언제 어떻게 액세스하는지에 대한 효율적인 관점과 인사이트를 제공합니다.

ATA에서 [공격 타임라인](https://docs.microsoft.com/advanced-threat-analytics/deploy-use/working-with-suspicious-activities)을 열면 의심스러운 활동이 포함된 종합 보고서가 표시되어 이 활동과 권장 사항에 대한 [엔터티](https://docs.microsoft.com/advanced-threat-analytics/plan-design/ata-architecture)를 볼 수 있습니다.

![의심스러운 활동에 대한 보고서에서 공격 타임라인 스크린샷.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig3.png)

이 예제에서는 Pass-the-Ticket 공격을 사용하는 신원 도용이 의심되는 이벤트가 있습니다. 초기 문제 해결 단계에 사용할 수 있는 권장 사항 목록도 있습니다. 이 예제에서는 서버 SHAREDADMIN-SRV에서 EXTVENDOR-TS로의 관리자 Keberos 티켓이 도난당하여 DC01에 액세스하는 데 사용되었기 때문에 ATA에서 경고를 제공합니다. 이 이벤트의 개체를 클릭하여 조사 프로세스를 심도 있게 진행할 수 있습니다. 예를 들어 외부 공급 업체 터미널 서버(EXTVENDOR TS)를 클릭하여 이 서버와 관련된 모든 [의심스러운 활동](https://docs.microsoft.com/advanced-threat-analytics/deploy-use/working-with-suspicious-activities)에 액세스할 수 있습니다.

ATA는 결정 엔진과 검색 엔진 모두에서 기계 학습을 사용하여 사용자와 엔티티에 대한 일반적인 동작 패턴 이해를 설정합니다. 이 기능은 거대한 공격을 일으키는 매개체 전체에 대해 정확하고 시기 적절한 경고를 제공하게 하는 ATA의 고유한 기능입니다.


### <a name="step-2-using-cloud-app-security-to-detect-threats-and-policy-violations-for-cloud-apps"></a>2단계: Cloud App Security를 사용하여 클라우드 앱에 대한 위협 및 정책 위반 검색

많은 조직에서는 비용 절감뿐 아니라 향상된 출시 시기와 효율적인 협업과 같은 경쟁 우위의 장벽을 허물기 위해 SaaS 앱을 채택하고 있습니다. 회사에서 클라우드 응용 프로그램을 사용하지 않더라도 직원은 그럴 수도 있습니다. 연구에 따르면 직원의 80% 이상이 직장에서 승인 되지 않은 SaaS 앱을 사용하고 있음을 인정합니다.

클라우드 앱에 대한 이러한 빠른 전환으로 인해 클라우드에서 회사 데이터를 저장하고, 포괄적인 가시성, 감사 또는 통제 없이 어디에서나 사용자가 액세스할 수 있게 하는 방법에 대해 걱정이 될 수 있습니다. 기존 보안 솔루션은 SaaS 응용 프로그램에서 데이터를 보호하도록 설계되지 않았습니다. IP, 방화벽 등의 전통적인 네트워크 보안 솔루션에서는 데이터를 사용하고 저장하는 방식을 비롯하여 각 응용 프로그램 및 트래픽 오프-프레미스에 고유한 트랜잭션에 대한 가시성을 제공하지 않습니다. 기존의 제어 방식으로는 작은 클라우드 트래픽 일부만 모니터링하고 앱 수준 활동에 대해 제한적으로 이해하기 때문에 클라우드 앱에 대한 보호를 제공할 수 없습니다.

그렇다면 클라우드 앱의 가시성, 제어 및 보호는 어떻게 유지 관리할 수 있을까요? 다음과 같이 해결책을 제시해 드립니다.

Microsoft Cloud App Security는 클라우드 앱에 대한 심도있는 가시성, 포괄적인 제어 및 향상된 보호를 제공하는 포괄적인 서비스입니다. Cloud App Security는 온-프레미스에서 구현했던 가시성, 감시, 제어를 클라우드 응용 프로그램으로 확장할 수 있도록 설계되었습니다.

Cloud App Security는 가시성 및 제어뿐만 아니라 광범위한 Microsoft 위협 인텔리전스 및 연구로 향상되어 클라우드 응용 프로그램에 대한 강력한 위협 보호를 제공합니다. 위험도가 높은 사용 및 보안 문제를 식별할 수 있으며 위협 방지를 위해 비정상적인 사용자 동작을 검색할 수 있습니다.

Cloud App Security 대시보드에 액세스하면 경고에 대한 전용 섹션을 포함하여 클라우드 앱의 보안 상태에 대해 포괄적으로 볼 수 있습니다.

![미해결 경고가 포함된 Cloud App Security 대시보드의 스크린샷.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig6.png)

경고 메뉴를 클릭하면 [경고 센터](https://docs.microsoft.com/cloud-app-security/monitor-alerts)에 액세스할 수 있습니다. 경고 센터에서는 위협 검색, 권한 있는 계정 및 규정 준수 위반을 비롯하여 다양한 분야의 경고를 수집합니다.

![각 경고의 목록을 표시하는 경고 센터의 스크린샷.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig5.png)

경고 센터에서는 잘못된 부분, 위협 검색 규정 준수 위반 및 권한 있는 계정을 포함하여 Cloud App Security에서 식별하는 모든 징후를 수집합니다. Cloud App Security의 고급 기계 학습 추론 방식을 통해 각 사용자가 클라우드 앱을 조작하는 방식, 그리고 행동 분석을 통해 각 트랜잭션에서 위험을 평가하는 방식을 살펴볼 수 있습니다.

경고를 조사하는 경우 경고 이름을 클릭하면 해당 경고에 대한 자세한 내용을 볼 수 있습니다. 다음 예제에서는 경고가 참조하는 일치하는 [정책 파일](https://docs.microsoft.com/cloud-app-security/data-protection-policies) *공유된 기밀 파일 공개*에서 일치하는 항목을 참조합니다. 데이터 누출을 일으킬 수 있으므로 우선 순위가 높은 것으로 간주됩니다.   

![경고 중 하나에 대한 특정 세부 정보 스크린샷.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig7.png)

앞의 예제는 정책 위반에 대해 살펴보았습니다. Cloud App Security는 또한 [잘못된 부분](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy#anomaly-detection-policy-reference)을 검색할 수도 있습니다. Cloud App Security에는 새 사용자, 활동, 장치 또는 위치에 대해 비정상으로 플래그를 지정하지 않는 7일 간의 초기 학습 기간이 있습니다. 검색하고 나면 각 세션과 이전 달에 감지된 활동(사용자가 활성 상태였던 시기, IP 주소, 장치)이 비교되고 위험 점수가 각 활동에 할당됩니다. 이 경고 유형에 대한 설명을 일반적인 이상 검색이라고 하며, 경고를 클릭하면 다음과 비슷한 화면이 표시됩니다.

![Cloud App Security에서 검색된 잘못된 부분을 보여 주는 스크린샷.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig8.png)

이 페이지에서는 경고를 트리거한 사용자, IP 주소, 사용자의 그룹 구성원, 그리고 의심스러운 동작에 대한 자세한 내용을 확인할 수 있습니다. 실패한 로그온 시도, 로그온이 발생한 위치 및 로그온 시도 수행하는 데 사용된 앱을 포함하여 이 활동에 대한 자세한 정보를 볼 수 있습니다.
