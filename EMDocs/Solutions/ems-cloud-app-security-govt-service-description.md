---
title: Microsoft Cloud App Security 정부 서비스 설명
description: Microsoft Cloud App Security 정부 서비스 설명은 제공의 개요를 제공 하도록 설계 되었습니다.
keywords: ''
author: shsagir
ms.author: shsagir
manager: rkarlin
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: c8b0bf7c4e4d687f8441c0aba71ebf55d6a108a2
ms.sourcegitcommit: 422f43a00933c66f17c85de243a1a3cf1a08cda2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "101831482"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security 정부 서비스 설명

## <a name="how-to-use-this-service-description"></a>이 서비스 설명을 사용 하는 방법

미국 정부 서비스에 대 한 설명은 GCC High 및 보호 (DoD) 환경에서 서비스 제공의 개요를 제공 하 고, 상용 제품의 기능 변형을 다룹니다. Microsoft Cloud App Security GCC 고객의 Microsoft Cloud App Security에 대 한 자세한 내용은 [microsoft의 EMS MICROSOFT 365 gcc 고객에 대 한 EMS](ems-govt-service-description.md#ems-for-us-gcc-high-and-dod-customers)를 참조 하세요.

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-offerings"></a>미국 정부 제품에 대 한 Microsoft Cloud App Security 시작

GCC High 및 DoD 고객에 대 한 Microsoft Cloud App Security 제품은 Microsoft Azure Government 클라우드에서 빌드되고 GCC High 및 DoD 환경과 Microsoft 365 간에 작동 하도록 설계 되었습니다. 서비스 및 사용 방법에 대 한 자세한 내용은 [Microsoft Cloud App Security 공개 문서](/cloud-app-security/)를 참조 하세요. 공개 문서는 서비스 배포 및 운영을 위한 출발점으로 사용 되어야 하며, GCC High 또는 DoD 환경의 기능이 나 기능에서 제공 하는 다음과 같은 서비스 설명 세부 정보 및 변경 사항을 제공 합니다.

시작 하려면 GCC High 또는 DoD 포털 Microsoft Cloud App Security에 대 한 액세스를 위한 [기본 설정](/cloud-app-security/general-setup) 페이지를 활용 하 고 [네트워크 요구 사항이](/cloud-app-security/network-requirements) 구성 되어 있는지 확인 합니다. 사용자 고유의 키를 사용 하 여 미사용 데이터를 암호화 하는 Cloud App Security 구성 하려면 [사용자 고유의 키를 사용 하 여 미사용 데이터 암호화 Cloud App Security (BYOK)](ems-cloud-app-security-govt-service-byok.md)를 참조 하세요. 다른 자세한 지침은 방법 가이드의 추가 단계를 따르세요.

> [!NOTE]
> 데이터 암호화는 현재 특정 Microsoft Cloud App Security 정부 제품에 대해서만 사용할 수 있습니다.

## <a name="feature-variations-in-microsoft-cloud-app-security-us-government-offerings"></a>미국 정부 제품 Microsoft Cloud App Security의 기능 변형

별도로 지정 하지 않는 한, [Microsoft Cloud App Security의 새로운](/cloud-app-security/release-notes)기능에 설명 된 미리 보기 기능을 포함 한 새로운 기능 릴리스는 다른 언급이 없는 한, Microsoft Cloud App Security 상용 환경에서 릴리스된 3 개월 이내에 GCC High 및 DoD 환경에서 사용할 수 있습니다.

## <a name="api-connector"></a>API 커넥터

AWS GovCloud 및 기타 정부 클라우드 인스턴스를 제공할 수도 있는 기타 API 연결 응용 프로그램에 대 한 API 커넥터는 현재 지원 되지 않습니다. 타사 응용 프로그램의 상용 클라우드 인스턴스에 대 한 API 커넥터가 지원 됩니다.

Azure 커넥터 및 Microsoft 365 커넥터는 각 서비스의 미국 정부 기관에 대 한 것입니다.

## <a name="notifications-and-automation"></a>알림 및 자동화

경고에 대 한 관리자 메일 알림과 위반이 감지 될 때 사용자에 게 전송 된 알림은 현재 지원 되지 않습니다.

## <a name="azure-sentinel-integration"></a>Azure Sentinel 통합

현재 Microsoft Cloud App Security와 Azure 센티널 간의 통합은 지원 되지 않습니다.

## <a name="other-integrations"></a>기타 통합

다음 통합을 사용할 수 없습니다.

- 엔드포인트에 대한 Microsoft Defender
- Microsoft 보안 점수의 서피싱 Microsoft Cloud App Security 컨트롤

## <a name="next-steps"></a>다음 단계

Cloud App Security에 대해 자세히 알아보고 시작 하는 방법에 대 한 자세한 내용은 [공개 문서를 Cloud App Security](/cloud-app-security/).