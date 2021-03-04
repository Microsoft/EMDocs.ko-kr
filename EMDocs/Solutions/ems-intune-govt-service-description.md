---
title: Microsoft Intune 정부 서비스 설명
description: Intune 정부 서비스 설명은 서비스 제공의 개요를 제공 하도록 설계 되었습니다.
keywords: ''
author: mlottner
ms.author: mlottner
manager: dougeby
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.suite: ems
ms.openlocfilehash: 83eab50cd4af65be5a28f3c0efaca7776ebd1fdb
ms.sourcegitcommit: 422f43a00933c66f17c85de243a1a3cf1a08cda2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "101831519"
---
# <a name="microsoft-intune-for-us-government-gcc-high-and-dod-service-description"></a>미국 정부 GCC High 및 DoD 서비스 설명에 대 한 Microsoft Intune

## <a name="how-to-use-this-service-description"></a>이 서비스 설명을 사용 하는 방법

Intune 미국 정부 서비스 설명은 GCC High 및 DoD 환경에서 서비스 제공에 대 한 개요를 제공 하도록 설계 되었으며, 상용 제품의 기능 변형을 다룹니다.

GCC 고객용 Intune에 대 한 자세한 내용은 [미국 정부 및 Microsoft 365 상호 운용성을 위한 EMS 제품](ems-govt-service-description.md#ems-offers-for-us-government-and-microsoft-365-interoperability)을 참조 하세요.

## <a name="get-started-with-intune-for-us-government-gcc-high-and-dod"></a>미국 정부 GCC High 및 DoD 용 Intune 시작

Intune GCC High 및 DoD 제품은 Microsoft Azure Government 클라우드에 빌드되고 Microsoft 365 GCC High 및 DoD 환경과 함께 작동 하도록 설계 되었습니다. 서비스 및 사용 방법에 대 한 자세한 내용은 [Intune 공개 문서](/intune/)를 참조 하세요. 공용 설명서를 사용 하 여 서비스를 배포 하 고 운영 하는 출발점으로 사용 하 고, GCC High 환경의 기능이 나 기능에서 제공 하는 다음과 같은 서비스 설명 세부 정보 및 변경 사항을 사용 해야 합니다.

### <a name="feature-variations-in-intune-gcc-high-and-dod"></a>Intune GCC High 및 DoD의 기능 변형

- GCC High 및 DoD 고객용 Intune은 독립 실행형 배포만 지원 합니다.
- GCC High 및 DoD 고객용 intune은 Intune 에이전트를 사용 하 여 레거시 PC 관리를 지원 하지 않습니다. Windows 10 관리는 최신 MDM 채널을 통해 지원됩니다.
- GCC High 및 DoD 고객용 Intune은 온-프레미스 Exchange Connector를 지원 하지 않습니다.
- Co-Management 지원은 Configuration Manager 버전 1906 이상 에서만 사용할 수 있습니다.
- 이번에는 Windows Autopilot 및 비즈니스 스토어 기능이 GCC High 및 DoD 고객에 게 제공 되지 않습니다. 계획은 진행 중입니다.
- GCC High 용 Intune은 macOS 장치에 대 한 Jamf Pro 및 Intune 통합을 지원 하지 않습니다.
- Intune for GCC High는 Android 및 iOS 장치용 모바일 위협 방어 커넥터를 지원 하지 않습니다.
- Microsoft 끝점 관리자 끝점 분석 및 Log Analytics 기능은 현재 미국 정부 고객에 게 제공 되지 않습니다.
- 지금은 미국 정부 클라우드 고객에 게 진단 설정 및 통합 문서를 사용할 수 없습니다.
- [Windows 구성 디자이너를 사용 하 여 windows 장치에 대 한 대량 등록](/mem/intune/enrollment/windows-bulk-enroll) 은 현재 GCC High에서 지원 되지 않습니다.
- Intune for GCC High는 [위치](/mem/intune/protect/use-network-locations) 기능을 지원 하지 않습니다.


## <a name="next-steps"></a>다음 단계
Intune에 대 한 자세한 정보 및 시작 방법에 대 한 자세한 내용은 [intune 공개 문서](/intune/index)를 참조 하세요.