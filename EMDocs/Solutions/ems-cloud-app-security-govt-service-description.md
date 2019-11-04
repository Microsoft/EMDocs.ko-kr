---
title: Microsoft Cloud App Security 정부 서비스 설명
description: Microsoft Cloud App Security 정부 서비스 설명은 제공의 개요를 제공 하도록 설계 되었습니다.
keywords: ''
author: mlottner
ms.author: mlottner
manager: rkarlin
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.suite: ems
ms.openlocfilehash: c0e22cdbbbddf99edb3b3e862afd58ad11c941ea
ms.sourcegitcommit: fd344763857d03303006b9da4f6931ed320d27ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462687"
---
# <a name="microsoft-cloud-app-security-government-service-description"></a>Microsoft Cloud App Security 정부 서비스 설명

## <a name="how-to-use-this-service-description"></a>이 서비스 설명을 사용 하는 방법 
미국 정부 기관 서비스 설명은 GCC High 환경에서 서비스 제공에 대 한 개요를 제공 하도록 설계 되었으며, 상용 제품의 기능 변형을 다룹니다. Microsoft Cloud App Security 

GCC 고객의 Microsoft Cloud App Security에 대 한 자세한 내용은 [미국 Office 365 GCC 고객을 위한 EMS](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description#ems-for-us-office-365-gcc-customers)를 참조 하세요.   

## <a name="getting-started-with-microsoft-cloud-app-security-for-us-government-gcc-high"></a>미국 정부 GCC High에 대 한 Microsoft Cloud App Security 시작 
Microsoft Cloud App Security GCC High 제품은 Microsoft Azure Government 클라우드를 기반으로 하며 Office 365 GCC High와의 상호 작용을 위해 설계 되었습니다. 서비스 및 사용 방법에 대 한 자세한 내용은 [Microsoft Cloud App Security 공개 문서](https://docs.microsoft.com/cloud-app-security/)를 참조 하세요. 공용 설명서를 사용 하 여 서비스를 배포 하 고 운영 하는 출발점으로 사용 하 고, GCC High 환경의 기능이 나 기능에서 제공 하는 다음과 같은 서비스 설명 세부 정보 및 변경 사항을 사용 해야 합니다.

시작 하려면 Microsoft Cloud App Security GCC High portal에 액세스 하기 위한 [기본 설정](https:/docs.microsoft.com/cloud-app-security/general-setup) 페이지를 활용 하 고 [네트워크 요구 사항이](https://docs.microsoft.com/cloud-app-security/network-requirements) 구성 되어 있는지 확인 합니다. 다른 자세한 지침은 방법 가이드의 추가 단계를 따르세요. 

## <a name="feature-variations-in-microsoft-cloud-app-security-gcc-high"></a>Microsoft Cloud App Security GCC High의 기능 변형 
별도로 지정 하지 않는 한, [Microsoft Cloud App Security의 새로운](https://docs.microsoft.com/cloud-app-security/release-notes)기능에서 설명 하는 미리 보기 기능을 비롯 한 새로운 기능 릴리스는 Microsoft Cloud App Security 상업적 출시 3 개월 이내에 GCC 이상에서 사용할 수 있습니다. 환경 (별도로 지정 하지 않은 경우) 

## <a name="api-connector"></a>API 커넥터 

AWS GovCloud 및 기타 정부 클라우드 인스턴스를 제공할 수도 있는 기타 API 연결 응용 프로그램에 대 한 API 커넥터는 현재 지원 되지 않습니다. 타사 응용 프로그램의 상용 클라우드 인스턴스에 대 한 API 커넥터가 지원 됩니다. 
 
Azure 커넥터 및 Office 365 커넥터는 각 서비스의 미국 정부 기관에 대 한 것입니다. 

## <a name="data-loss-prevention-dlp-features"></a>DLP (데이터 손실 방지) 기능  
Microsoft Cloud App Security 기본 제공 DLP 엔진을 통해 콘텐츠 검사를 사용할 수 있으며, 신용 카드 또는 주민 등록 번호와 같은 중요 한 데이터를 다른 많은 중요 한 데이터 형식으로 검사할 수 있습니다. Cloud App Security에서 [기본 제공 콘텐츠 검사](https://docs.microsoft.com/cloud-app-security/content-inspection-built-in) 에 대해 자세히 알아보세요.  

**다음 DLP 통합은 지원 되지 않습니다.** 
- Microsoft Information Protection 레이블은 Office 365 및 Azure Information Protection에서 통합 레이블을 제공 합니다.  
- Microsoft 데이터 분류 서비스 (DC)와의 기본 통합
- 외부 DLP 통합  

## <a name="conditional-access-app-control"></a>조건부 액세스 앱 제어  
조직에서 Microsoft Cloud App Security 역방향 프록시 기능을 사용 하 여 사용자 세션을 실시간으로 모니터링 하 고 제어할 수 있도록 하는 Microsoft Cloud App Security 조건부 액세스 앱 제어를 사용할 수 없습니다.   
API에 연결 된 응용 프로그램에 대해서는 활동, 파일 및 변칙 검색 정책이 계속 지원 됩니다. 추가 정보는 [Microsoft Cloud App Security에서 정책을 사용 하 여 클라우드 앱 제어](https://docs.microsoft.com/cloud-app-security/control-cloud-apps-with-policies) 에 대해 자세히 알아보세요.   

## <a name="notifications-and-automation"></a>알림 및 자동화  
경고에 대 한 관리자 메일 알림과 위반이 감지 될 때 사용자에 게 전송 된 알림은 현재 지원 되지 않습니다.   

워크플로 자동화를 위한 Microsoft Flow와의 통합을 사용할 수 없습니다.

## <a name="malware-reports"></a>맬웨어 보고서 
지원 되는 앱에서 감염 된 파일에 대 한 맬웨어 보고서를 사용할 수 없습니다.  

## <a name="security-configuration-assessments"></a>보안 구성 평가 
Azure 및 AWS에 대 한 보안 구성 평가가 지원 되지 않습니다.  

## <a name="enhanced-investigation-experience"></a>향상 된 조사 환경 
향상 된 조사 환경을 제공 하기 위해 Azure Advanced Threat Protection과의 통합은 지원 되지 않습니다.  

## <a name="other-integrations"></a>기타 통합 

다음 통합을 사용할 수 없습니다.  
- Microsoft Defender Advanced Threat Protection 
- Microsoft 보안 점수의 서피싱 Microsoft Cloud App Security 컨트롤 

## <a name="next-steps"></a>다음 단계
Cloud App Security에 대해 자세히 알아보고 시작 하는 방법에 대 한 자세한 내용은 [공개 문서를 Cloud App Security](https://docs.microsoft.com/cloud-app-security/).