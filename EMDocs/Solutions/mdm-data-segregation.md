---
title: "데이터 분리"
description: "이 문서에서는 모바일 장치 관리 시나리오에 사용 해야 하는 데이터 분리에 대한 다양한 디자인 고려 사항을 제공합니다."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 50bd37fe-30b5-4a45-9c36-0b907dd13cc2
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: ffed65ca17663ac0e2ff758318bbf6f0e1540b57
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="data-segregation"></a>데이터 분리

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

데이터 분리는 조직을 위해서만 아니라 사용자의 개인 정보를 비공개로 유지하려는 경우에도 중요합니다. 데이터 분리를 사용하면 사용자의 개인 데이터에 영향을 주지 않으면서 사용자 소유의 장치에서 모든 회사 앱 및 데이터를 제거하는 데 도움이 됩니다(아래 그림 참조).

![데이터 분리](./media/MDM_Figure_10.png)

## <a name="users-personal-data-is-isolated-from-companys-data"></a>사용자의 개인 데이터가 회사 데이터에서 격리됨

MDM 솔루션을 통해 배포된 모든 앱, 회사 데이터 및 정책을 별도로 유지하면 선택적 초기화를 사용해서 사용자의 개인 콘텐츠 및 앱에 영향을 주지 않으면서 필요할 때 장치에서 제거할 수 있습니다.

>[!TIP]
> 원격 초기화가 iOS 및 Android 등의 다른 플랫폼에서 작동하는 방식에 대한 자세한 내용을 보려면 [Microsoft Intune을 사용하여 전체 또는 선택적 초기화를 통해 데이터 보호 지원](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)을 읽어보세요.

모바일 장치 데이터 관리를 위한 선택적 초기화는 Windows Server 2012 R2 및 Windows 8.1에 포함되어 있습니다. 이 기능은 Exchange Server 및 Microsoft Intune 관리자가 장치의 엔터프라이즈 데이터를 관리하고 [Windows 선택적 초기화](https://technet.microsoft.com/library/dn486874.aspx) 기능을 사용할 수 있는 앱을 개발하는 데 도움이 되는 리소스를 연결하는 방식으로 작동합니다.  Windows Phone 8 이상에서는 내부 저장소에서의 데이터 분리를 지원합니다.

![데이터 분리](./media/MDM_Figure_11.png)

[Windows Phone 8.1 보안 개요](http://www.microsoft.com/download/details.aspx?id=42509)를 다운로드하여 Windows Phone 8.1 보안 기능에 대해 자세히 읽어보세요.

사용자가 모바일 장치에서 개인 계정과 회사 계정 간을 전환할 경우 데이터를 분리하기 어려울 수 있습니다. BYOD 시나리오에서는 일반적으로 사용자가 여러 자격 증명을 사용하여 장치에서 여러 다른 작업을 수행할 수 있습니다.

엔터프라이즈 데이터 보호(EDP)는 데이터 분리를 제공하지만, 컨테이너를 사용하거나 비즈니스 데이터 액세스를 위한 특수 앱 버전이나 개인 데이터 액세스를 위한 별도의 인스턴스를 요구하지 않습니다. 개인 및 비즈니스 데이터의 물리적 구분을 위한 컨테이너, 파티션 또는 특수 폴더가 없습니다. 대신 Windows 10 Mobile이 액세스 제어 중개 역할을 하며 기업에 대해 암호화되어 있는 엔터프라이즈 데이터를 식별합니다.

EDP는 엔터프라이즈 데이터를 암호화하므로 데이터 분리를 제공합니다. 자세한 내용은 [엔터프라이즈 데이터 보호(EDP) 개요](https://technet.microsoft.com/library/dn985838.aspx)를 읽어보세요. Intune EDP 정책은 EDP, 엔터프라이즈 네트워크 위치, 보호 수준 및 암호화 설정으로 보호되는 앱 목록을 관리합니다.

사용자가 Intune 관리 장치에서 여러 ID를 지원하는 앱(예: Outlook)을 설치하고 로그인하면 Intune에서는 사용되는 계정이 장치의 관리되는 계정과 일치하는지 확인합니다. 계정이 관리되고 앱 및 사용자에 대한 정책이 있으면 정책 설정이 해당 계정의 데이터를 보호합니다. 사용자가 앱에 추가하는 개인 계정은 Intune 관리 및 보호를 벗어납니다. 따라서 회사 보호 수준을 그대로 유지하면서 개인적으로 응용 프로그램을 사용할 수 있습니다. Intune의 다중 ID 기능에 대한 자세한 내용은 [Microsoft Intune을 통해 모바일 응용 프로그램 관리 정책을 사용하여 데이터 보호](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)를 읽어보세요.

아래 표에서는 다양한 MDM 솔루션에서 사용할 수 있는 선택적 초기화 기능을 비교하여 조직의 데이터 분리 요구 사항에 가장 잘 맞는 MDM 솔루션을 선택하는 데 도움을 줍니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

**장점**

- 선택적 지우기를 수행하여 모바일 장치에 있는 회사 데이터만 제거할 수 있음
- 공장 재설정을 수행하고 모바일 장치를 완전히 초기화할 수 있음
- 다중 ID 앱 지원

**단점**

- 모바일 장치 저장소용 네이티브 암호화를 포함하지 않음
- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 사용할 수 있는 추가 관리 인터페이스가 제공됨

## <a name="office-365-with-mdm"></a>MDM 포함 Office 365

**장점**

- 공장 재설정을 수행하고 Android, Windows Phone 및 iOS 장치를 완전히 초기화할 수 있음
- Android, Windows Phone 및 iOS 장치에서 선택적 지우기를 수행하여 모바일 장치에서 회사 데이터만 제거할 수 있음

**단점**

- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 사용할 수 있는 추가 관리 인터페이스가 제공됨

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- 선택적 지우기를 수행하여 모바일 장치에서 회사 데이터만 제거할 수 있음
- 공장 재설정을 수행하고 모바일 장치를 완전히 초기화할 수 있음
- 다중 ID 앱 지원
- 단일 관리 콘솔을 통해 클라우드 기반 및 온-프레미스 모바일 장치 관리

**단점**

- 조직에 최신 온-프레미스 ConfigMgr 인프라가 없는 경우 통합 전에 이 플랫폼의 계획, 설치 및 구성 필요

각 모바일 장치 플랫폼에 대한 선택적 초기화 후에 데이터 제거되고 유지되는 방식을 이해하려면 [Microsoft Intune을 사용하여 전체 또는 선택적 초기화를 통해 데이터 보호 지원](/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune) 문서를 읽어보세요. 하이브리드 환경인 경우 ConfigMgr가 이 작업을 수행하는 데 어떻게 도움이 되는지 확인하려면 [Configuration Manager를 사용하여 모바일 장치를 원격으로 초기화하는 방법](https://technet.microsoft.com/library/dn956981.aspx) 문서를 읽어보세요.
