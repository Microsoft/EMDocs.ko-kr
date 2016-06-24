---
# required metadata

title: 장치 등록 옵션
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 54082b94-1d21-44d5-9fba-af6e04397def

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# 장치 등록 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

독립 실행형이거나 System Center 2012 R2 ConfigMgr(Configuration Manager)에 연결된 Microsoft Intune에 장치를 등록하려면 장치에 맞게 해당 서비스를 준비해야 합니다. MDM for Office 365에서 모바일 장치를 등록하려면 MDM을 활성화하고, 기본 설정을 구성하고, 각 사용자를 [보안 정책](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx)에 포함하고, 다음에 모바일 장치에서 Office 365에 로그인할 때 등록 메시지에 응답해야 합니다. 사용자는 Office 365 메일 및 문서에 액세스하는 데 사용하는 각 모바일 장치에서 등록 및 정품 인증 단계를 완료해야 합니다.

Intune 독립 실행형은 Intune 또는 온-프레미스 ConfigMgr 인프라일 수 있는 모바일 장치 관리 기관 솔루션을 정의하도록 구성해야 합니다. 즉 간단히 말해 "등록 장치를 관리하는 데 Intune *또는* ConfigMgr 중 어떤 관리 플랫폼을 사용할 것인지"를 의미합니다. 관리 솔루션은 일단 선택하면 쉽게 변경할 수 없으므로 [최상의 옵션을 선택할 때의 결과](/Intune/deployuse/enroll-devices-in-microsoft-intune)를 이해하는 것은 *매우 중요합니다*. 나중에 이 구성을 변경해야 하는 경우 Microsoft 지원 서비스에 문의해야 합니다. Office 365 테넌트의 경우 MDM for Office 365와 Intune 사이에서 MDM 권한을 간편하게 지정하고 변경할 수 있습니다. 사용자에 대한 라이선스 할당을 변경하여 간편하게 사용자 수준 관리 권한을 전환할 수 있습니다. 

이미 ConfigMgr를 사용하여 PC, 서버 및 기타 장치를 관리하는 대부분의 조직은 온-프레미스 솔루션을 Intune에 연결하고 ConfigMgr를 사용하여 장치를 관리하는 것이 가장 좋은 방법입니다. 모바일 장치 관리 기관을 ConfigMgr에 할당하려면 [Intune 구독](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0)을 만들고 ConfigMgr에서 Intune 구독 및 Intune 등록 장치를 관리할 수 있도록 하는 옵션을 선택합니다. [ConfigMgr 콘솔 내에서](https://technet.microsoft.com/library/jj884158.aspx) Intune 구독을 만들 수도 있습니다.

또한 다양한 유형의 모바일 운영 체제를 실행하는 특정 유형의 모바일 장치를 등록하려면 먼저 특정 구성 요구 사항에 따라 Intune 서비스 또는 MDM for Office 365를 준비해야 합니다. 예를 들어 Apple iOS 기반 장치를 등록하려는 경우 iOS 기반 장치를 등록하기 전에 **[APN(Apple 푸시 알림) 서비스 인증서를 사용하여 Intune을 구성](https://technet.microsoft.com/library/dn408185.aspx)**해야 합니다. 이 인증서가 구성되지 않으면 Intune에서 APN 서비스 및 iOS 기반 장치와 통신할 수 없습니다. **[Android](https://technet.microsoft.com/library/dn764960.aspx)** 또는 **[Windows Phone](https://technet.microsoft.com/library/dn764959.aspx)** 운영 체제가 실행되는 모바일 장치에는 별도의 등록 요구 사항이 있습니다.

1단계의 질문에 대한 답변은 모바일 장치 관리 솔루션에 장치를 등록하는 방법을 결정하는 데 도움이 됩니다. 아래 표에서는 각 등록 시나리오의 장점과 단점을 비교합니다.

| 영역  | 관리자가 모바일 장치 등록 | 사용자가 직접 장치 등록 |
| ------------- | ------------- | ------------ |
| 비용 | 숙련된 관리자가 장치 등록을 수행하므로 지원 비용/지원 센터 비용 절감 | 지원 비용 또는 지원 센터 호출이 증가하고 숙련되지 않은 사용자가 등록 시 개인적인 도움을 요청할 수 있음 |
| 편리함  | 각 장치가 사용자 개입 없이 등록되므로 장치 등록 오류가 줄어듭니다. 사용자가 모바일 장치를 전달하거나 가져갈 때 관리자와 시간을 맞춰야 할 수 있으므로 장치 등록 예약 및 추적이 필요합니다.| 대부분의 경우 중앙 집중식 등록 프로세스보다 더 빠르게 장치를 등록합니다. 장치 소유자/사용자의 편의와 유연성을 높일 수 있습니다. |
| 관리 | 보다 복잡하거나 대량으로 진행되거나 고도로 사용자 지정된 장치 등록을 간편하게 지원합니다. 관리자가 모든 장치의 등록을 긴밀히 제어하고, 등록 프로세스를 시작할 때 장치 또는 사용자를 효과적으로 미리 차단합니다. | 비교적 간단한 관리 작업을 사용자에게 오프로드하여 시간, 예약, 추적 및 관리 오버헤드를 절감합니다. |
| 보안 | BYOD 전략을 지원하는 경우 적절한 보안 제어 장치가 없을 때 관리자가 중요한 사용자 개인 정보를 보거나 노출할 수 있습니다. | 최신 모바일 장치 사용자는 이러한 중앙 집중식 관리가 번거롭고 불편하다고 느끼게 되어 등록 보안 및 규정 준수를 손상시킬 수 있는 사용자 정의 해결 방안을 따를 수 있음 |

조직에서는 이러한 등록 시나리오를 모두 허용하여 부서 또는 상황별로 유연하게 다른 방법을 사용하도록 할 수 있습니다. 이 경우 모바일 장치 관리 솔루션은 두 시나리오를 모두 지원할 수 있어야 합니다.

<!--HONumber=Jun16_HO1-->


