---
# required metadata

title: BYOD 인프라 솔루션 구상
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9596531a-2eef-4c91-af11-091088c52929

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#BYOD 인프라 솔루션 구상

해결하려는 BYOD 문제를 명확하게 정의한 후 문제에 대한 솔루션을 정의하고 솔루션의 세부 요구 사항을 정의할 수 있습니다.

## 솔루션 정의

앞에서 확인한 문제를 해결하고 조직의 사용자가 자신의 장치를 회사로 가져와 해당 장치에서 회사 데이터에 액세스할 수 있도록 하려면 회사가 장치 중심 IT 방식에서 사용자 중심 IT 방식으로 전환해야 합니다. 이 문서의 디자인 고려 사항은 다음과 같은 고유한 BYOD 인프라 솔루션을 정의할 때 사용할 수 있습니다. 

- 사용자가 자신의 장치를 사용하여 회사 앱 및 데이터에 액세스할 수 있는 유연성을 제공합니다.
- 온-프레미스 및 클라우드에서 회사 리소스에 액세스하고 있는 장치를 관리합니다.
- 암호화 및 권한 관리를 사용하여 권한 없는 로컬 액세스로부터 보호하고 장치가 손실되거나 사용 중단된 경우 또는 직원의 종료 프로세스 중에 인터넷을 통해 회사 데이터를 원격으로 삭제하여 IT 부서에서 장치에 저장된 회사 데이터를 보호할 수 있도록 합니다.
- 사용자가 온-프레미스 및 클라우드에서 리소스에 액세스할 때 일반적인 ID를 제공합니다.
- IT 부서에서 여러 ID를 관리하여 서로 다른 환경에서 정보가 동기화되도록 합니다.
- Multi-Factor Authentication 및 Single Sign-On과 같은 엔터프라이즈 인증 서비스를 사용합니다.
- 정보 보안 및 규정 준수 증명과 같은 규정 준수 활동을 제공합니다.

## 솔루션 요구 사항

사용자가 자신의 장치를 사용하여 회사 리소스에 액세스할 수 있도록 하려면 먼저 기존 인프라의 기술적 역량을 수정해야 합니다. 이러한 수정 작업의 목표는 이 새 모델에 대한 솔루션 요구 사항이 이미 충족되는지 또는 문제를 해결하기 위해 새로운 기술을 도입해야 하는지를 파악하는 것입니다. 이렇게 하려면 먼저 환경의 제약 조건뿐만 아니라 다양한 요구 사항을 정의해야 합니다. 일부 요구 사항 및 제약 조건은 역량 소비자가 정의하지만 기존의 기술적 역량, 서비스, 정책 및 프로세스와 관련된 일부는 기존 환경에 의해 정의됩니다.

사용자가 관리되는 장치에서 회사 리소스에 액세스할 수 있도록 요구 사항, 제약 조건 및 디자인을 결정하는 것이 주요 프로세스입니다. 환경의 제약 조건과 연관된 초기 요구 사항은 일부 초기 요구 사항을 충족하지 못하는 초기 디자인을 만들 수 있으므로 초기 요구 사항과 이후 디자인을 변경해야 합니다. 요구 사항 및 디자인을 마무리하기 전에 요구 사항 및 솔루션 디자인 정의를 여러 번 반복해야 합니다. 따라서 이 문서를 통한 첫 번째 실행이 마지막 실행이 될 거라고 기대하지 않는 것이 좋습니다. 프로세스 초반의 의사 결정에서 프로세스 후반에 사용할 수 있게 된 보다 기본적인 옵션이 제외된 것을 확인할 수 있습니다.

다음 섹션의 질문과 대답은 사용자가 자신의 장치에서 회사 리소스에 액세스할 수 있도록 하기 위한 포괄적인 요구 사항 목록을 작성하며, 이 목록은 IT 부서에서 데이터를 보호하면서 관리할 수 있습니다. 이러한 질문은 공급업체와 관련이 없으며 모든 BYOD 인프라 솔루션에 적용할 수 있습니다.

이 가이드에 표시된 BYOD 문제 영역과 관련된 고려 사항은 하위 영역으로 구분됩니다. 각 하위 영역에는 구성 요소 컬렉션이 있습니다. 이 가이드에 제시된 각 하위 도메인의 경우 다음과 같은 요구 사항이 있습니다.

- 사용자 및 장치 요구 사항
- 데이터 액세스 및 보호 요구 사항
- 관리 요구 사항
- 앱 요구 사항



<!--HONumber=Apr16_HO2-->

