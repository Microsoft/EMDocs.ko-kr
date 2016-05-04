---
# required metadata

title: Microsoft Intune 및 Configuration Manager가 포함된 Exchange Online 및 온-프레미스에서 조건부 액세스 사용
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 5ccd033f-bc31-4fae-b6bf-9e1c2722627f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune 및 Configuration Manager가 포함된 Exchange Online 및 온-프레미스 배포
[회사 메일 및 문서를 보호하기 위한 아키텍처 지침](../Solutions/architecture-guidance-for-protecting-company-email-and-documents.md)을 참고했으므로 솔루션 배포를 진행할 준비가 되었습니다.

Exchange 온-프레미스 및 Exchange Online 둘 다를 사용하여 메일 프로필을 관리하는 환경에서는 기존 온-프레미스 Microsoft Exchange 조직에서 보유한 풍부한 기능을 갖춘 환경과 관리 제어를 클라우드로 확장할 수 있는 기능을 회사에 제공합니다. 이 "하이브리드" 유형의 배포는 온-프레미스 Exchange Server 2013 조직과 Microsoft Office 365의 Exchange Online 간에 단일 Exchange 조직의 매끄러운 모양과 느낌을 제공합니다. 또한 이 유형의 배포는 Exchange Online 조직으로 완전히 이동하기 위한 중간 단계 역할을 할 수 있습니다.

Exchange 온-프레미스와 Exchange Online의 공존성과 함께 Configuration Manager를 이미 사용 중인 경우 Intune을 통합하여 모바일 장치에서 메일 액세스를 관리하고 메일 데이터를 보호할 수 있습니다. 각 솔루션을 개별적으로 구현하기 위한 위의 지침에 따라 이 솔루션을 구현할 수 있습니다.

## 전제 조건
Exchange 온-프레미스와 Exchange Online 둘 다를 구현하는 공존성 유형의 환경을 구성하려면 기존 Exchange 조직이 특정 요구 사항을 충족해야 합니다. 이러한 요구 사항을 충족하지 않으면 Exchange 온-프레미스 조직과 Microsoft Office 365의 Exchange Online 조직 간에 하이브리드 배포를 구성하는 데 필요한 단계를 완료할 수 없습니다.

이러한 유형의 환경을 만들고 구성하기 위한 필수 조건을 검토하려면 [하이브리드 배포 필수 조건](https://technet.microsoft.com/en-us/library/hh534377.aspx) 을 참조하세요.

## 배포 단계
공존성 솔루션을 배포하려면 [Exchange Server 온-프레미스](../Solutions/conditional-access-intune-configmgr-exchange.md) 및 [Exchange Online](../Solutions/conditional-access-intune-configmgr-exchange-online.md) 솔루션 둘 다를 배포하기 위한 위의 단계를 따르세요.

## 추가 정보
모바일 장치의 회사 전자 메일 및 전자 메일 데이터를 보호하기 위한 솔루션을 배포한 후에 [조건부 액세스의 최종 사용자 환경](../Solutions/end-user-experience-conditional-access.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 최종 사용자가 특정 장치를 등록할 때 발생할 수 있는 문제에 대비하는 데 도움이 됩니다.


<!--HONumber=Apr16_HO2-->

