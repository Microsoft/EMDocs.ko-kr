---
title: "장치 모니터링 옵션"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 23cfc12a-fa96-4fb3-8de1-af4569e8cb71
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: f543376b1e850c7d6e868c91d942aa8058e11b41


---

# 장치 모니터링 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

조직에서 관리되는 모든 모바일 장치의 상태 및 구성을 모니터링하고 이해하면 문제 및 규정 비준수를 검색하고 장치 인벤토리를 관리하는 데 도움이 됩니다. 하드웨어, 소프트웨어 및 규정 준수 상태에 대한 자세한 보고서가 없으면 장치 정책을 실제로 적용되고 제대로 작동되도록 할 수 없습니다. 사전 모니터링은 문제가 더 커지고 해결하는 데 드는 비용이 증가하기 전에 문제를 완화하는 데 도움이 됩니다.

[Intune](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune), [MDM for Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) 및 Intune과 ConfigMgr의 [하이브리드 배포](https://technet.microsoft.com/library/gg699377.aspx)에는 장치, 사용자 및 조직의 정책과 절차에 대한 준수 여부를 관리하는 데 도움이 되는 모니터링 및 보고 기능이 포함되어 있습니다. 사용자 지정된 보고서와 기본 제공 보고서를 함께 사용하여 다음과 같은 영역에서 모바일 장치 관리를 모니터링할 수 있습니다.

- 소프트웨어 업데이트 보고서
- 소프트웨어 인벤토리 보고서
- 하드웨어 인벤토리 보고서
- 라이선스 보고서
- 비규격 보고서

인프라 설정 방법에 따라 조직을 모니터링하는 데 도움이 되는 다양한 보고서를 만들 수 있습니다. Intune 기반 모니터링 및 보고 기능은 Intune 독립 실행형 배포뿐만 아니라 MDM for Office 365의 보고서를 위한 백본입니다. 또한 이러한 보고서는 하이브리드 배포에서 Intune에 연결될 때 ConfigMgr의 보고 기능과 긴밀하게 통합될 수 있습니다. 아래와 같이 각 제품에는 서로 다르지만 상호 보완적인 보고 기능이 있습니다. 각 모바일 장치 관리 솔루션의 보고 기능이 갖는 의미를 확인하면 필요한 보고서를 제공하는 솔루션을 선택하는 데 도움이 될 수 있습니다.

![통합 모바일 장치 모니터링 및 보고](./media/MDM_Figure_05.png)

**통합 모바일 장치 모니터링 및 보고**

작업 2의 질문에 답변한 내용은 모바일 장치에 대한 모니터링 및 보고 요구를 파악하는 데 도움이 될 수 있습니다. 아래 목록에서는 각 MDM 솔루션이 제공하는 모니터링 및 보고 기능의 장단점을 보여 줍니다.

## Intune(독립 실행형)

**장점**

- 모니터링 개요/대시보드
- 직접 관리되는 네트워크 장치에서 오류가 발견될 때 경고 발생
- Intune 서비스 RSS 피드가 서비스 및 향후 유지 관리 문제를 알릴 수 있음
- 임계값 및 메일 경고 알림이 있는 3가지 수준의 경고(심각, 경고, 정보)
- 장치 유형별로 경고를 필터링할 수 있음
- 관리되는 모든 장치의 상태를 검토할 수 있음
- IT 정책에 맞지 않는 장치에 대한 보고서 제공
- 다음과 같은 영역의 세부 정보를 모니터링할 수 있음
 - System (시스템)
 - OS
 - 저장소
 - Exchange ActiveSync
 - 시스템 엔클로저
 - Network (네트워크)
 - 서비스

**단점**

- 메일 경고만 제공하고 텍스트 기반 또는 음성 경고는 제공하지 않음

## Office 365용 MDM

**장점**

- 모니터링 개요/대시보드
- 임계값 및 메일 경고 알림이 있는 3가지 수준의 경고(심각, 경고, 정보)
- 장치 유형별로 경고를 필터링할 수 있음
- 관리되는 모든 장치의 상태를 검토할 수 있음
- IT 정책에 맞지 않는 장치에 대한 보고서 제공

**단점**

- 모바일 장치 규정 준수 상태 보고서 제공

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 모니터링 및 보고 기능과 다음 기능
 - 비 모바일 및 비 Intune 등록 장치를 포함하여 조직의 모든 장치에 대한 포괄적인 임계값 기반의 통합 모니터링 및 보고 기능
 - SQL SSRS(Server Reporting Services)의 고급 보고 기능과 Reporting Services 보고서 작성기가 제공하는 풍부한 제작 환경

**단점**

- Intune을 온-프레미스 ConfigMgr 인프라와 연결하기 위한 추가적인 구성이 필요합니다.
- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성이 필요합니다.

다음을 검토하여 모바일 장치 모니터링 옵션에 대한 세부 정보를 살펴봅니다.

- Intune: **[모바일 장치 모니터링](https://technet.microsoft.com/library/jj733634.aspx)** 및 [보고 기능 관리](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune) 방법
- ConfigMgr: [모바일 장치 모니터링](https://technet.microsoft.com/library/gg682128.aspx) 및 [보고 기능 관리](https://technet.microsoft.com/library/gg699377.aspx)
- MDM for Office 365: [개요 및 장치 관리 작업](https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx)


<!--HONumber=Jun16_HO4-->


