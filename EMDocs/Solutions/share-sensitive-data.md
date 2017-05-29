---
title: "내부 및 외부에서 중요한 데이터 공유 | Microsoft 문서"
description: "Enterprise Mobility + Security를 통해 Microsoft Azure Information Protection 기능을 활용하여 내부 및 외부에서 중요한 데이터를 공유하는 방법을 설명하는 시나리오입니다."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a996fbf8-ece4-40bc-b866-d4606c230027
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 3d84bbe6d252976e1a3152f65003787e37d408c8
ms.contentlocale: ko-kr
ms.lasthandoff: 05/29/2017


---

# <a name="share-sensitive-data-internally-and-externally"></a>내부 및 외부에서 중요한 데이터 공유

많은 데이터 위반이 사이버 공격으로 인해 발생하지만 전문가들은 그보다 훨씬 많은 데이터 위반이 사람의 실수, 즉 직원이 중요한 비즈니스 데이터를 실수로 유출한 결과에서 비롯된다는 점에 동의합니다. 올바른 보안 정보 및 데이터 손실 방지 프로토콜을 갖추고 있다면 이러한 종류의 위반을 거의 모두 방지할 수 있습니다.

기업과 사용자에게 데이터 공유는 불가피하고 필요하지만 이로 인해 “다른 사람과 공유하는 데이터의 유출을 최소화하면서 여러 장치 간에 데이터 공유를 지원하는 방법”이라는 업계에서 가장 중대한 과제 중 하나가 발생합니다. 중요한 데이터를 파트너, 고객 등 외부 소스와 공유해야 하는 경우 위협 환경은 훨씬 광범위해집니다.

![다이어그램](./media/share-sensitive-data/share-sensitive-data-fig1.png)

이 컨텍스트에서는 일반적으로 비즈니스에 맞게 보안 프로토콜을 조정하고 데이터 분류 및 보호 프로세스에서 최종 사용자 동작에 영향을 주는 동시에 직원이 데이터 사일로에서 내부적으로 공동 작업하고 타사 공급업체와 외부적으로 공동 작업하도록 지원해야 프로젝트가 있습니다.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?

EMS(Enterprise Mobility + Security)는 ID, 장치, 앱, 데이터 등의 4단계 보호 기능으로 장치뿐 아니라 그 이상에서 기업 데이터를 기본적으로 보호하는 유일한 포괄적인 클라우드 솔루션입니다. EMS는 모바일 우선, 클라우드 우선 환경의 핵심 과제 중 하나인, 업무 중인 직원에게 보안 전자 메일을 제공하는 문제를 해결하도록 도와줍니다. EMS를 사용하면 직원들이 조직 내외부에서 안전하게 공동 작업을 수행할 수 있습니다. EMS를 사용하면 IT 관리자가 [Azure 권한 관리](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) 정책 템플릿을 사용하여 사용 현황을 전자 메일로 보낼 수 있습니다. 사용 권한은 온라인 및 오프라인뿐 아니라 조직 방화벽의 내부 및 외부에서도 보호가 이루어지도록 메시지 자체에 연결됩니다.

## <a name="recommended-solution"></a>권장 솔루션

