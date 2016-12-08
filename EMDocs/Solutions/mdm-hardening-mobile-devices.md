---
title: "모바일 장치 보안 강화"
description: "이 문서에서는 모바일 장치 관리 시나리오에서 모바일 장치의 보안을 강화하기 위한 디자인 고려 사항을 제공합니다."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ade57c73-a8a2-497f-ad8d-5dfc3cba9e70
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 050d92824ad2616440d9d4b972a812be0ab5a14a


---

# <a name="hardening-mobile-devices"></a>모바일 장치 보안 강화

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

비즈니스 요구 사항에 따라 기능을 강화하기 위한 모바일 장치용 구성 기준을 만들 경우 사용 편의성과 보안 간에 균형을 유지해야 합니다. 매우 엄격한 보안 강화 템플릿은 직원에게 사용 편의성 및 액세스 문제를 초래할 수 있으므로 자신의 장치에서 회사 리소스에 액세스하여 생산성을 높이려는 사용자의 목적에 저해됩니다. 

또한 모든 모바일 장치 플랫폼에서 모든 보안 정책을 사용할 수 있는 것은 아닙니다. 조직의 모바일 장치 플랫폼을 허용하는 우선 순위와 장치 보안을 강화하기 위한 보안 규정 준수 요구 사항 간을 균형 있게 조율해야 합니다.
모바일 장치 보안 강화 방법 중 하나는 다른 보안 계층을 적용하는 것입니다. MDM 솔루션에 따라 각 계층에 사용할 수 있는 설정도 달라질 수 있습니다. 아래 그림은 이러한 계층화된 접근을 설정하는 방법의 예를 보여 줍니다.

![보안 계층](./media/MDM_Figure_12.png)

## <a name="different-areas-of-mobile-device-hardening"></a>다양한 영역의 모바일 장치 보안 강화

각 계층은 비즈니스 보안 요구 사항을 준수해야 하는 영역을 그룹화하는 데 사용할 수 있습니다. 예를 들어, 시스템 설정 보안을 강화하고 암호화를 구현하기 위한 전용 장치에 [보안 정책](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)을 배포하도록 Intune을 구성할 수 있습니다. 또한 이 정책을 통해 액세스 허용 목록을 만들어 모바일 장치에서 [규격 앱](https://technet.microsoft.com/library/dn818906.aspx)만 설치하도록 할 수 있습니다.

Windows 8.1 Enterprise를 실행하는 BYOD 장치에서 AppLocker를 사용하면 응용 프로그램 업데이트 후에도 지속되는 파일 경로, 해시 또는 속성을 기준으로 앱을 허용하거나 차단할 수 있습니다(예: 게시자 이름, 제품 이름, 파일 이름, 파일 버전). Windows 10에는 MDM 서버를 사용하여 AppLocker 규칙을 활성화할 수 있게 새 AppLocker 구성 서비스 공급자가 추가되었습니다. Windows 10의 이 새 기능에 대한 자세한 내용은 [AppLocker CSP](https://msdn.microsoft.com/library/windows/hardware/dn920019(v=vs.85).aspx)에서 확인합니다.

제어가 필요한 또 다른 부분은 사용자의 모바일 탐색 환경입니다. 관리되는 브라우저 정책에는 관리되는 브라우저의 사용자가 방문할 수 있는 웹 사이트를 제한하는 허용 또는 차단 목록을 포함합니다. Intune에서 이러한 정책을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune에서 관리 브라우저 정책을 사용하여 인터넷 액세스 관리](/intune/deploy-use/manage-internet-access-using-managed-browser-policies) 문서를 읽어보세요.

ConfigMgr 온-프레미스 하이브리드 환경에서는 [구성 기준](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)을 만들어, 관리되는 모바일 장치의 기본 보안 강화 상태를 설정할 수 있습니다. 모든 필수 설정을 포함하도록 이러한 기준을 사용자 지정한 후 모바일 장치에 배포할 수 있습니다. 규정 준수 설정 옵션은 모바일 장치 플랫폼마다 다르므로 [Configuration Manager의 모바일 장치에 대한 준수 설정](https://technet.microsoft.com/library/dn376523.aspx)에서 각각의 장치에 사용할 수 있는 옵션에 대한 자세한 내용을 읽어보세요.

[MDM for Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx)에도 다음 범주의 모바일 장치 보안 강화에 도움을 주는 여러 기능이 포함되어 있습니다.

- 보안
- 암호화
- 무단 해제
- 관리되는 메일 프로필

이러한 옵션을 강화하기 위한 보안 정책 설정 방법에 대한 자세한 내용은 [Office 365의 기본 제공 모바일 장치 관리 기능](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx) 문서를 읽어보세요.

모바일 장치 플랫폼의 보안을 강화하면 사용자가 보안을 침해하지 않으면서 모바일 장치를 사용할 수 있도록 하면서 회사 데이터를 보호할 수 있습니다. 아래 표를 참조하면 조직의 데이터 보안 강화 요구 사항에 가장 잘 맞는 MDM 옵션을 선택하는 데 도움이 될 것입니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

**장점**

- 등록된 장치에 암호화, 맬웨어, 앱, 이메일, 이메일 프로필, 탈옥, 시스템 및 보안 등에 대한 정책을 시행할 수 있습니다.
- 주요 모바일 장치 플랫폼(Android, iOS, Windows 10, Windows 8.x 및Windows Phone)에 대한 정책 배포를 지원합니다.

**단점**

- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 모바일 장치를 관리하는 데 사용할 수 있는 추가 관리 인터페이스가 제공됨
- 일부 모바일 플랫폼에서 일부 정책을 사용할 수 없음

## <a name="mdm-for-office-365"></a>Office 365용 MDM

**장점**

- 등록된 장치에 대해 암호화, 앱, 탈옥, 보안 등에 대한 정책을 적용할 수 있습니다.
- 주요 모바일 장치 플랫폼(Android, iOS, Windows 10, Windows 8.x 및Windows Phone)에 대한 정책 배포를 지원합니다.

**단점**

- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 모바일 장치를 관리하는 데 사용할 수 있는 추가 관리 인터페이스가 제공됨
- 일부 모바일 플랫폼에서 일부 정책을 사용할 수 없음
- Intune 만큼의 세분성 수준을 허용하지 않습니다.

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- 등록된 장치에 암호화, 맬웨어, 앱, 이메일, 이메일, 시스템, 보안 및 탈옥 등에 대한 정책을 시행할 수 있습니다.
- 주요 모바일 장치 플랫폼(Android, iOS, Windows 10, Windows 8.x 및Windows Phone)에 대한 정책 배포를 지원합니다.
- 클라우드 및 온-프레미스 장치에서 등록된 모바일 장치에 대한 단일 관리 콘솔

**단점**

- 회사에 최신 온-프레미스 ConfigMgr 인프라가 없는 경우 통합 전에 ConfigMgr의 계획, 설치 및 구성을 위한 리소스가 필요합니다.

>[!TIP] 
> [Microsoft Intune에 대한 모바일 장치 관리 정책 설정](https://technet.microsoft.com/library/dn913730.aspx)에서 Microsoft Intune 모바일 장치 보안 정책에서 구성할 수 있는 모바일 장치 관리 설정에 대해 자세히 읽어보세요. 



<!--HONumber=Nov16_HO4-->


