---
title: Microsoft Cloud App Security Government 서비스 설명
description: Microsoft Cloud App Security Government 서비스 설명은 당사 제품에 대한 개요를 제공합니다.
keywords: ''
author: shsagir
ms.author: shsagir
manager: rkarlin
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: 3e122d51c6711a8638e81c4539b666835425ff4f
ms.sourcegitcommit: 76cad8e05a1a149fa5e344e680e6f11c08d89110
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79133923"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security Government 서비스 설명

## <a name="how-to-use-this-service-description"></a>서비스 설명을 사용하는 방법

Microsoft Cloud App Security 미국 정부 서비스 설명은 GCC High 환경의 서비스 제공 사항에 대한 개요를 제공하도록 설계되었으며, 상용 제품에서 변형된 기능에 관해 다룹니다.

GCC 고객을 위한 Microsoft Cloud App Security에 대해 자세히 알아보려면 [미국 Office 365 GCC 고객용 EMS](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description#ems-for-us-office-365-gcc-customers)를 참조하세요.

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-gcc-high"></a>미국 정부 GCC High용 Microsoft Cloud App Security 시작

Microsoft Cloud App Security GCC High 제품은 Microsoft Azure Government Cloud를 기반으로 하며 Office 365 GCC High와 상호 운용되도록 디자인되었습니다. 서비스 및 서비스 사용 방법에 대한 자세한 내용은 [Microsoft Cloud App Security 공개 설명서](https://docs.microsoft.com/cloud-app-security/)에서 확인할 수 있습니다. 공개 설명서를 서비스 배포 및 운영을 위한 시작점으로 사용해야 하며, GCC High 환경의 기능 또는 특정의 모든 변경 사항을 자세히 설명하는 다음 서비스 설명 내용을 참조하세요.

시작하려면 [기본 설정](https:/docs.microsoft.com/cloud-app-security/general-setup) 페이지를 활용하여 Microsoft Cloud App Security GCC High 포털에 액세스하고 [네트워크 요구 사항](https://docs.microsoft.com/cloud-app-security/network-requirements)을 구성해야 합니다. 다른 자세한 지침은 방법 가이드에 나온 추가 단계를 따르세요.

## <a name="feature-variations-in-microsoft-cloud-app-security-gcc-high"></a>Microsoft Cloud App Security GCC High의 기능 변형

달리 지정하지 않는 경우 미리 보기 기능을 포함하여 [Microsoft Cloud App Security의 새로운 기능](https://docs.microsoft.com/cloud-app-security/release-notes)에 설명된 새로운 기능 릴리스는 Microsoft Cloud App Security 상용 환경에서 출시 3개월 이내에 GCC High에서 사용할 수 있습니다.

## <a name="api-connector"></a>API 커넥터

현재 API 커넥터는 AWS GovCloud 및 별도의 정부 클라우드 인스턴스를 제공할 수도 있는 다른 API 연결 애플리케이션용으로 지원되지 않습니다. 타사 애플리케이션의 상용 클라우드 인스턴스를 위한 API 커넥터가 지원됩니다.

Azure 커넥터 및 Office 365 커넥터는 각 서비스의 미국 정부 인스턴스용입니다.

## <a name="data-loss-prevention-dlp-features"></a>DLP(데이터 손실 방지) 기능

Microsoft Cloud App Security 기본 제공 DLP 엔진을 통한 콘텐츠 검사를 사용할 수 있으며 다양한 중요 데이터 유형 중에서 신용 카드 또는 사회 보장 번호 같은 중요한 데이터를 검사할 수 있습니다. Cloud App Security의 [기본 제공 콘텐츠 검사](https://docs.microsoft.com/cloud-app-security/content-inspection-built-in)에 대해 자세히 알아보세요.

**다음 DLP 통합은 지원되지 않습니다.**

- Microsoft Information Protection 레이블이 Office 365 및 Azure Information Protection 전체에서 통합된 레이블 지정을 제공합니다.
- Microsoft DCS(데이터 분류 서비스)와 네이티브 통합

## <a name="conditional-access-app-control"></a>조건부 액세스 앱 제어

Microsoft Cloud App Security 역방향 프록시 기능을 사용하여 조직이 실시간으로 사용자 세션을 모니터링하고 제어할 수 있게 하는 Microsoft Cloud App Security 조건부 액세스 앱 제어를 사용할 수 없습니다.
API에 연결된 애플리케이션에 대해 활동, 파일 및 변칙 검색 정책은 여전히 지원됩니다. 자세한 내용은 [Microsoft Cloud App Security에서 정책을 사용하여 클라우드 앱 제어](https://docs.microsoft.com/cloud-app-security/control-cloud-apps-with-policies)를 참조하세요.

## <a name="notifications-and-automation"></a>알림 및 자동화

경고를 알리는 관리 메일 및 위반이 감지되면 사용자에게 전송되는 알림은 현재 지원되지 않습니다.

## <a name="security-configuration-assessments"></a>보안 구성 평가

Azure 및 AWS에 대한 보안 구성 평가가 지원되지 않습니다.

## <a name="other-integrations"></a>기타 통합

다음 통합을 사용할 수 없습니다.

- Microsoft Defender Advanced Threat Protection
- Microsoft Secure Score에서 Microsoft Cloud App Security 컨트롤 표시

## <a name="next-steps"></a>다음 단계

Cloud App Security에 대해 자세히 알아보고 시작하는 방법을 살펴보려면 [Cloud App Security 공개 설명서](https://docs.microsoft.com/cloud-app-security/)를 참조하세요.
