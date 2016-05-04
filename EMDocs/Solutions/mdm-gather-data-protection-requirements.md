---
# required metadata

title: 데이터 보호 요구 사항 수집
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 98f7bd00-4be7-478e-82ea-6046813f1556

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 데이터 보호 요구 사항 수집

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

모바일 장치에 대한 조직의 데이터 보호 요구 사항을 정의하는 데 도움이 되려면 먼저 조직에 이미 있는 데이터 보호 요구 사항을 고려하는 것이 좋습니다. 예를 들어 회사가 특정 규정을 준수해야 하거나 사용자에게 데이터 보호 관련 정책이 이미 있을 수 있습니다. 

먼저 이러한 중요한 요구 사항을 적어둔 다음 이를 토대로 MDM 솔루션에 대해 더 나은 설계 결정을 내리는 데 도움이 되는 보다 세분화된 질문에 답변할 수 있습니다.  이러한 요구 사항의 정의할 때는 다음 사항을 고려합니다.

- 저장된 데이터 암호화: 그림 8에서처럼 회사 데이터는 사용자의 모바일 장치에 저장됩니다. 회사에 다음이 사항이 중요한지 고려하세요. 
    - MDM 솔루션이 전체 모바일 장치 디스크 및 SD 카드의 암호화를 지원하나요?
        - 지원하는 경우 어떤 운영 체제에 해당하나요?
    - MDM 솔루션이 앱 데이터 암호화를 지원하나요?
        - 지원하는 경우 어떤 운영 체제에 해당하나요?
        - 지원하는 경우 어떤 앱에 해당하나요?
- 전송 중인 데이터 암호화: 데이터 소유자에 상관 없이, 데이터 통신 중 특정 시점에, 모바일 장치와 회사 서버(또는 웹 서비스) 간에 데이터가 전송됩니다. MDM 솔루션에 전송 중인 데이터를 보호하기 위한 어떤 기능이 있는지 이해해야 합니다. 회사에 다음이 사항이 중요한지 고려하세요. 
    - MDM 솔루션이 전송 중인 데이터의 암호화를 지원하나요?
        - 지원하는 경우 어떤 운영 체제에 해당하나요?
        - 지원하는 경우 어떤 기능을 사용할 수 있나요?
    - MDM 솔루션에 전송 중인 데이터를 보호하기 위한 어떤 옵션이 있나요?
- 데이터 분리: 회사 데이터를 사용자의 데이터와 따로 처리해야 하는지 여부도 이해하는 것이 중요합니다. 이러한 기능을 설명하는 데 용어 분리 또는 격리를 사용할 수 있습니다. MDM 솔루션을 설계할 때는 다음을 고려하세요.
    - MDM 솔루션이 데이터 분리를 지원하나요?
        - 지원하는 경우 모바일 장치 사용자의 데이터를 유지하면서 회사의 데이터를 지울 수 있나요?
    - MDM 데이터 분리 기능이 신뢰할 수 있는 앱만 모바일 장치에 있는 데이터에 액세스할 수 있도록 보장하나요?
    - MDM 솔루션은 사용자 ID에 따른 데이터 분리를 지원하나요?
    - MDM 솔루션이 컨테이너화를 지원하나요?
        - 지원하는 경우 특정 컨테이너에 있는 데이터를 암호화할 수 있나요?
- 모바일 장치 보안 강화: 조직에서 여러 다른 모바일 장치 플랫폼이 사용될 수 있으므로 각 모바일 장치 플랫폼에서 사용할 수 있는 보안 강화 기능을 이해해야 합니다. 각 모바일 장치 플랫폼은 다양한 방법 및 다른 세분화 수준을 사용하여 장치 보안을 강화하고 제어할 수 있습니다. 한 모바일 장치 집합이 다른 집합보다 좀 더 세분화된 구성 집합을 갖는 경우 사용자 지정 정책을 사용하여 조직에서 지원하는 각 모바일 장치 플랫폼에 대한 보안을 강화하면서 장치 보안을 강화하는 공통 옵션 집합이 필요할 것입니다. 

아래 목록에는 모바일 장치 보안을 강화하기 위해 MDM 솔루션에서 지원해야 공통된 옵션에 나와 있습니다.

- 모바일 장치의 잠금 해제를 위해 암호 필요
- 암호 유형 필요 - 최소 문자 및 문자 형식
- 최소 암호 길이
- 모바일 장치를 초기화하기 전까지 허용되는 로그인 반복 오류 횟수
- 장치 화면이 잠기기 전까지 비활성 시간(분)
- 암호 기록 기억 -> 이전 암호 다시 사용 안 함
- 암호 만료(일)
- 모바일 장치에 대한 암호화 필요
- 메모리 카드 암호화 필요
- 암호 없는 유휴 반환 허용

>[!TIP] Windows Phone 8.1에서는 [Windows Phone 8.1 Enterprise Device Management Protocol](http://download.microsoft.com/download/C/A/0/CA091018-1A43-4063-B70B-20B9901F4D10/Windows Phone 8.1 MDM Protocol.pdf)을 사용하여 암호 없는 정책 허용 유휴 반환을 구성할 수 있습니다.

<!--HONumber=Apr16_HO2-->

