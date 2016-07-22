---
title: "SaaS 연결 요구 사항 식별"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 6afbce4c-7500-4387-a19c-dff52c152097
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: d5e660e87a80b7703a09214b1d1f07e41e8f5483


---

# SaaS 연결 요구 사항 식별

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

온-프레미스 인프라를 연결하는 방법은 MDM 솔루션(Intune, MDM for Office 365 및 하이브리드 Intune 및 ConfigMgr 배포)에서 사용자 및 장치 ID가 관리되는 방식에 영향을 줍니다. Intune 및 MDM for Office 365 모두 Azure Active Directory 서비스에서 제공하는 디렉터리 서비스 아키텍처를 사용합니다. 이와 같이 Azure와 통합할 경우 모바일 장치 관리 솔루션에서 아주 유연하게 ID 관리 지원을 설계할 수 있습니다.

아래 목록과 같이 온-프레미스 디렉터리 서비스를 Azure에 연결하는 작업은 SSO(Single Sign-On) 및 통합 디렉터리 계정 관리를 사용하기 위해 반드시 필요합니다. SSO(Single Sign-On)를 사용하면 사용자는 온-프레미스 및 클라우드의 회사 리소스에 훨씬 더 쉽게 연결할 수 있습니다. 단일 위치에서 계정을 관리할 수 있으므로 관리자는 편리하게 작업할 수 있습니다. 모바일 액세스의 경우, Azure와 온-프레미스 디렉터리 서비스 간에 디렉터리 계정 특성 및 자격 증명이 동기화되므로 사용자는 모바일 장치에서 인증을 받아 MDM for Office 365 또는 Intune에서 관리되는 리소스에 액세스할 수 있습니다.

![통합 ID 관리 개요](./media/MDM_Figure_15.png)

**통합 ID 관리 개요**

작업 2의 질문에 대한 답변에 따라, SaaS 솔루션이 모바일 장치 관리 솔루션을 위해 어떤 방법으로 온-프레미스 클라이언트 관리 플랫폼에 연결해야 하는지를 확인할 수 있습니다. 아래 목록은 온-프레미스 인프라를 SaaS 솔루션에 연결할 때의 장단점을 이해하는 데 도움이 됩니다.

## Intune(독립 실행형)

**장점**

- 사용자 및 장치 ID와 인증을 관리하기 위해 Azure Active Directory와 긴밀하게 통합됨
- 기존 온-프레미스 계정 자격 증명을 활용할 수 있는 사용자 자격 증명 자체 관리 및 Single Sign-On 환경 지원
- 수천 개의 미리 통합된 SaaS 응용 프로그램에 대한 Single Sign-On 액세스 지원
- 온-프레미스 및 클라우드 응용 프로그램 둘 다에 대해 규칙 기반의 MFA(다단계 인증)를 적용하여 응용 프로그램 액세스 보안 지원

**단점**

- 고급 디렉터리 서비스 연결 기능을 사용하기 위해 Azure Active Directory Premium에 연결해야 함

## Office 365용 MDM

**장점**

- 사용자 및 장치 ID와 인증을 관리하기 위해 Azure Active Directory 백본을 사용하는 Office 365 테넌트와 통합됨
- 온-프레미스 디렉터리 서비스를 Office 365와의 서비스 연결 일부로 연결할 수 있음
- 기존 온-프레미스 계정 자격 증명을 활용할 수 있는 사용자 자체 관리 및 Single Sign-On 환경 지원
- Azure MFA 서비스를 사용하여 장치 등록에서의 다단계 인증 지원

**단점**

- 다른 SaaS 솔루션 또는 응용 프로그램과의 모바일 응용 프로그램 관리 통합을 지원하지 않음

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점 및 다음 장점
 - ConfigMgr 인프라를 통해 온-프레미스 디렉터리 서비스와 직접 통합

**단점**

- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성이 필요합니다.
- ConfigMgr를 사용하는 조직의 경우 추가 온-프레미스 배포 요구 사항 및 구성 변경이 필요함


<!--HONumber=Jul16_HO3-->