Azure 권한 관리를 Exchange Online의 권한 관리와 통합하면 EMS에서 전자 메일을 통해 조직에서 나가는 데이터를 보호할 수 있습니다. 온-프레미스에 있는 Exchange Server와 Exchange Online(Office 365)에 대해 이 솔루션을 구현할 수 있습니다. 정보 권한 관리와 [Office 365 메시지 암호화](https://technet.microsoft.com/library/dn569285.aspx) 둘 다 정책을 기반으로 하며, Exchange 전송 규칙 엔진과 함께 작동하도록 설계되었습니다. 따라서 Microsoft Azure Rights Management를 사용하면 한 번의 작업으로 복잡한 정책 제한 사항을 쉽게 설정할 수 있습니다.

이 솔루션에서 제공되는 일부 기능에 대한 설명은 다음과 같습니다.

- 전자 메일 메시지에 여러 IRM 옵션을 적용하여 무단 액세스로부터 전자 메일을 보호하도록 도와줍니다.
- Office Online을 사용하여 파일을 보든 로컬 컴퓨터에 파일을 다운로드하든 상관없이 파일이 보호되므로 온라인 또는 오프라인에서 정보를 안전하게 유지하도록 도와줍니다.
- 모든 Office 문서와 원활하게 통합되므로 조직의 지적 재산을 보호하도록 도와줍니다.
- 기본 권한 관리 서비스 템플릿 외에 비즈니스 요구 사항에 따라 사용자 지정 템플릿을 적용합니다.


## <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법

Azure RMS를 지원하도록 Exchange Online을 구성하려면 Exchange Online에 대해 IRM(정보 권한 관리) 서비스를 구성해야 합니다. 다음 단계에 따라 이 솔루션을 구현할 수 있습니다.

1. Exchange와의 통합:
    - Exchange Online: Exchange Online에서 Azure RMS 사용
    - Exchange 온-프레미스: Azure 권한 관리 커넥터 배포
2. Exchange를 사용하여 보호된 Office 문서 보내기

## <a name="how-to-share-sensitive-data-internally-and-externally"></a>내부 및 외부에서 중요한 데이터를 공유하는 방법

기업은 비즈니스에 맞게 보안 프로토콜을 조정하고 데이터 분류 및 보호 프로세스에서 최종 사용자 동작에 영향을 주는 동시에 직원이 데이터 사일로에서 내부적으로 공동 작업하고 타사 공급업체와 외부적으로 공동 작업하도록 지원해야 합니다. 데이터 공유는 이 프로세스의 중요한 부분이 되며, 조직에서는 데이터 개인 정보 보호 및 무결성이 손상될 가능성을 줄이면서 이를 지원해야 합니다.

### <a name="step-1-integration-with-exchange"></a>1단계: Exchange와의 통합

권한 관리 보호는 Azure 권한 관리 정책 템플릿을 전자 메일 메시지에 적용함으로써 전자 메일에 적용됩니다. 이 통합을 지원하는 첫 번째 단계는 Exchange의 위치(클라우드(Exchange Online) 또는 온-프레미스)에 따라 다릅니다.

#### <a name="enable-rights-management-integration-with-exchange-online"></a>Exchange Online과의 권한 관리 통합 지원

Azure RMS를 지원하도록 Exchange Online을 구성하려면 Exchange Online에 대해 IRM(정보 권한 관리) 서비스를 구성해야 합니다. [Office 365: 클라이언트 및 온라인 서비스 구성](https://docs.microsoft.com/rights-management/deploy-use/configure-office365) 문서의 [Exchange Online: IRM 구성](https://docs.microsoft.com/rights-management/deploy-use/configure-office365#exchange-online-irm-configuration) 섹션에 설명된 단계에 따라 IRM에 대해 Exchange Online을 구성합니다.

마지막 단계는 구성의 유효성을 검사하는 최종 테스트여야 하며, 다음 화면에 표시된 것과 유사한 결과가 나타나야 합니다.

![PowerShell](./media/share-sensitive-data/share-sensitive-data-fig2.png)

#### <a name="enable-rights-management-integration-with-exchange-on-premises"></a>Exchange 온-프레미스와의 권한 관리 통합 지원

Exchange 온-프레미스와의 권한 관리 통합을 구성하려면 Microsoft Rights Management(RMS) 커넥터를 구성해야 합니다. 이 커넥터를 통해 기존 온-프레미스 Exchange Server가 클라우드 기반 Microsoft Rights Management 서비스(Azure RMS)에서 IRM(정보 권한 관리) 기능을 사용하도록 할 수 있습니다. 하이브리드 시나리오에서 일부 사용자가 온라인 서비스에 연결하더라도 이 커넥터를 사용할 수 있습니다.

[RMS 커넥터를 설치하기 위한 필수 구성 요소](https://docs.microsoft.com/rights-management/deploy-use/deploy-rms-connector#prerequisites-for-the-rms-connector)를 검토하고 [Azure 권한 관리 커넥터 설치 및 구성](https://docs.microsoft.com/rights-management/deploy-use/install-configure-rms-connector) 문서에 설명된 5가지 단계를 따릅니다.

### <a name="step-2-send-a-protected-document-using-exchange"></a>2단계: Exchange를 사용하여 보호된 문서 보내기

[분류 및 레이블 지정을 사용하여 데이터 보호](infoprotect-secure-classify-scenario.md) 시나리오의 3단계에 따라 RMS 공유 응용 프로그램을 설치합니다. 여러 유형의 클라이언트를 지원해야 하는 경우 [Rights Management 공유 응용 프로그램: 클라이언트 설치 및 구성](https://docs.microsoft.com/rights-management/deploy-use/configure-sharing-app) 문서에서 RMS 공유 응용 프로그램 설치 방법에 대한 자세한 내용을 검토합니다.

Office 문서를 공유하려면(예: Word에서 직접) 다음 이미지에 표시된 대로 리본 메뉴에 있는 보호된 항목 공유 아이콘을 사용하면 됩니다.

![ShareProtect](./media/share-sensitive-data/share-sensitive-data-fig3.png)

이 옵션을 클릭하면 다음 이미지에 표시된 대로 이 문서를 공유할 방법에 대한 자세한 정보가 포함된 보호된 항목 공유 대화 상자가 나타납니다.

![공유](./media/share-sensitive-data/share-sensitive-data-fig4.png)

이 창의 위쪽에서 대상 사용자의 전자 메일을 입력하고 이 사용자에게 제공할 액세스 유형을 선택합니다. 이 창의 아래쪽에서 문서의 만료 날짜를 제어할 수 있으며, 다른 사람이 이 문서를 열려고 할 때마다 전자 메일을 수신하는 옵션을 사용하도록 설정할 수 있습니다. 적절한 항목을 선택한 후 보내기를 클릭하면 다음 화면에 표시된 대로 Outlook에서 새 메시지가 열립니다.

![전자 메일](./media/share-sensitive-data/share-sensitive-data-fig5.png)

> [!IMPORTANT]
> 이 시나리오에 대한 자세한 내용은 Microsoft Ignite에서 [Azure Information Protection을 사용하여 안전하게 공동 작업](https://myignite.microsoft.com/videos/49947) 프레젠테이션을 참조하세요.

