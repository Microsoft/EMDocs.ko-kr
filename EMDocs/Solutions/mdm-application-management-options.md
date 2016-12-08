---
title: "응용 프로그램 관리 옵션"
description: "이 문서에서는 고객이 회사 소유 장치와 개인 장치(BYOD)에서 회사 데이터의 보안을 유지할 수 있도록 Intune 독립 실행형 및 하이브리드의 MAM(모바일 응용 프로그램 관리) 기능에 대해 설명합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 1f77eba2-8e27-4e08-b2f2-e71e3d776cf4
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 58270148fda3f3b3bb407055abff962ae86f1a14


---

# <a name="application-management-options"></a>응용 프로그램 관리 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

MAM(모바일 응용 프로그램 관리) 정책은 모바일 장치에서 회사 데이터가 소비자 앱이나 서비스에 유출되지 않도록 합니다. 일반적으로 이러한 정책은 모바일 관리 솔루션에 등록된 장치에서만 시행됩니다. 이제 다른 모바일 장치 관리 솔루션에서 관리되는 장치와, 장치 관리 시스템에 등록되지 않은 장치까지 포괄하도록 Intune의 MAM 기능이 확장되었습니다.

아래 그림에서 보듯 이미 MDM 솔루션을 갖추고 있다면 동시 사용 및 마이그레이션 시나리오에서, 직원 장치를 등록 해제한 다음 다시 Intune MDM에 등록할 필요 없이 Intune MAM이 Office 응용 프로그램과 Office 365 데이터의 관리 및 보호에 도움이 될 수 있습니다.

![Intune MAM 정책을 사용한 모바일 장치의 응용 프로그램 관리 분리 개요](./media/Intune_without_enrollment.png)

**Intune MAM 정책을 사용한 모바일 장치의 응용 프로그램 관리 분리 개요**

Intune MAM 기능은 전체 MDM 솔루션을 대체하는 것이 아닙니다. VPNm Wi-Fi, 인증서 관리, 응용 프로그램 배포 및 장치 수준 보안 설정 구성 등의 종합적인 장치 관리 시나리오에는 MDM 프로토콜이 필요합니다.

ConfigMgr 및 Intune이 있는 하이브리드 배포의 경우, Intune에서 관리하지 않는 장치에 있는 앱을 보호하는 데 모바일 앱 관리 정책을 사용할 수 있습니다. 이 새 기능을 사용하여 Office 365 서비스에 연결하는 앱에 대해 모바일 앱 관리 정책을 적용할 수 있습니다. 온-프레미스 Exchange 또는 SharePoint에 연결하는 앱에 대해서는 지원되지 않습니다. 이 기능을 사용하려면 Azure Preview 포털을 사용해야 합니다.

1단계의 질문에 대한 답변에 따라, 모바일 장치 관리 솔루션에서 응용 프로그램을 관리하는 방식을 결정할 수 있습니다. 아래 목록에서는 각 앱 관리 옵션의 장단점을 보여 줍니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

- Intune에 등록된 장치, 다른 관리 솔루션에 등록된 장치 또는 다른 관리 솔루션에 등록되지 않은 장치에서의 응용 프로그램 관리를 지원합니다.
- Intune에 적합한 앱 안에서 고객 개인 데이터로부터 회사 데이터를 격리합니다. 여기에는 Office Mobile 앱, Intune SDK에 맞게 조정된 타사 앱, Intune이 래핑한 기간 업무 앱 등이 포함됩니다.
- 회사 데이터를 잘라내기/복사/붙여넣기를 통해 회사 앱에 공유하면서, 회사 데이터가 개인 앱에 공유되지 않게 차단합니다.
- 앱별 PIN, 다른 이름으로 저장 제어, 앱 간 관리 데이터 공유 등과 같은 핵심 데이터 손실 방지 정책이 있습니다.
- Microsoft Word, Excel, PowerPoint, Outlook, OneNote 및 OneDrive for Business에서 이러한 기능을 지원합니다.
- 기업용 단체 구매 프로그램의 Apple Volume Purchase Program을 통해 구매한 iOS 앱을 관리합니다.
- Android, iOS 장치 및 Windows 10 장치(해당 기본 제공 기능인 [Windows 정보 보호](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip)를 통해)에서 지원됩니다.

## <a name="mdm-for-office-365"></a>Office 365용 MDM

- 현재 지원되지 않음

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점

**단점**

- Intune을 온-프레미스 ConfigMgr 인프라와 연결하기 위한 추가적인 구성 필요
- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성이 필요합니다.

Intune 및 ConfigMgr에 대해 다음을 검토하여 모바일 응용 프로그램 관리 옵션에 대한 자세한 내용을 확인합니다: Microsoft Intune 콘솔에서 모바일 응용 프로그램 관리 정책 구성 및 배포. 또한 Intune MAM 정책에 사용할 수 있는 Microsoft 앱의 목록과, Intune 호환 파트너 앱의 확장 목록도 확인합니다.



<!--HONumber=Nov16_HO4-->


