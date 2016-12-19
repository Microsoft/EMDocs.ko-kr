---
title: "MDM에서 MAM을 사용하여 회사 데이터 보호"
description: "MAM(모바일 앱 관리) 정책을 사용하여 앱을 만들고 배포하여 회사 데이터를 최상으로 보호합니다."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6c7088a9-ca88-4ff2-97a6-f842691fd3c7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fd6318efea58b5b6b72de306339629b568bc902d
ms.openlocfilehash: dcf178146e9145f7526368763a8c1452327d939a


---

# 앱 관리 정책을 통해 모바일 장치에서 회사 데이터 보호
회사의 데이터를 보호하는 일은 매우 중요하며 점점 더 많은 직원들이 모바일 장치를 사용하여 메일 및 메일 첨부 파일을 포함한 회사 리소스에 액세스함에 따라 더 어려운 과제가 되고 있습니다. IT 관리자는 직원들의 모바일 장치가 회사의 물리적 위치를 벗어나는 경우에도 회사 데이터를 보호해야 합니다.

이 가이드에서는 관리되는 응용 프로그램을 두 개의 Intune MDM 배포에 적용할 경우 이러한 응용 프로그램을 지원하는 방법을 중점적으로 설명합니다.

- Intune을 사용하여 클라우드 관리 솔루션으로 구현
- Configuration Manager와의 통합 서비스로 구현

이 방법을 사용하면 MAM(모바일 앱 관리) 정책을 사용하여 앱을 만들고 배포하여 회사 데이터를 가장 잘 보호할 수 있습니다.

이 문서에서는 최종 사용자 장치가 MDM용 Intune에 등록될 때 이러한 MAM 기반 정책을 만드는 방법을 중점적으로 다룹니다. 장치 자체가 MDM용 Intune에 등록되지 않은 경우 이러한 MAM 정책을 구성하는 방법에 대한 자세한 내용은 [Microsoft Intune에 등록되지 않은 장치의 기간 업무 앱 및 데이터 보호](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune)를 참조하세요.

> [!TIP]
> [TechNet 갤러리](https://gallery.technet.microsoft.com/Protect-Company-Data-on-d972f4f4/file/154240/1/Protect%20Company%20Data%20on%20Mobile%20Devices%20through%20Application%20Management%20Policies.pdf)에서 이 전체 항목의 복사본을 다운로드하세요.

## 소개
관리되는 앱은 회사의 보안 요구 사항을 준수하게끔 MAM 정책이 적용되는 앱입니다. 모바일 앱을 관리하는 두 가지 옵션은 다음과 같습니다.
- **기본 기능**(예: Apple Managed Open In): 특정 문서 및 메일 첨부 파일을 열 수 있는 앱을 제어하여 회사 데이터를 보호합니다.
- **Intune 앱 SDK**: Intune 앱 SDK가 사용되도록 설정된 앱의 기능 및 데이터 공유를 제한할 수 있습니다. Intune 앱 SDK의 주요 기능 중 일부는 다음 작업을 수행할 수 있다는 것입니다.
  - save-as 함수 관리
  - 잘라내기, 복사, 붙여넣기 방지
  - 앱에 액세스할 때 인증 요구
  - Intune에서 관리하는 앱에서 회사 데이터 초기화

  모든 SDK 기능에 대한 설명을 보려면 [Intune 앱 SDK 개요](https://docs.microsoft.com/intune/develop/intune-app-sdk)를 참조하세요.

## 시작하기 전에
- **Microsoft Intune을 사용하여 앱을 배포하는 방법 알아보기:**  Intune 앱 배포에 대한 [기본 사항을 알아보세요](https://docs.microsoft.com/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).

- **원하는 구현 평가:** 모바일 장치 관리를 위한 모든 다양한 디자인 및 구성 옵션으로, 회사 요구에 가장 잘 부합하는 조합을 결정하기가 어렵습니다. [모바일 장치 관리 디자인 고려 사항 가이드](https://docs.microsoft.com/enterprise-mobility/Solutions/mdm-design-considerations-guide)를 참조하면 모바일 장치 관리 디자인 요구 사항을 이해하고, 회사의 비즈니스 및 기술 요구 사항에 가장 적합한 솔루션을 디자인하기 위해 수행하는 일련의 단계와 작업을 세부적으로 살펴볼 수 있습니다.
- **높은 수준의 최종 사용자 환경 이해:** 솔루션이 구현되면 회사에서 장치를 관리하는지 여부에 관계없이 장치의 데이터를 보호할 수 있습니다. 앱 수준 정책을 구현하기만 하면 회사 리소스에 대한 액세스를 제한하고 IT 부서의 범위 내에 데이터를 유지할 수 있습니다.

   > [!NOTE]
   > 이 솔루션의 최종 사용자 환경은 [최종 사용자 환경](end-user-experience-mam.md)에 자세히 설명되어 있습니다.

- **앱 수명 주기 이해:** 장치 관리 방식과 마찬가지로 앱의 경우에도 전체 수명 주기에서 준비, 배포, 모니터링, 업데이트, 사용 중지 등의 작업을 수행해야 합니다. Intune은 이 수명 주기의 모든 단계에서 도움이 됩니다. 앱 수명 주기에 대한 자세한 내용은 [앱 수명 주기 개요](https://docs.microsoft.com/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune)를 참조하세요.
- **MAM 정책을 함께 사용할 수 있는 Microsoft 앱에 대한 자세한 정보:** [Microsoft Intune 응용 프로그램 파트너](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) 페이지에는 모바일 앱 관리 정책과 함께 사용할 수 있는 Microsoft 및 기타 회사의 앱에 관한 최신 정보가 나와 있습니다.

  Microsoft Intune 앱 래핑 도구를 사용하여 사내 앱의 동작을 수정하면 해당 앱 코드를 수정하지 않고도 앱 기능을 구성할 수 있습니다. 좀 더 구체적인 내용은 다음 항목을 참조하세요.
 - [Microsoft Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 iOS 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
 - [Intune 앱 래핑 도구를 사용하여 모바일 응용 프로그램 관리용 Android 앱 준비](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

- **정책 충돌을 해결하는 방법 이해:** 사용자나 장치에 대한 첫 번째 배포에서 모바일 앱 관리 정책이 충돌하면 앱에 배포된 정책에서 충돌한 특정 설정 값이 제거되며 앱은 기본 제공 충돌 값을 사용합니다(기본값: **제한 수준 높음**).

  그 이후의 앱 또는 사용자에 대한 배포에서 모바일 앱 관리 정책이 충돌하는 경우에는 충돌한 특정 설정 값이 앱에 배포된 모바일 앱 관리 정책에 업데이트되지 않으며 앱은 해당 설정의 기본 값을 사용합니다.

  장치나 사용자가 충돌하는 두 정책을 받는 경우에는 다음 동작이 적용됩니다.
  - 정책이 장치에 이미 배포된 경우에는 기존 정책 설정을 덮어쓰지 않습니다.
  - 장치에 아직 배포된 정책이 없는 상태에서 충돌하는 두 설정이 배포되면 장치에서 기본 제공되는 설정이 사용됩니다.

## 추가 정보
MAM의 전체 프로세스에 익숙해졌으면 [Intune에서 모바일 앱 관리 정책 사용](mam-intune.md) 또는 [Configuration Manager에서 모바일 앱 관리 정책 사용](mam-configmgr.md) 준비가 완료된 것입니다. 또는 [MAM 정책의 최종 사용자 환경](end-user-experience-mam.md)에 대해 알아볼 수 있습니다.



<!--HONumber=Nov16_HO2-->


