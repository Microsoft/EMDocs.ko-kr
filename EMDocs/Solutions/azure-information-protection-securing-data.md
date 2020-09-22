---
title: 데이터 보안 유지에서 Azure Information Protection의 역할 | Microsoft 문서
description: 이 문서에서는 조직의 데이터 보안 유지에서 Azure Information Protection의 역할을 설명합니다.
author: yuridio
ms.author: mbaldwin
manager: barbkess
ms.date: 04/16/2019
ms.topic: conceptual
ms.service: rights-management
ms.reviewer: v-craic
ms.suite: ems
ms.openlocfilehash: 8ae48fabe638e41c3291396bcb9421fd00f11b69
ms.sourcegitcommit: 60e6e9ad2824e82b53e1ca5f55020e82d133db63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90989165"
---
# <a name="the-role-of-azure-information-protection-in-securing-data"></a>데이터 보안 유지에서 Azure Information Protection의 역할

[AIP(Azure Information Protection)](/azure/information-protection/what-is-information-protection)는 고객에게 데이터를 분류하고 데이터의 레이블을 지정하고 암호화를 사용하여 데이터를 보호하는 기능을 제공합니다. Azure Information Protection을 통해 IT 관리자는 다음과 같이 할 수 있습니다.

- 미리 설정된 규칙에 따라 메일 및 문서를 자동으로 분류
- 사용자 지정 머리글, 바닥글 및 워터마크와 같은 콘텐츠에 표식 추가
- 다음과 같은 기능을 제공하는 Rights Management로 회사의 기밀 파일 보호:
    - 공개 키 암호화에는 RSA 2048비트 키를 사용하고 작업 서명에는 SHA-256을 사용함
    - 조직 내부 및 외부의 특정 받는 사람 집합에 대해 파일 암호화
    - 특정 권한 집합을 적용하여 파일의 사용 가능성 제한    
    - 권한 정책의 사용자 ID 및 권한 부여에 따라 콘텐츠 암호 해독

이러한 기능을 통해 엔터프라이즈는 데이터에 대해 더 향상된 엔드투엔드 제어가 가능합니다. 이 컨텍스트에서 Azure Information Protection은 회사의 데이터 보안 유지에 중요한 역할을 합니다.

> [!IMPORTANT]
> Azure Information Protection 작동 방식에 대 한 자세한 내용은 [Azure RMS 어떻게 작동 하나요?를 참조 하세요. 내부적으로](/azure/information-protection/how-does-it-work)

## <a name="the-state-of-enterprise-protection-today"></a>현재 엔터프라이즈 보호 상태

현재 많은 엔터프라이즈에는 어떠한 보호 기술도 적용되어 있지 않아, 문서와 메일이 일반 텍스트로 공유되고 데이터 보유자는 권한 있는 콘텐츠에 대한 액세스 권한이 있는 사용자를 명확하게 지정하고 있지 않습니다. SMIME와 같은 보호 기술은 복잡하고 ACL은 반드시 메일 및 문서와 함께 이동하는 것은 아닙니다.

![문서 보호 없음](./media/azure-information-protection-securing-data/aip-securing-data-fig1.png)

대체로 보호되지 않는 환경에서 Azure Information Protection은 이전에는 사용할 수 없었던 보안 조치를 제공합니다. 또한 보안은 끊임없이 발전하는 문제이므로 어떠한 조직도 임의의 시점에 100% 보호를 주장할 수 없는 데 반하여, 제대로 배포된 경우 Azure Information Protection은 조직의 보안 공간을 증가시킵니다.

## <a name="security-principles-for-sharing-content"></a>콘텐츠 공유에 대한 보안 원칙

조직 내에서 Azure Information Protection을 사용할 경우 IT 관리자는 클라이언트 디바이스 및 사용자 ID 관리를 완벽하게 제어할 수 있으며 이를 통해 조직 내의 공유에 대한 적절한 신뢰 플랫폼이 구축됩니다. 조직 외부로 정보를 보내는 것은 본질적으로 신뢰도가 떨어집니다. 정보 보호 접근 방식에 대해 생각할 때 위험 평가를 수행해야 하는 몇 가지 원칙이 있습니다. 이 위험 평가를 수행하는 동안 다음 사항을 고려하세요.

- 받는 사람은 관리되지 않는 디바이스에 대한 물리적 액세스 권한이 있으며, 따라서 디바이스에서 발생하는 모든 일을 제어할 수 있습니다.
- 받는 사람은 비위장과 관련된 신뢰 수준으로 인증됩니다.

IT 관리자가 디바이스 또는 ID를 제어하지 상황에서는, IT에서 보호된 정보에 발생하는 일을 제어할 수 없습니다. 사용자가 보호된 정보를 인증하고 열면 더 이상 IT 관리자가 제어할 정보가 아니게 됩니다. 이때 IT 관리자는 콘텐츠에 배치된 정책을 따르는 받는 사람을 신뢰하고 있습니다.

