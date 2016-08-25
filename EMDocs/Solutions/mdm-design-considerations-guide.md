---
title: "모바일 장치 관리 디자인 고려 사항 가이드"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7083b6b8-27a3-427b-b505-25d007d63cdd
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b77c2b49180c3871a1885d8faa232b412bac384
ms.openlocfilehash: 3aa63ee4cab5e53ea37b34e02aead8e188bbda52


---

# 모바일 장치 관리 디자인 고려 사항 가이드

MDM(모바일 장치 관리) 솔루션에 대한 다양한 설계 및 구성 옵션을 고려할 때 조직의 요구에 가장 잘 맞는 솔루션을 결정하는 일은 어려울 수 있습니다. 이 설계 가이드는 MDM 설계 요구 사항을 이해하도록 도와주고, 조직의 비즈니스 및 기술 요구에 가장 잘 맞는 MDM 솔루션을 설계하기 위해 진행할 수 있는 일련의 단계와 작업을 자세히 설명합니다. 

## 시작

각 단계 및 작업을 진행하면서 이 가이드에서는 조직이 기능 및 서비스 품질(예: 가용성, 확장성, 성능, 관리 및 보안) 수준 요구 사항을 충족할 수 있는 관련 기술 및 기능 옵션을 설명합니다.

구체적으로 이 가이드의 목표는 다음 질문에 답변하도록 도와주는 것입니다.

- 비즈니스 요구 사항에 가장 부합하는 모바일 장치 관리 솔루션의 도입을 촉진하기 위해 답해야 하는 질문은 무엇인가요?
- 사용자 조직을 위한 모바일 장치 관리 솔루션을 설계하기 위해 수행이 필요한 일련의 작업은 무엇인가요?
- 사용자 조직의 요구 사항에 부합하는 데 도움이 되는 Microsoft 모바일 관리 기술 및 구성 옵션은 무엇이며 서로 어떤 장단점이 있나요?

**이 가이드의 대상** 중간 규모 또는 대규모 조직을 위한 모바일 장치 관리 솔루션을 설계하는 정보 기술 설계자 및 전문가

**이 가이드의 활용 방법** 이 가이드를 사용하여 회사 소유의 장치 뿐 아니라 다양한 폼 팩터의 사용자 소유 장치를 관리할 수 있는 모바일 장치 관리 솔루션을 설계하는 방법을 이해할 수 있습니다.

![하이브리드 Intune 및 System Center Configuration Manager MDM 솔루션의 예](./media/MDM_Figure_01.png)
**하이브리드 Intune 및 System Center Configuration Manager MDM 솔루션의 예**

위의 그림에서는 해당 위치에 관계 없이 모든 유형의 장치를 관리할 수 있도록 클라우드 서비스를 활용하여 온-프레미스 기능에 통합하는 하이브리드 관리 솔루션의 예를 보여 줍니다. 이것은 매우 일반적인 시나리오이지만 각 조직은 고유한 관리 요구 사항을 가지므로 각 조직의 MDM 설계가 예와 다를 수 있습니다.
 
이 가이드에서는 조직의 고유한 요구 사항에 적합한 사용자 지정된 MDM 솔루션을 설계하기 위해 따라야 하는 일련의 단계 및 작업에 대해 자세히 설명합니다. 다음 단계 및 작업 전체에서 이 가이드는 MDM의 기능 및 서비스 품질 수준 요구 사항을 충족하기 위해 사용할 수 있는 적절한 기술 및 기능 옵션을 소개합니다. 

이 가이드는 MDM 솔루션을 설계하는 데 도움을 줄 수 있지만 관리 솔루션에 대한 구체적인 구현, 작업 옵션 또는 기존 타사 MDM 솔루션에서 마이그레이션하는 방법은 설명하지 않습니다. 이 가이드 끝에 나오는 **다음 단계 및 추가 리소스** 섹션에 제공되는 링크를 사용하여 TechNet 라이브러리에서 [Microsoft Intune](/Intune/), [Mobile Device Management for Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) 및 [Microsoft System Center Configuration Manager](https://technet.microsoft.com/library/cc507089.aspx)에 대한 자세한 배포 및 구성 단계를 찾을 수 있습니다.

[여기](https://blogs.technet.microsoft.com/intunesupport/2016/02/10/new-guide-on-how-to-migrate-from-other-mdm-technologies-to-microsoft-intune/)에서 다른 MDM 솔루션에서 Microsoft Intune으로 마이그레이션하는 방법에 대한 지침도 찾을 수 있습니다.

**가정:** 사용자가 Microsoft Intune, System Center 2012 R2 ConfigMgr(Configuration Manager), Windows Server 2012 R2와, Android, iOS 및 Windows Phone을 실행하는 모바일 장치에 대해 다소 경험이 있습니다. 초기 MDM 테스트 또는 제한된 프로덕션 환경에서 이러한 솔루션 중 하나를 배포했을 수도 있습니다. 이 가이드는 이러한 솔루션이 어떻게 자체 또는 통합된 솔루션에서 비즈니스 요구를 충족할 수 있는지 확인하려는 사용자를 위해 작성되었습니다.

## MDM 설계 고려 사항
이 가이드에서는 요구 사항에 가장 잘 맞는 솔루션을 설계하기 위해 수행할 수 있는 단계 및 작업 집합을 다룹니다. 이러한 단계는 순서에 따라 제시됩니다. 그러나 설계를 진행하면서 생각이 달라지거나 충돌하는 설계 선택 사항 때문에 이후 단계에서 배우는 설계 고려 사항에 따라 이전 단계에서 결정한 사항을 변경해야 할 수 있습니다. 이 가이드 전체에서 설계 충돌이 발생할 수 있다는 점에 유의하세요.

이 가이드에 포함된 모든 고려 사항을 적용할 수 있도록 필요한 만큼 다음 단계를 반복하면 요구 사항에 가장 적합한 모바일 장치 관리 설계를 얻을 수 있습니다. 

- [1단계: 모바일 장치 관리 요구 사항 파악](mdm-step-1-identify-your-mobile-device-management-requirements.md)
- [2단계: 모바일 장치 관리 계획](mdm-step-2-plan-for-mobile-device-management.md)
- [3 단계: 모바일 장치 보안 계획](mdm-step-3-plan-enhancing-mobile-devices-protection.md)
- [4단계: SaaS(Software as a Service) 모바일 장치 관리 계획](mdm-step-4-plan-for-software-as-a-service-mobile-device-management.md)
- [다음 단계 및 추가 리소스](mdm-next-steps-and-additional-resources.md)
        
## 다운로드 가능한 버전을 찾고 있나요?
이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.



<!--HONumber=Aug16_HO1-->


