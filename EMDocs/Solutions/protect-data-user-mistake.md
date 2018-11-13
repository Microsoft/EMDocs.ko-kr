---
title: 사용자 실수로부터 데이터 보호 | Microsoft 문서
description: Enterprise Mobility + Security를 통해 Cloud App Security 및 Azure Information Protection 기능을 활용하여 사용자 실수로부터 회사 데이터를 보호하고 데이터 손실을 방지할 수 있는 방법을 설명하는 시나리오입니다.
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 09/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.assetid: 0af3894c-7b0e-4c0c-8874-31e041d81300
ms.reviewer: v-craic
ms.suite: ems
ms.custom: information-protection
ms.openlocfilehash: 5b1e5d113546da0df64e7777c0031543a7096a72
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196698"
---
# <a name="protect-data-against-user-mistakes"></a>사용자 실수로부터 데이터 보호

이동성 및 클라우드로의 전환은 직원 생산성을 크게 향상시켰지만 온-프레미스와 클라우드 모두에서 사용자, 장치, 응용 프로그램 및 데이터 간의 복잡한 상호 작용으로 인해 IT 팀에 새로운 과제를 안겨 주었습니다. 조직에서 이러한 전환을 수용하지 않을 수도 있지만 직원들은 이미 전환한 상태입니다. 이러한 구성 요소 간의 상호 작용 및 공격 벡터의 정교성이 증가함에 따라 보안은 여전히 기업의 가장 중요한 과제입니다. IT 직원들은 회사 데이터의 가시성, 제어 및 보호를 유지 관리하기 위해 노력하고 있습니다.

사용자 실수로부터 회사 데이터를 보호하고 데이터 손실을 방지하는 데이터 제어 리소스는 사용자의 생산성을 유지하면서 리소스의 보안을 유지하기 위한 중요한 단계입니다.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?

EMS(Enterprise Mobility + Security)를 통해 IT 부서는 온-프레미스와 클라우드에서 사용자, 장치 및 데이터 작업에 대한 보다 심도 깊은 가시성을 얻을 수 있습니다.  EMS를 사용하면 보다 강력한 제어 및 적용을 통해 사용자 실수로부터 회사 데이터를 보호할 수 있습니다.  IT 부서에서는 사용자, 업로드/다운로드 트래픽, 사용 패턴 및 검색된 응용 프로그램의 트랜잭션에 대한 강력한 보고 및 분석을 사용하여 위험 감지를 모니터링할 수 있습니다.

## <a name="recommended-solution"></a>권장 솔루션