보호된 콘텐츠에 액세스하는 권한이 있는 악의적인 외부 받는 사람을 완전히 막을 수는 없습니다. Azure Information Protection은 윤리적 경계를 설정하고 지원 애플리케이션을 사용하여 사용자가 문서에 액세스하는 방법에 대해 정직하게 하는 데 도움이 됩니다. Azure Information Protection은 ID를 기반으로 제공된, 정의된 액세스 경계 내에 암시적 신뢰가 있는 경우 유용합니다.

그러나 이후 액세스를 검색하고 완화하기는 더 간단합니다. Azure Information Protection 서비스의 문서 추적 기능은 액세스를 추적할 수 있으며 조직은 특정 문서에 대한 액세스 권한을 해지하거나 사용자의 액세스 권한을 해지하여 행동을 취할 수 있습니다.

콘텐츠가 매우 중요하고 조직에서 받는 사람을 신뢰할 수 없는 경우 콘텐츠의 추가 보안이 가장 중요합니다. 이 경우 보안을 위해 다이얼을 돌리고 문서에 액세스 제어를 배치하는 것이 좋습니다.

## <a name="identity-based-security"></a>ID 기반 보안

다음 섹션에서는 보호 된 콘텐츠에 대 한 공격의 세 가지 주요 시나리오와 환경 컨트롤과 Azure Information Protection의 조합을 사용 하 여 콘텐츠에 대 한 악의적인 액세스를 완화 하는 방법에 대해 설명 합니다.

### <a name="attacks-by-unauthorized-users"></a>권한이 없는 사용자의 공격

Azure Information Protection 보호 기능의 기본 사항은 보호된 콘텐츠에 대한 액세스를 인증된 ID 및 권한 부여를 기반으로 하는 것입니다. 즉, Azure Information Protection을 사용할 경우 *인증 안 함* 또는 *권한 부여 없음*은 *액세스 권한 없음*을 의미합니다. 이것이 Azure Information Protection을 배포하는 주된 이유이며, 이를 통해 엔터프라이즈는 무제한 액세스 상태에서 정보에 대한 액세스가 사용자 인증 및 권한 부여를 기반으로 하는 상태로 갈 수 있습니다.

이 Azure Information Protection 기능을 사용하여 엔터프라이즈는 정보를 구획화할 수 있습니다. 예를 들어 HR(인사) 부서의 중요한 정보를 부서 내에 격리해 두고, 재무 부서의 데이터를 재무 부서로 제한할 수 있습니다. Azure Information Protection은 *아무것도 기반하지 않는 것이 아니라 ID를 기반으로 한 액세스*를 제공합니다.

아래 다이어그램에는 문서를 Tom로 보내는 사용자 (Bob)의 예가 있습니다. 이 경우 Bob은 재무 부서 소속이며 Tom은 영업 부서 소속입니다. 권한이 부여되지 않은 경우 Tom은 문서에 액세스할 수 없습니다.

![액세스 권한 없음](./media/azure-information-protection-securing-data/aip-securing-data-fig2.png)

이 시나리오의 요점은 Azure Information Protection이 권한이 없는 사용자의 공격을 막을 수 있다는 점입니다. Azure Information Protection의 암호화 컨트롤에 대한 자세한 내용은 [Azure RMS에서 사용하는 암호화 컨트롤: 알고리즘 및 키 길이](/azure/information-protection/how-does-it-work)를 참조하세요.

### <a name="access-by-malicious-programs-on-behalf-of-users"></a>사용자를 대신하여 악성 프로그램에서 액세스

사용자를 대신하여 악성 프로그램에서 액세스하는 경우 일반적으로 사용자가 알지 못하는 어떤 일이 발생하는 것입니다. 트로이 목마, 바이러스 및 기타 맬웨어는 사용자를 대신 하 여 작동할 수 있는 악성 프로그램의 일반적인 예입니다. 이러한 프로그램이 사용자의 ID를 가장하거나 조치를 취할 수 있는 사용자의 권한을 활용할 수 있는 경우 [Azure Information Protection SDK](/azure/information-protection/develop/developers-guide)를 사용하여 자신도 모르는 사용자를 대신하여 콘텐츠 암호를 해독할 수 있습니다. 이 작업은 사용자의 컨텍스트에서 수행되므로 이 공격을 막는 간단한 방법은 없습니다.

![악성 프로그램](./media/azure-information-protection-securing-data/aip-securing-data-fig3.png)

여기서 의도는 사용자 ID의 보안을 향상하는 것이며, 이렇게 하면 Rogue 애플리케이션이 사용자의 ID를 하이재킹하는 기능을 완화하는 데 도움이 됩니다. Azure Active Directory는 사용자 ID의 보안을 유지하는 데 도움이 될 수 있는 몇 가지 솔루션을 제공합니다(예: 2단계 인증 사용). 또한 Azure Activity Directory ID 보호의 일부로 제공되며 사용자 ID의 보안을 유지하기 위해 탐색해야 하는 다른 기능도 있습니다.

