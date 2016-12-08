---
title: "메일 관리 옵션"
description: "이 문서에서는 Enterprise Mobility + Security를 사용하여 Microsoft 모바일 장치 관리 솔루션을 계획하고 디자인할 때 필요한 기존 메일 관리 옵션에 대한 지침을 제공합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9b89da63-039f-4831-b204-28c0681478fe
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: ac2c64b54883204f0051250c23f7a6b085e67ebe


---

# <a name="email-management-options"></a>메일 관리 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

모바일 장치 관리 솔루션을 구현하는 주요 이유는 일반적으로 모바일 장치에서 회사 메일에 대해 관리되는 액세스를 제공하기 위한 것입니다. 예를 들어 MDM for Office 365에서는 Exchange Online에서 호스트되는 메일 사서함에 대한 기본적인 관리되는 액세스를 제공하거나 Office 앱(iOS 및 Android)를 통해 액세스하는 [보안 정책](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx)을 만들 수 있습니다. 이 정책은 장치의 사용자 사서함 연결을 허용하기 전에 장치 암호 및 장치 암호화를 요구하는 등의 기본 모바일 장치 규정 준수 설정을 적용합니다.

비슷한 프로세스에 따라 Intune과 하이브리드 Intune 및 ConfigMgr 배포에서 메일 관리 옵션을 구성합니다. 주요 차이점은 MDM for Office 365에서 할 수 있는 것보다 더 많은 고급 메일 관리 옵션을 구현할 수 있다는 것입니다. 예를 들어 Intune 독립 실행형을 사용하여 Exchange Online 및 Exchange 온-프레미스 둘 다에 호스트되는 사서함 액세스를 허용하도록 조건부 메일 액세스를 구성하고 사용자 지정된 메일 프로필을 구성할 수 있습니다. Intune에서는 구성 및 규정 준수 정책을 사용하여 이러한 기능을 사용할 수 있도록 합니다.  하이브리드 Intune 및 ConfigMgr 배포에서는 Exchange Online에서 호스트되는 사서함에 대해서만 조건부 메일 액세스를 지원합니다.

아래의 그림 6에 표시된 시나리오에서 사용자는 Intune에 자신의 장치를 등록했으며 현재 Office 365 또는 Exchange 온-프레미스를 사용하여 회사 메일에 액세스하려고 합니다. 회사의 IT 관리자가 정의한 설정에 따라 Intune은 정책 확인 프로세스를 실행합니다. 이 시나리오에서는 장치가 암호화되거나, 암호가 설정되거나, 장치가 무단 해제 또는 루팅되지 않을 때 사용자의 액세스 권한이 부여됩니다. 사용자가 회사 메일에 액세스하려고 하며 해당 장치가 등록되지 않았거나 IT 관리자가 정의한 설정에 따라 규정을 준수하지 않을 경우 사용자에게 액세스가 차단된 이유와 문제 해결 방법에 대한 단계를 설명하는 메일이 제공됩니다. 

![조건부 액세스](./media/MDM_Figure_06.png)

**조건부 액세스**

1단계의 질문에 대한 답변은 모바일 장치 관리 솔루션에서 장치를 관리하는 방법을 결정하는 데 도움이 됩니다. 아래 목록에서는 각 MDM 솔루션에서 메일 관리의 장단점을 나열합니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

**장점**

- 모든 주요 모바일 장치 운영 체제(Android, iOS, Windows 10, Windows 8.x, 및 Windows Phone)에서 메일 관리 지원
- Exchange ActiveSync와의 통합을 통해 네이티브 모바일 장치 메일 응용 프로그램 활용 가능
- 서비스 간 커넥터를 통해 Exchange Online과 통합하여 Intune 및 Office 365 간에 크로스 플랫폼 모니터링 및 보고 허용
- 모바일 장치에서 Exchange ActiveSync 기반 설정을 관리하기 위해 메일 프로필 구성 지원
- 리소스에 대한 조건부 메일 액세스

**단점**

- Android 기반 모바일 장치의 경우 메일 프로필이 지원되지 않음

## <a name="mdm-for-office-365"></a>Office 365용 MDM

**장점**

- 암호, 암호화, 루팅된 장치 규정 준수에 대한 Exchange ActiveSync 지원 허용
- 장치 관리 정책을 허용하고 Office 및 비즈니스용 OneDrive 앱(iOS 및 Android)에 대한 액세스 권한을 부여하기 전에 장치 등록 요구
- 리소스에 대한 조건부 메일 액세스

**단점**

- 일부 고급 메일 관리 옵션이 지원되지 않음 
- 메일 프로필 배포가 지원되지 않음(iOS 제외)

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- Exchange Online과의 하이브리드 연결을 위한 Intune 온-프레미스 커넥터
- Exchange ActiveSync와의 통합(가장 엄격한 정책 설정 적용)
- 전자 메일 프로필
- Exchange Online으로 메일 액세스를 제한하는 조건부 액세스
- 서비스에 대한 액세스가 허용되기 위해 장치가 준수해야 하는 규칙과 설정을 정의하기 위한 규정 준수 정책
- 각 서비스에 대한 조건부 액세스 정책(보안 그룹, Intune 그룹 또는 등록 해제된 장치를 관리하는 방식에 대한 규칙 정의)

**단점**

- Exchange 온-프레미스에 호스트된 사서함이 아닌 Exchange Online에 호스트된 사서함에 대해서만 사용할 수 있는 메일에 대한 관리되는 액세스
- Exchange Online 및 Exchange 온-프레미스 둘 다에 대해 조건부 액세스를 사용하도록 설정하는 경우 서비스 간 커넥터를 구성하지 않아야 함

다음을 검토하여 모바일 장치 메일 구성 관리 옵션에 대한 세부 정보를 살펴봅니다.

- Intune: [메일 프로필](/Intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) 및 [조건부 메일 액세스를 사용하도록 설정](/Intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)하는 방법
- ConfigMgr: [메일 프로필](https://technet.microsoft.com/library/dn554227.aspx) 및 [조건부 메일 액세스](https://technet.microsoft.com/library/dn919655.aspx)를 사용하도록 설정
- MDM for Office 365: [모바일 장치 관리 기능](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)



<!--HONumber=Nov16_HO4-->


