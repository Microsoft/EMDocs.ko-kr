---
title: "SaaS 모바일 장치 관리 전략 개발"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b3cefcc5-b045-48f9-91f5-6d282a4428f3
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b77c2b49180c3871a1885d8faa232b412bac384
ms.openlocfilehash: 29a71aed55e7b92626443caa5536928d42458b49


---

# SaaS 모바일 장치 관리 전략 개발

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

## SaaS 솔루션 요구 사항 확인

작업 1의 질문에 대한 답변에 따라, 모바일 장치 관리 솔루션에서 SaaS 솔루션이 지원해야 하는 대상을 결정할 수 있습니다. 아래의 표 20은 각 SaaS 솔루션 시나리오의 장단점을 이해하는 데 도움이 됩니다.

## Intune(독립 실행형)

**장점**

- 다중 테넌트, 공용 클라우드 아키텍처로 제공
- 최대 50,000개의 모바일 장치를 지원하도록 확장
- 온-프레미스 인프라, 하드웨어 또는 소프트웨어에서 추가 투자가 필요하지 않음
- 매일 업데이트 및 기능 개선이 수행됨. 주요 특성 및 기능 향상은 월별로 진행됨
- 서비스를 특정 지리적 위치의 데이터 센터에 할당할 수 있음
- 데이터 센터 장애 조치(Failover)가 특정 지리적 위치로 제한될 수 있음
- 대부분의 업계 및 정부 표준에서 인증 및 호환되는 SLA(서비스 수준 계약)는 재정적으로 후원되며, 서비스 또는 기능을 사용할 수 없으면 월별 청구가 취소됨

**단점**

- 사설 클라우드 인스턴스는 지원되지 않음
- 50,000개 이상의 모바일 장치를 지원해야 하는 경우 추가 장치 관리를 위해 Intune을 ConfigMgr에 연결해야 함

## Office 365용 MDM

**장점**

- Office 365 상용 테넌트와 통합하여 모바일 장치와 Office 365 테넌트 서비스를 위한 단일 관리 콘솔 제공(Exchange Online, SharePoint Online 및 Skype for Business Online)
- Office 365 다중 테넌트(공용) 또는 개인(전용) 플랫폼 형식에 제공됨
- 추가 사용자 또는 장치 라이선스 비용이 없음, 기본적으로 Office 365 상용(Business, Enterprise, Education 및 Government) 요금제에 포함

**단점**

- 비모바일 운영 체제 관리를 지원하지 않음
- 비모바일 장치에 대해 온-프레미스 관리 플랫폼을 사용하는 경우에만 모바일 장치를 프로비전하기 위한 추가 관리 인터페이스 필요

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점 및 다음 장점: Intune(클라우드 기반 장치 관리 서비스)와 ConfigMgr(온-프레미스 장치 관리 플랫폼) 간의 기본 통합
- Intune 연결을 통해 모바일 장치에 대한 고급 장치 프로비저닝 옵션 지원
- 새 Intune 서비스 특성 및 기능이 플랫폼 확장을 통해 자동으로 또는 사용자 지정 방식으로 온-프레미스 ConfigMgr 인프라로 확장

**단점**

- Intune을 온-프레미스 ConfigMgr 인프라와 연결하기 위한 추가적인 구성 요구 사항이 필요합니다.
- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성이 필요합니다.

선택적 초기화 후에 제거되는 데이터 및 장치에 남아 있는 데이터에 미치는 영향을 이해하려면 **[Microsoft Intune을 사용하여 원격 초기화, 원격 잠금 또는 암호 재설정으로 데이터 보호 지원](https://technet.microsoft.com/library/jj676679.aspx)** 문서를 읽어보세요. 하이브리드 환경인 경우 ConfigMgr가 이 작업을 수행하는 데 어떻게 도움이 되는지 확인하려면 [Configuration Manager를 사용하여 모바일 장치를 원격으로 초기화하는 방법](https://technet.microsoft.com/library/dn956981.aspx) 문서를 읽어보세요.

SaaS 솔루션 기능 및 요구 사항에 대한 자세한 내용을 보려면 **[Microsoft Intune 서비스 설명](https://technet.microsoft.com/library/dn600286.aspx)**을 검토하여 [MDM for Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) 및 [하이브리드](https://technet.microsoft.com/library/jj884158.aspx) Intune 및 ConfigMgr 인프라에서의 SaaS 지원 차이를 이해하세요.



<!--HONumber=Aug16_HO1-->