ID 보안 유지는 Azure Information Protection의 범위를 벗어나며 관리자 책임 영역에 속합니다.

> [!IMPORTANT]
> 또한 악성 프로그램의 존재를 제거하려면 "관리되는" 환경에 초점을 두는 것도 중요합니다. 이 내용은 다음 시나리오에서 다룹니다.

### <a name="malicious-users-with-authorization"></a>권한 부여된 악의적인 사용자

악의적인 사용자의 액세스는 기본적으로 신뢰가 손상되었음을 의미합니다. 이 시나리오에서 조력자는 사용자의 권한을 에스컬레이션하기 위해 조작된 프로그램이어야 하는데, 이전 시나리오와 달리 이 사용자는 자발적으로 신뢰를 끊기 위한 자격 증명을 제공하기 때문입니다.

![악의적인 사용자](./media/azure-information-protection-securing-data/aip-securing-data-fig4.png)

Azure Information Protection은 애플리케이션이 문서와 연결된 권한을 적용하는 일을 담당하는 클라이언트 디바이스에 있게 하도록 설계되었습니다. 어쨌든 현재 보호된 콘텐츠의 보안에서 가장 약한 링크는 콘텐츠가 최종 사용자에게 일반 텍스트로 표시되는 클라이언트 디바이스에 있습니다. Microsoft Office와 같은 클라이언트 애플리케이션은 권한을 올바르게 적용하므로 악의적인 사용자가 이러한 애플리케이션을 사용하여 권한을 에스컬레이션할 수 없습니다. 그러나 동기가 부여된 공격자는 Azure Information Protection SDK를 사용하여 권한을 적용하지 않는 애플리케이션을 만들 수 있으며 이는 *악성 프로그램*의 본질입니다.

이 시나리오의 초점은 Rogue 애플리케이션이 사용될 수 없도록 클라이언트 디바이스 및 애플리케이션의 보안을 유지하는 데 있습니다. IT 관리자가 따를 수 있는 몇 가지 단계는 다음과 같습니다.

- [Windows AppLocker](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759117(v=ws.11))를 사용하여 사용자 동의 없이 설치된 프로그램이 실행될 수 없도록 합니다.
- [Intune](/intune/) 및 [Microsoft 끝점 Configuration Manager](/configmgr/) 를 사용 하 여 장치가 ' 정상 ' 상태가 되도록 합니다.
- 디바이스의 바이러스 백신이 최신 상태인지 확인합니다.
- 인증 및 [SSO](https://azure.microsoft.com/resources/videos/overview-of-single-sign-on/)에 [Microsoft Identity Brokers](/previous-versions/sql/sql-server-2008-r2/ms166045(v=sql.105))를 지원하는 애플리케이션을 사용합니다.

이 시나리오의 요점은 클라이언트 컴퓨터 및 애플리케이션의 보안 유지가 Azure Information Protection을 뒷받침하는 신뢰의 중요한 부분이라는 점입니다.

Azure Information Protection은 콘텐츠에 대한 액세스 권한이 부여된 사용자의 악의적인 오용을 방지하도록 설계되지 않았으므로 해당 사용자의 악의적인 수정에 대해 콘텐츠를 보호할 수 없습니다. 콘텐츠의 수정은 실제로 사용자가 처음에 보호된 데이터에 대한 액세스 권한을 부여받고 문서와 관련된 정책과 권한 자체는 적절한 서명 및 변조임이 요구되지만, 사용자에게 필요한 암호화/암호 해독 키에 대한 액세스 권한을 부여하면 사용자는 기술적으로 데이터를 해독하고, 수정하고, 다시 암호화할 수 있다고 가정할 수 있습니다. Microsoft 제품(예: Office 문서 서명 지원, Outlook의 s/MIME 지원) 내에서 및 타사로부터 Office 문서에 대한 문서 서명, 저자 증명, 변조 방지 및 부인 방지를 제공하기 위해 구현할 수 있는 많은 솔루션이 있습니다. 권한 있는 사용자의 악의적인 수정으로부터 보호하기 위해 AIP의 보호 기능에만 의존해서는 안됩니다. 

## <a name="summary"></a>요약

완벽한 보안은 한 가지 기술로 구현되는 것이 아닙니다. IT 관리자는 다양한 상호 종속적 방법을 통해 실제 환경에서 보호된 콘텐츠의 공격에 대한 취약성을 줄일 수 있습니다.

- **Azure Information Protection**: 콘텐츠에 대한 무단 액세스를 방지함
- **Microsoft Intune, Microsoft 끝점 Configuration Manager 및 기타 장치 관리 제품**: 악성 앱이 없는 관리 되 고 제어 되는 환경을 가능 하 게 합니다.
- **Windows AppLocker**: 악성 앱이 없는 관리되고 제어되는 환경을 가능하게 함
- **Azure AD ID 보호**: 사용자 ID의 신뢰를 향상함
- **EMS 조건부 액세스**: 디바이스 및 ID의 신뢰를 향상함