---
title: "모바일 장치 보호 향상 계획"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a4504456-a241-4380-ab92-3bc14c91347c
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d43860e838a40de05bdec73b00b6721ee634d7e5
ms.openlocfilehash: 8d2df20d71d83ccd38ef96c84600f234665ab27e


---

# 모바일 장치 보호 향상 계획

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

온-프레미스 및 원격 사용자는 자신의 모바일 장치에서 회사 리소스에 액세스하여 생산성을 높일 수 있지만 이렇게 하면 보안 위협이 증가합니다. 회사의 데이터를 보호하고 사용자 개인 정보를 유지하기 위해서는 이러한 보안 위협을 해소해야 합니다. 회사에서는 자체의 상황에 따라 이러한 요구 사항의 균형을 유지하는 방법을 결정해야 합니다. 규정 준수 규칙은 회사의 비즈니스 업종에 따라 다를 수 있으며 이로 인해 결정되는 설계 방식이 달라질 수 있습니다.
 
그러나 업계에 관계없이, 잘 이해하고 준수해야 하는 모바일 장치 관리의 일반적인 보안 측면이 있습니다. 이 옵션은 아래 그림에서 보여 줍니다.

![MDM 플랫폼에 대한 핵심 보안 기능](./media/MDM_Figure_08.png)

## MDM 솔루션의 보안 기능

이 다이어그램에서는 모든 MDM 솔루션에 필요한 핵심 보안 기능을 보여 줍니다. 고려해야 할 주요 영역은 다음과 같습니다.

1. 모바일 장치 수준의 데이터 보호 고려 사항:
    - 데이터 암호화
    - 데이터 분류
    - 클라이언트 개인 정보
    - 컨테이너화
    - 정책 적용
    - 규정 준수 정책
    - 보안 강화
2. 전송 시 데이터 보호 고려 사항:
    - 데이터 암호화
    - 인증
    - 권한 부여
3. 온-프레미스 조직에서의 데이터 보호 고려 사항:
    - 데이터 암호화
    - 인증
    - 권한 부여
4. 클라우드에서의 데이터 보호 고려 사항:
    - 데이터 암호화
    - 인증
    - 권한 부여

다음 섹션에서 설명하는 작업은 가장 적합한 MDM 솔루션을 결정하는 데 영향을 미치는 방식을 이해하는 데 도움이 될 수 있습니다.

## 이 단계 정보

이 가이드의 본 섹션에는 12단계가 있습니다. 전체 섹션을 읽는 시간은 총 36분이며 특정 섹션으로 건너뛸 수도 있습니다.

- [데이터 보호 요구 사항 수집](mdm-gather-data-protection-requirements.md)
- [개인 정보 보호 요구 사항 지정](mdm-specify-privacy-requirements.md)
- [액세스 요구 사항 지정](mdm-specify-your-access-requirements.md)
- [사고 대응 요구 사항 파악](mdm-develop-incident-response-requirements.md)
- [데이터 암호화에 대한 계획](mdm-data-encryption.md)
- [데이터 분리에 대한 계획](mdm-data-segregation.md)
- [모바일 장치 보안 강화](mdm-hardening-mobile-devices.md)
- [클라이언트 개인 정보](mdm-client-privacy.md)
- [데이터 분류](mdm-data-classification.md)
- [인증 및 권한 부여](mdm-authentication-authorization.md)
- [리소스에 대한 액세스 제어](mdm-access-control-resources.md)





<!--HONumber=Jun16_HO4-->


