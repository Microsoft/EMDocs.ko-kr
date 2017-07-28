---
title: "모바일 장치 관리 요구 사항 지정"
description: "이 문서에서는 모바일 장치 관리 시나리오에서 장치 위치와 관련된 일반 요구 사항을 제공합니다."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c8824726-082e-417a-8522-183a69328ae4
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: d5e7d0231795558aadc96786741e710a3352d097
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="specify-your-mobile-device-management-location-requirements"></a>모바일 장치 관리 요구 사항 지정

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

위치 요구 사항은 모바일 장치 관리 전략을 설계할 때 고려해야 할 여러 요인 중 하나입니다. 위치는 장치 자체뿐만 아니라 모바일 장치 관리 솔루션 관점에서도 중요합니다. 다음 질문에 답변합니다.

- 사용자 추적: 일부 유형의 모바일 장치 제어에서는 사용자의 위치에 따라 회사 리소스에 대한 액세스를 제한할 수 있는 정책을 구현해야 할 수 있습니다.
    - 회사에 지오펜싱을 위한 메커니즘이나 장치의 지리적 위치에 따라 정책을 적용하는 기능이 필요한가요?
    - 회사에서 사용자가 회사 리소스에 액세스할 때 사용자의 지리적 위치를 추적해야 하나요?
- 관리 모델: 배포하는 모바일 장치 관리 솔루션에 따라 관리 작업을 여러 다른 사이트(위치)에 분산하거나 단일 위치에 집중할 수 있습니다. 중앙 관리 사이트는 대규모 배포에 적합하며 글로벌 네트워크 인프라를 통해 배포되는 장치를 지원할 수 있는 유연성과 중앙 관리 지점을 제공합니다. 기본 사이트는 향후 성장에 맞게 조정할 수 있는 옵션은 더 적지만 소규모 배포에 적합합니다. MDM을 중앙에서 제어할지 또는 분산 방식으로 제어할지를 결정합니다.
    - 회사에 중앙 관리 모델이 필요한가요?
    - 장치 관리 솔루션을 온-프레미스에 배치해야 하나요?
        - 그러지 않은 경우 클라우드에 둘 수 있나요?
        - 그러지 않은 경우 하이브리드 방식일 수 있나요?
    - 회사에서 위치에 따라 자율적으로 장치를 관리할 수 있는 분산형 모델이 필요한가요?

>[!TIP]
> 각 응답을 적어두고 답변의 의미를 이해해야 합니다. 다음 섹션에서는 사용 가능한 옵션과 각 옵션의 장단점을 살펴봅니다.  이러한 질문에 답변하면서 비즈니스 요구에 적합한 최상의 솔루션을 선택할 수 있게 됩니다.
