---
title: "디자인 고려 사항"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 639dfd46-33ea-4cfd-918d-f3d8e57645ed
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e51462f1b238f7e3b518a7a9c8042ff3ad78a5a5
ms.openlocfilehash: da1a3088b8c7d7488c0a666ab64c65b23c2fe317


---

# 디자인 고려 사항

이 문서의 BYOD 인프라 솔루션 구상에 자세히 설명되어 있는 요구 사항을 이해하면 BYOD 인프라 디자인의 요구 사항을 구현하는 데 적절한 제품 및 기술을 선택할 수 있습니다. 다음 표에는 BYOD 인프라 솔루션을 구현하는 데 사용할 수 있는 Microsoft 제품, 기술 및 서비스가 나열되어 있습니다.

이 가이드에서 설명한 BYOD 인프라 솔루션을 위한 Microsoft 제품, 기술 및 서비스용 Microsoft 제품, 기술 및 서비스는 다음과 같습니다.

## 사용자 및 장치

- Windows Server 2012 R2
- Windows 10
- 작업 공간 참여
- 장치 등록 서비스
- 장치 등록
- Wi-Fi 프로필
- 회사 포털
- HTTPS 프로토콜

## 데이터 액세스 및 보호

- Windows Server 2012 R2
- AD DS(Active Directory 도메인 서비스)
- Azure AD(Azure Active Directory)
- Azure MFA(Azure Multi-Factor Authentication).
- AD FS(Active Directory Federation Services)
- 동적 액세스 제어
- Microsoft Rights Management 서비스
- Azure  권한 관리 
- SMB 암호화
- SSO(Single Sign-On)
- 작업 폴더
- WAP(웹 응용 프로그램 프록시)

## Management

- Microsoft Intune
- 장치 관리 정책
- 통합 관리 인프라
- 선택적 초기화
- 소프트웨어 배포
- 배포 지점 사용 보고서 및 관리
- System  Center  2012  R2  Configuration  Manager

## 앱

- 웹 응용 프로그램 프록시
- 자동 트리거 VPN
- RemoteApp
- 세션 섀도
- 빠른 다시 연결
- 중복 제거 저장소
- SDL(보안 개발 수명 주기)
- AD FS(Active Directory Federation Services)
- HTTPS 프로토콜

다음 섹션에서는 디자인 프로세스에 대해 간략하게 설명하지만 이 문서의 BYOD 인프라 솔루션 구상에서 설명한 대로 디자인 및 요구 사항 정의 프로세스는 완료될 때가지 반복됩니다.
문서의 나머지 부분에서는 디자인 고려 사항과 위의 표에 나열된 제품, 기술 및 서비스에 대해 설명합니다. 여러 가지 Microsoft 제품, 기술 및 서비스를 사용하여 다양한 디자인 고려 사항을 해결할 수 있는 경우 장단점에 대해서도 설명합니다.

BYOD를 지원하는 인프라 디자인은 이전에 이 문서에서 제공된 질문과 대답 및 사용할 수 있는 기술 기능과 옵션을 종합합니다. 이 문서에서 설명하는 디자인에서는 Microsoft 기반 기술을 사용합니다. 그러나 디자인 옵션 및 고려 사항은 BYOD 모델을 포함하는 데 사용되는 모든 인프라에 적용할 수 있습니다.





<!--HONumber=Aug16_HO1-->


