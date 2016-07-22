---
title: "데이터 분류"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: f3486381-66d5-469a-93a3-013eaaa17c07
ms.reviewer: 
ms.suite: ems
ms.sourcegitcommit: a16e90093c7571f3c098ce815a2b70ae03c080e3
ms.openlocfilehash: b2025b8b3d976b7a14c050c095d199c5a4c73cb8


---

# 데이터 분류

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

대부분의 회사에는 [데이터 분류](http://blogs.microsoft.com/cybertrust/2014/01/28/the-importance-of-data-classification/) 정책이 이미 있으며, 모바일 장치 관리 솔루션 배포가 이 정책에 미치는 영향을 이해해야 합니다. 회사에 현재 데이터 분류 정책이 없으면 모바일 장치 관리 솔루션을 계획하면서 이 기능을 도입해야 합니다. 일부 조직에서는 [ADRMS(Active Directory Rights Management Services)](https://technet.microsoft.com/windowsserver/dd448611.aspx)를 사용하여 파일 서버 수준에서 온-프레미스 데이터 분류를 수행합니다. 일부 회사에서 사용하는 또 다른 도구는 조직이 해당 파일 서버의 데이터를 식별, 분류 및 보호하도록 도와주는 [Microsoft 데이터 분류 도구 키트](http://www.microsoft.com/download/details.aspx?id=27123)입니다. 

Office 365에서는 보호해야 하는 중요한 정보를 파악하는 데 도움이 되는 메일 데이터 자동 분류를 제공합니다. Office 365에서는 메일 흐름 처리에 통합되는 전송 규칙을 사용하여 중요한 정보를 검색합니다. 그런 다음 [DLP 기능](http://blogs.office.com/2013/10/28/office-365-compliance-controls-data-loss-prevention/)은 키워드 일치, 사전 일치, 정규식 평가, 내부 함수를 통해 신용 카드 번호에 대한 체크섬 유효성 검사와 같은 심도 깊은 콘텐츠 분석을 수행하고 메시지 본문 또는 첨부 파일 내에서 특정 콘텐츠 유형을 검색하기 위한 기타 콘텐츠 검사를 수행합니다. 

Intune 및 ConfigMgr에는 기본적으로 데이터 분류 기능이 없으므로 Azure RMS를 사용하는 클라우드 기반 분류나 ADRMS를 사용하는 온-프레미스 분류를 사용합니다. [EMS(Enterprise Mobility Suite)](http://www.microsoft.com/server-cloud/enterprise-mobility/overview.aspx)를 MDM 솔루션으로 사용할 수도 있습니다. EMS를 사용하면 데이터를 분류하는 데 사용할 수 있는 [Azure AD Premium](https://msdn.microsoft.com/library/azure/dn532272.aspx) 및 [Azure RMS](https://technet.microsoft.com/library/jj585026.aspx)에 액세스할 수 있습니다. Azure RMS를 사용하는 데이터 분류는 하이브리드 환경의 온-프레미스 관리 솔루션에 통합될 수 있습니다. 

IT에서는 Intune를 사용하여 조건부 액세스를 통해 규정에 부합하는 것으로 간주되기 위해 장치가 따라야 하는 규칙 및 설정 집합인 규정 준수 정책을 사용하여 정책에 부합할 수 있습니다. 또한 규정 준수 정책을 사용하여 조건부 액세스와 독립적으로 장치를 모니터링하고 규정 준수 문제를 관리합니다. 자세한 내용은 [Microsoft Intune 장치 규정 준수 정책 관리](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)를 읽어보세요.

아래 표를 참조하면 조직의 *데이터 분류* 요구 사항에 가장 잘 맞는 MDM 옵션을 선택하는 데 도움이 될 것입니다.

## Intune(독립 실행형)

**장점**

- 사용할 수 없음

**단점**

- 사용할 수 없음

## Office 365용 MDM

**장점**

- Exchange 전송 규칙을 사용하여 중요한 정보를 검색할 수 있음
- Compliance Center에서 [데이터 손실 방지(DLP)](https://technet.microsoft.com/library/ms.o365.cc.DLPLandingPage.aspx) 정책을 사용하여 여러 위치에서 중요한 정보 식별

**단점**

- 파일 자체에 대해 데이터 분류가 수행되지 않음 모바일 장치에 있는 파일은 제한 없이 사용할 수 있음

## 하이브리드(ConfigMgr와 Intune)

**장점**

- 사용할 수 없음

**단점**

- 사용할 수 없음

## Enterprise Mobility Suite

**장점**

- Azure RMS를 사용하여 데이터 분류 수행
- Azure RMS 구독이 EMS에 포함되어 있음
- 데이터 분류를 위해 온-프레미스 인프라가 필요하지 않음
- 기존의 온-프레미스 AD RMS 솔루션에 통합할 수 있음
- 파일 자체에 보호 기능이 있어서 파일을 다른 위치에 저장하더라도 분류 상태가 유지됨

**단점**

- 클라우드 기반 솔루션을 채택하지 않는 고객은 사용할 수 없음



<!--HONumber=Jul16_HO2-->


