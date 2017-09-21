---
title: "Microsoft Intune - Microsoft 365 Enterprise를 사용하여 Office 365 ProPlus 배포 | Microsoft Docs"
description: "Microsoft Intune을 사용하여 Microsoft Office 365 ProPlus를 배포하는 방법에 대해 설명합니다."
author: jeffgilb
manager: femila
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/10/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: e631ca9282fc937279c7e2d639f1ecf509ceeab5
ms.sourcegitcommit: a5900174df584bee2f94086668cb0eff53bd5ed0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2017
---
# <a name="deploy-office-365-proplus-with-microsoft-intune"></a>Microsoft Intune을 사용하여 Office 365 ProPlus 배포
Microsoft 365 Enterprise는 누구나 창의적이 되고 안전하게 함께 일하게 해주는 최신 작업 공간 솔루션입니다. Microsoft 365 Enterprise 솔루션은 Enterprise Mobility + Security(EMS), Office 365 및 Windows 10 팀 간 긴밀한 협업의 결과입니다. 이 협업으로 Intune을 사용하여 Office 365 ProPlus 응용 프로그램을 Windows 10 장치에 배포하는 기능 같은 혁신적 솔루션이 탄생했습니다. 

이제 특정 Office 365 ProPlus 앱 선택(간편 실행 사용), Windows 10 Creators Update를 실행하는 등록된 장치에 앱 배포 및 Azure의 새 Intune 포털을 통해 배포 메트릭 보기가 훨씬 더 쉽습니다. 이 기능은 Windows AutoPilot에서 원활하게 작동하므로 Azure AD와 Intune이 백그라운드에서 함께 작동하여 장치 등록, 필요한 구성 배포 및 이제는 Office 365 ProPlus 앱 설치도 수행하는 동안 즉시 실행 환경(OOBE)에서 회사 자격 증명만 제공하면 직원의 장치에서 즉시 작동하도록 할 수 있습니다.

![Windows 10 관리 단순화 및 EMS를 사용하여 TCO 절감](./media/deploy-office-proplus-intune/windows-10-management-ems.png)

[여기서 이 인포그래픽을 다운로드](https://gallery.technet.microsoft.com/Infographic-Simplify-37e77674)할 수 있습니다.

## <a name="deploy-office-365-proplus-with-intune"></a>Intune을 사용하여 Office 365 ProPlus 배포 
Intune을 사용하여 Office 365 ProPlus 배포를 구성할 수 있는 방법을 살펴보겠습니다.

새 Intune Portal을 통해 Office 365 ProPlus 배포 추가 및 사용자 지정을 쉽게 했습니다. **Office 365 ProPlus Suite(Windows 10)** 앱 유형을 선택한 후 3단계 만에 간단히 Office 앱 배포를 사용자 지정할 수 있습니다.

먼저 최종 사용자 장치에 사용할 응용 프로그램을 선택합니다.

![배포할 응용 프로그램 선택](./media/deploy-office-proplus-intune/Configure-App-Suite.png)

그런 다음 응용 프로그램 패키지의 정보를 구성합니다. 예를 들어 이 패키지에서 Intune 회사 포털에 표시할 앱에 대한 간략한 설명을 추가하고자 할 수 있습니다.

![응용 프로그램 패키지 정보 구성](./media/deploy-office-proplus-intune/App-Suite-Information.png)

끝으로 시스템 아키텍처 또는 업데이트 채널 등 몇 가지 설치 설정을 구성합니다.

![설치 설정 구성](./media/deploy-office-proplus-intune/App-Suite-Settings.png)

최종 사용자가 Intune 회사 포털을 통해 Office 앱을 설치할 수 있도록 구성할 수 있습니다. 그렇지 않으면 사용자는 자동 설치만 이용할 수 있습니다. [Office는 서비스에 의해 자동으로 최신 상태로 유지되므로](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4) Office가 사용자의 장치에 설치된 후 사용자는 로그인하고 제품을 활성화한 후 최신 기능을 사용할 수 있습니다.

> [!NOTE]
> 현재 이 형태의 Office 365 ProPlus 배포는 Office 기존 버전이 설치되지 않은 장치에 대해서만 지원됩니다. Office 기존 버전이 설치된 장치의 경우 등록하기 전에 모든 Office 버전을 제거하는 것이 좋습니다. 우리는 기존 Office 배포를 가진 장치를 지원하는 미래의 기능 향상을 위해Windows 및 Office 팀과 협력하고 있습니다.

## <a name="learn-more"></a>자세한 정보
자세한 단계별 지침은 [Intune을 사용하여 Windows 10용 Office 365 앱 배포](https://docs.microsoft.com/intune/apps-add-office365)를 참조하세요.