이 시나리오에 대한 요구 사항을 해결하기 위해 EMS에서는 [Cloud App Security](https://technet.microsoft.com/library/mt489024.aspx) 및 [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)을 사용합니다. 이러한 기술을 구현하여 조직에서 얻을 수 있는 이점은 다음과 같습니다.

- 직원의 클라우드 응용 프로그램 사용 현황 및 섀도 IT에 대한 완전한 가시성
- 클라우드 응용 프로그램의 지속적인 데이터 보호에 대한 세부적인 제어 및 데이터 정책
- 데이터의 저장 위치 및 공유 대상에 상관없이 데이터가 항상 보호되도록 하는 영구 데이터 분류 및 보호
- 조직 내부 및 외부 사용자와의 안전한 데이터 공유
- 데이터 분류 및 보호에 대한 직관적인 제어
- 사용자 및 IT에 대한 공유 데이터의 가시성 및 제어

다음 다이어그램에서는 이 시나리오와 관련된 기능과 리소스 보호를 위해 이러한 기능이 사용되는 방식을 요약해서 보여 줍니다.

![Cloud App Security와 Azure Information Protection을 함께 사용하여 온-프레미스 및 클라우드에서 데이터를 보호하는 방법을 보여 주는 그래픽](./media/protect-data-user-mistake/protect-data-user-mistake-fig1-1.png)

이 짧은 비디오는 IT가 EMS(Enterprise Mobility + Security)를 통해 심층적인 가시성과 제어력을 얻는 방법을 간략히 소개합니다.

<iframe width="675" height="480" src="https://www.youtube.com/embed/LWlRVHp7sKQ" frameborder="0" allowfullscreen></iframe>


## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

다음 단계에 따라 [Cloud App Security](https://technet.microsoft.com/library/mt668458.aspx) 및 [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)을 구현할 수 있습니다.

- 1단계: 사용 중인 클라우드 응용 프로그램 검색 및 정책을 통한 제어
- 2단계: 온-프레미스 및 클라우드에서 데이터 보호

## <a name="how-to-protect-data-against-user-mistakes"></a>사용자 실수로부터 데이터를 보호하는 방법

오늘날 대부분의 기업에서 클라우드 응용 프로그램을 사용하므로 조만간 온-프레미스보다 클라우드에 저장되는 회사 데이터가 더 많아질 것입니다. 대부분의 경우 사용자는 회사의 동의 없이 또는 회사에서 모르게 자신의 장치에서 SaaS 응용 프로그램을 사용할 것이므로 이로 인해 클라우드의 섀도 IT 사용이 증가할 것입니다. 이러한 결론은 직원의 80%가 승인되지 않은 SaaS 응용 프로그램을 업무에 사용하고 있음을 보여 주는 조사에 따른 것입니다. [Cloud App Security](https://technet.microsoft.com/library/mt657567.aspx)는 조직에서 사용 중인 모든 클라우드 응용 프로그램에 대한 자세한 개요를 제공합니다. 응용 프로그램에 액세스하는 모든 사용자와 IP 주소를 식별하며, 13,000개 이상의 클라우드 응용 프로그램에 대한 위험 평가를 수행하고, 60개가 넘는 매개 변수에 따라 각 응용 프로그램에 대한 자동화된 위험 점수를 제공합니다. 

1단계에 따라 사용자 환경에서 클라우드 응용 프로그램을 검색하고 이러한 응용 프로그램을 제어하는 정책을 구현합니다. 이 솔루션의 두 번째 단계에서는 데이터를 보호하고 분류하여 사용자의 실수와 데이터의 잘못된 사용을 완화하기 위해 [Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements)을 구현합니다.

### <a name="step-1-discover-cloud-apps-in-use-and-control-them-with-policy"></a>1단계: 사용 중인 클라우드 응용 프로그램 검색 및 정책을 통한 제어

Cloud App Security를 사용하기 위한 첫 번째 단계는 [응용 프로그램을 검색](https://technet.microsoft.com/library/mt657567.aspx)하는 것입니다. 이 단계를 건너뛰면 분석하고 정책을 사용하여 제한할 응용 프로그램이 없게 됩니다. 검색 프로세스를 시작하지 않은 경우 Cloud App Security 대시보드의 검색 옵션에 다음과 같은 메시지가 표시됩니다.

![사용자가 Cloud Discovery 로그를 아직 업로드하지 않았다는 메시지를 보여 주는 스크린샷](./media/protect-data-user-mistake/protect-data-user-mistake-fig2-1.png)

조직에서 사용 중인 응용 프로그램을 검색하는 것은 중요한 회사 데이터를 보호하기 위한 첫 번째 단계입니다. 검색 프로세스가 완료되면 [Cloud Discovery 대시보드](https://technet.microsoft.com/library/mt727946.aspx) 아래에 검색된 응용 프로그램 목록이 표시됩니다.

![Cloud Discovery 대시보드와 검색된 응용 프로그램 목록을 보여 주는 스크린샷](./media/protect-data-user-mistake/protect-data-user-mistake-fig3.png)

각 응용 프로그램에는 클라우드 응용 프로그램의 신뢰도와 안정성을 나타내는 점수가 있습니다. 응용 프로그램의 순위에 액세스하면 이 순위를 생성하는 데 사용된 세 가지 범주(일반, 보안 및 규정 준수)가 표시됩니다. 각 범주에는 검색 프로세스 중에 테스트된 특정 특성이 있습니다. 하나의 특성이 완전히 준수되지 않은 경우 부분으로 표시되며, 해당 특성의 세부 정보에 액세스하여 부분으로 표시된 이유를 파악할 수 있습니다.

!["HTTP 보안 헤더" 특성에 대한 세부 정보를 보여 주는 스크린샷](./media/protect-data-user-mistake/protect-data-user-mistake-fig4.png)

다음 단계는 검색된 응용 프로그램의 동작을 정책을 사용하여 제어하는 것입니다. 이 기능을 통해 IT 부서에서는 검색된 응용 프로그램 및 조직의 관련 위험 수준을 미세 조정할 수 있습니다. 여러 유형의 정책이 있습니다. 만들어야 하는 정책은 조직의 비즈니스 요구 사항에 따라 다릅니다. 기본적으로 변칙 검색 정책이 사용하도록 설정되어 있으므로 새 정책을 구성하지 않아도 됩니다. 그러나 기본 정책에서 경고를 생성할 변칙 유형을 미세 조정할 수 있습니다.

![만들 정책 유형을 선택하는 방법을 보여 주는 스크린샷](./media/protect-data-user-mistake/protect-data-user-mistake-fig5.png)

정책을 구성한 후에는 현재 정책에 대한 잠재적 위반을 조사할 수 있습니다. 이 특정 시나리오에서는 클라우드에서 공유되는 PII(개인적으로 식별이 가능한 정보)가 있는지 확인할 수 있습니다. 이 유형의 작업에 대한 정보는 파일 정책을 통해 사용할 수 있습니다. 필요한 파일 수준 정책은 PII 규정 준수 정책입니다. 이 정책의 목적은 공유되는 개인적으로 식별이 가능한 정보가 포함된 파일을 식별하고 조사 및 수정 옵션을 제공하는 것입니다.

![잠재적 위반에 대해 파일 정책 유형을 조사하는 방법을 보여 주는 스크린샷](./media/protect-data-user-mistake/protect-data-user-mistake-fig6.png)

이 예제의 경우 이 정책에 대한 세 가지 일치 항목이 있습니다. 즉, 이 정책과 일치하는 세 개의 파일이 있습니다. 각 파일을 클릭하여 파일 이름과 해당 위치를 조사할 수 있습니다.

### <a name="step-2-protect-data-on-premises-or-in-the-cloud"></a>2단계: 온-프레미스 및 클라우드에서 데이터 보호

이 솔루션을 구현하기 전에 [Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1)에 대한 요구 사항을 검토하세요.

Microsoft의 Azure Information Protection을 사용하면 데이터를 만들 때 데이터를 분류하고 레이블을 지정할 수 있습니다. 그런 다음 중요한 데이터에 보호(암호화+인증+사용 권한)를 적용할 수 있습니다. 분류 레이블과 보호는 영구적이므로 데이터와 함께 이동합니다. 따라서 저장된 위치 또는 공유 대상에 상관없이 항상 식별 가능하고 보호됩니다. 정보 보호 정책 및 레이블을 구현하려고 할 때 다음 지침을 따르세요.



- 민감도에 따라 데이터 분류
- 가장 중요한 데이터부터 시작
- IT 부서에서 자동 규칙을 설정할 수 있으며 사용자가 보완할 수 있음
- 시각적 표시 및 보호 등의 작업 연결

Azure Information Protection은 사용자 지정 가능한 기본 레이블과 함께 제공되지만 사용자의 Information Protection 표시줄에 표시되는 고유의 레이블 또는 하위 레이블을 사용자 지정하고 만들 수도 있습니다.

> [!NOTE]
> 레이블은 문서에 기록되는 메타데이터입니다. 레이블은 DLP 엔진과 같은 기타 시스템에서 읽을 수 있도록 일반 텍스트로 표시됩니다.

다음 예제에서는 Secret 레이블 아래에 생성된 사용자 지정 하위 레이블을 볼 수 있습니다.

!["Secret" 레이블 아래에 생성된 사용자 지정 하위 레이블을 보여 주는 스크린샷 ](./media/protect-data-user-mistake/protect-data-user-mistake-fig7.png)


레이블을 사용하는 방식(기본 또는 사용자 지정)을 정의한 후에는 [Rights Management 보호를 적용하도록 레이블을 구성](/azure/information-protection/configure-policy-protection#to-configure-a-label-to-apply-rights-management-protection)합니다.

Azure Information Protection을 사용하면 데이터 분류 및 보호 컨트롤이 Office 및 기타 일반 응용 프로그램에 통합됩니다. 이 통합에서는 사용자가 작업하는 데이터를 보호하기 위한 간단한 원클릭 옵션을 제공합니다. Azure Portal에서 관리자는 "신용 카드 번호" 또는 "주민등록번호"와 같은 미리 정의된 패턴을 자동 분류 조건으로 적용할 수 있습니다. 또는 텍스트 패턴 및 정규식을 사용하여 사용자 지정 문자열이나 패턴을 정의할 수 있습니다.

레이블에 대한 조건을 구성할 때 문서/메일에 자동으로 레이블을 할당하거나 사용자에게 권장하는 레이블을 선택하라는 메시지를 표시할 수 있습니다. 이 구성을 수행하는 방법에 대한 자세한 내용은 [Azure Information Protection에 대한 자동 및 권장 분류 조건을 구성하는 방법](https://docs.microsoft.com/rights-management/information-protection/configure-policy-classification)

> [!NOTE]
> 데이터 분류 및 보호에 대한 자세한 내용은 [분류, 레이블 지정 및 보호를 사용하여 데이터 보안 유지](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario)를 참조하세요.

## <a name="next-steps"></a>다음 단계

Microsoft Cloud App Security는 클라우드 응용 프로그램에서 작업 및 데이터를 검색하고 모니터링하며 제어하고 보호하기 위한 전체적인 솔루션을 제공합니다. Cloud App Security로 IT 관리자는 Azure Information Protection을 사용하여 Cloud App Security 콘솔에서 직접 암호화할 수 있습니다. Azure Information Protection과의 통합을 통해, 필요 시 SharePoint Online 및 비즈니스용 OneDrive에 저장된 파일에 대한 일반 보호를 적용할 수 있습니다. Cloud App Security 및 Azure Information Protection 간의 통합에 대한 자세한 내용은 [Azure Information Protection 통합](https://docs.microsoft.com/cloud-app-security/azip-integration)을 읽어보세요.
