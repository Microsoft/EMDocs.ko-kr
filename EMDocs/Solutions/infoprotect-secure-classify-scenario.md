---
title: "분류, 레이블 지정 및 보호를 사용하여 데이터 보안 유지 | Microsoft 문서"
description: "Enterprise Mobility + Security에서 Microsoft Azure Information Protection 기능을 활용하여 어떻게 데이터를 분류하고, 레이블을 지정하고, 보호할 수 있는지를 설명하는 시나리오."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/17
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 65409d5c-4f1b-4026-86e9-e65e1c4fe2b4
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 98bedbc50843cb7cfc284f5f29d40ca8b298f11a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="secure-data-using-classification-labeling-and-protection"></a>분류, 레이블 지정 및 보호를 사용하여 데이터 보안 유지

오늘날 조직 경계를 너머 여러 장치를 통해 정보 공유가 진행되고 있습니다.  사용자들이 업무 수행에 중요한 데이터를 안전하게 공유할 수 있도록 하면서 이러한 프로세스 중에 중요한 회사 데이터가 노출되지 않도록 하는 것이 매우 중요합니다. 아웃소싱과 같은 추세가 늘어나면서 계약업체 및 공급업체와 회사 기밀 데이터를 공유해야 할 수 있습니다. 모든 콘텐츠에 동일한 보호가 필요한 것은 아니므로 기업은 보호가 필요한 데이터와 그렇지 않은 데이터를 식별해야 합니다.

Enterprise Mobility + Security로 어떻게 이 시나리오를 해결할 수 있는지 자세히 알아보세요.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?

EMS(Enterprise Mobility + Security)는 ID, 장치, 앱, 데이터 등의 4단계 보호 기능으로 장치뿐 아니라 그 이상에서 기업 데이터를 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS는 모바일 중심, 클라우드 중심 환경의 핵심 과제 중 하나인, 업무 중인 직원에게 보안 데이터를 제공하는 문제를 해결해 줍니다. EMS를 사용하면 직원들이 조직 내외부에서 안전하게 공동 작업을 수행할 수 있습니다. IT 관리자는 EMS를 통해 Azure Information Protection을 활용하여 파일 수준에서 회사 데이터의 보안을 유지할 수 있습니다. 이 기능을 사용하여 저장 위치, 공유 대상, 데이터가 정지 상태인지 전송 중인지에 관계없이, 항상 보호되도록 할 수 있습니다.

## <a name="recommended-solution"></a>권장 솔루션

Azure Information Protection을 사용하여 조직에서는 데이터 생성 또는 수정 시에 데이터를 분류하고 레이블을 지정하고 보호할 수 있습니다. 사용자는 Azure Information Protection을 사용하여 다음을 수행할 수 있습니다.

- 민감도를 기준으로 데이터를 분류하고 수동 또는 자동으로 레이블 추가
- 암호화, 인증 및 사용 권한을 사용하여 데이터 보호
- 최종 사용자를 위한 직관적이고 비침입성 환경 설정

또한 조직에서는 공유 데이터에서 발생하는 현상을 파악하여 보다 잘 관리할 수 있도록 자세한 추적 및 보고 기능에 액세스할 수 있습니다. 다음 다이어그램에서는 정보 보호 수명 주기를 요약해서 보여 줍니다.

![정보 보호 수명 주기](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig1.png)

아래의 짧은 동영상을 통해 외근 중에도 Azure Information Protection을 통해 더욱 간단하게 정보를 분류하고 레이블 지정하고 보호하는 방법을 간단히 알아보세요.

<iframe src="https://channel9.msdn.com/Shows/Mechanics/An-Introduction-to-Microsoft-Azure-Information-Protection/player" width="560" height="315" allowFullScreen frameBorder="0"></iframe>

## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

다음 단계에 따라 Azure Information Protection을 사용하여 데이터 분류, 레이블 지정 및 보호를 구현하세요.

- 1단계: 데이터 분류 및 보호 준비
- 2단계: 정보 보호 정책 및 레이블 구성
- 3단계: 콘텐츠 기반 자동 분류 구현
- 4단계: 자동 및 권장 분류의 조건 구성

## <a name="how-to-secure-data-using-classification-labeling-and-protection-with-azure-information-protection"></a>Azure Information Protection에서 분류, 레이블 지정 및 보호를 사용하여 데이터를 보호하는 방법

회사는 보호해야 할 데이터와 보호할 필요가 없는 데이터를 구별해야 합니다. 다음 단계에서는 IT 부서에서 Azure Information Protection을 구현하도록 지원하기 위해 필요한 핵심 작업을 안내합니다.

### <a name="step-1-preparing-for-document-protection-and-content-classification"></a>1단계: 문서 보호 및 콘텐츠 분류 준비

이 솔루션을 구현하기 전에 [Azure Information Protection에 대한 요구 사항](/information-protection/get-started/requirements)을 검토하고 Azure Rights Management가 활성화되어 있는지 확인합니다. 활성화되면 Azure Portal에 다음과 같은 화면이 표시됩니다.

![Azure 포털](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig2.png)

Azure Rights Management를 활성화하면 이 정보 보호 솔루션이 지원하는 응용 프로그램 및 서비스를 사용하여 중요한 데이터를 보호할 수 있습니다. 또한 조직에서 소유한 보호된 파일 및 메일을 관리하고 모니터링할 수 있습니다. Office, SharePoint 및 Exchange 내에서 Rights Management 기능을 사용하여 중요한 파일이나 기밀 파일을 보호하려면 먼저 Azure Rights Management를 활성화해야 합니다.

### <a name="step-2-configure-information-protection-policies-and-labels"></a>2단계: 정보 보호 정책 및 레이블 구성

정보 보호 정책 및 레이블을 구현하려고 할 때 다음 지침을 따르세요.

- 민감도에 따라 데이터 분류
- 가장 중요한 데이터부터 시작
- IT 부서에서 자동 규칙을 설정할 수 있으며 사용자가 구현할 수 있음
- 시각적 표시 및 보호 등의 작업 연결

다음 다이어그램은 이러한 지침을 구현하는 방법의 예제를 보여 줍니다.

![분류](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig3.png)

Azure Information Protection은 사용자 지정 가능한 기본 레이블과 함께 제공되지만 사용자의 Information Protection 표시줄에 표시되는 고유의 레이블 또는 하위 레이블을 [사용자 지정](/information-protection/deploy-use/configure-policy-new-label)하고 만들 수도 있습니다.

> [!IMPORTANT]
> 레이블은 문서에 기록되는 메타데이터입니다. 레이블은 DLP 엔진과 같은 기타 시스템에서 읽을 수 있도록 일반 텍스트로 표시됩니다.

다음 예제에서는 **Secret** 레이블 아래에서 생성된 사용자 지정 하위 레이블을 볼 수 있습니다.

![Label](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig4.png)

레이블을 사용하는 방식(기본 또는 사용자 지정)을 정의한 후에는 [Rights Management 보호를 적용하도록 레이블을 구성](/information-protection/deploy-use/configure-policy-new-label)합니다.

### <a name="step-3-implement-content-based-automatic-classification"></a>3단계: 콘텐츠 기반 자동 분류 구현

Azure Information Protection을 사용하면 데이터 분류 및 보호 컨트롤이 Office 및 기타 일반 응용 프로그램에 통합됩니다. 이 통합에서는 사용자가 작업하는 데이터를 보호하기 위한 간단한 원클릭 옵션을 제공합니다. Azure Portal에서 "신용 카드 번호" 또는 "주민등록번호"와 같은 미리 정의된 패턴을 자동 분류 조건으로 적용할 수 있습니다. 또는 텍스트 패턴 및 정규식을 사용하여 사용자 지정 문자열이나 패턴을 정의할 수 있습니다.

레이블에 대한 조건을 구성할 때 문서/메일에 자동으로 레이블을 할당하거나 사용자에게 권장하는 레이블을 선택하라는 메시지를 표시할 수 있습니다. 이 구성을 수행하는 방법에 대한 자세한 내용은 [Azure Information Protection에 대한 자동 및 권장 분류 조건을 구성하는 방법](/information-protection/deploy-use/configure-policy-classification)


### <a name="step-4-configure-conditions-for-automatic-and-recommended-classification"></a>4단계: 자동 및 권장 분류의 조건 구성

IT 관리자는 데이터에 분류 및 보호를 자동으로 적용하기 위한 정책을 설정할 수 있습니다. 정책이 작업 중인 콘텐츠를 기준으로 적용될 수도 있으며 추천 분류를 선택하라는 메시지를 표시하도록 구성될 수도 있습니다. 기본 제공 조건 목록:

- SWIFT 코드
- 신용 카드 번호
- ABA 라우팅 번호
- 주민등록번호
- IBAN(국제 은행 계좌 번호)

이러한 유형의 구현에 대한 자세한 내용은 [기본 제공 조건에 대한 정보](/information-protection/deploy-use/configure-policy-classification#information-about-the-built-in-conditions)를 참조하세요.
