---
title: "장치 프로비전 옵션"
description: "이 문서에서는 Enterprise Mobility + Security를 사용하여 Microsoft 모바일 장치 관리 솔루션을 계획하고 디자인할 때 필요한 장치 프로비전 옵션에 대한 지침을 제공합니다."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 991cd722-089c-4e8c-80b9-b82e405cc891
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 3df9be3ef643303f4205aa1b6daf18fdf53762d8


---

# <a name="device-provisioning-options"></a>장치 프로비전 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

사용자가 본인의 장치를 사용 및 등록할 수 있으면 사용자 및 IT 부서의 요구 사항이 증가하고 여러 영역에 영향을 주게 됩니다. 예를 들어 아래 표에서는 Intune 및 ConfigMgr를 둘 다 사용하는 조직의 등록 프로세스를 대략적으로 보여 줍니다. 이 예에서는 솔루션을 계획할 때 고려해야 하는 인증서, 웹 응용 프로그램 및 동기화 문제를 설명합니다.

![하이브리드 Intune 및 ConfigMgr를 사용하는 모바일 장치 등록 프로세스 개요](./media/MDM_Figure_04.png)

**하이브리드 Intune 및 ConfigMgr를 사용하는 모바일 장치 등록 프로세스 개요**

1. <token>Windows Server 2012 R2에서는 장치 등록이라는 새로운 개념이 도입되었습니다.  사용자는 Single Sign-On에 맞게 장치를 등록하고 작업 공간 연결을 사용하여 회사 데이터에 액세스할 수 있습니다.  이 등록 프로세스의 일부로 인증서가 장치에 설치됩니다. 그런 후 사용자는 장치를 등록하고 장치 관리 솔루션에 알리기 위해 이전에는 도메인에 연결된 PC 외부에서 사용할 수 없었던 회사 리소스에 대한 액세스 권한을 얻습니다.
2. 사용자는 [회사 포털을 통해](/Intune/deploy-use/enroll-devices-in-microsoft-intune) Intune을 사용한 관리를 위해 장치를 구성하는 장치를 등록한 후, Microsoft Intune 회사 포털을 통해 회사 응용 프로그램 및 데이터에 쉽게 액세스하고, 자신의 장치를 관리할 수 있고, 분실, 도난 또는 교체 시 장치를 원격으로 초기화하는 등의 작업을 수행하기 위해 Microsoft Intune 회사 포털을 활용할 수 있습니다.
3. 장치 인식(등록) 및 사용자 ID에 따라 Windows Server 2012 R2의 [웹 응용 프로그램 프록시](https://technet.microsoft.com/library/dn584107.aspx)라는 기본 제공 기능을 사용하여 회사 리소스에 대한 액세스 권한을 게시할 수 있습니다. Enterprise Mobility + Security를 사용할 경우 Azure AD 응용 프로그램 프록시를 통해 응용 프로그램을 게시할 수도 있습니다. 다단계 인증은 [Azure 활성 인증](https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/)을 통해 사용할 수 있습니다.
4. 관리자에게 전체 환경에 대한 통합된 보기를 제공하기 위해 Intune의 데이터는 온-프레미스와 클라우드 모두에서 통합된 관리를 제공하는 ConfigMgr와 동기화됩니다.
5. 등록 프로세스의 일부로 Active Directory에서 새 장치 개체가 만들어집니다.  이 장치 개체는 사용자와 장치를 연결하고, 장치 관리 솔루션에 알리고, 장치가 원활한 2단계 인증을 통해 효과적으로 인증될 수 있도록 합니다.

1단계의 질문에 대한 답변에 따라, 모바일 장치 관리 솔루션에서 장치를 관리하는 방식을 결정할 수 있습니다. 아래 목록에서는 각 프로비전 옵션의 장단점을 보여 줍니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

**장점**

- 모든 주요 모바일 장치 운영 체제(Android, iOS, Windows 10, Windows 8.x, 및 Windows Phone)의 등록 및 프로비전 지원
- 클라우드 기반 서비스, 모바일 장치를 인터넷에 연결된 모든 위치에서 등록할 수 있음
- 중앙 집중식 사용자 지정 가능 회사 포털을 통해 장치를 등록할 수 있음
- 모바일 장치를 위한 고급 장치 프로비전 옵션

**단점**

- 비모바일 장치에 대해 온-프레미스 관리 플랫폼을 사용하는 경우에만 모바일 장치를 프로비전하기 위한 추가 관리 인터페이스 필요
- 클라우드 기반 서비스 및 온-프레미스 관리 플랫폼에 대한 별도의 장치 규정 준수 및 보안 정책 제공

## <a name="mdm-for-office-365"></a>Office 365용 MDM

**장점**

- Office 365 테넌트와 통합하여 모바일 장치와 Office 365 테넌트 서비스를 위한 단일 관리 콘솔 제공(Exchange Online, SharePoint Online 및 Skype for Business)
- 모든 주요 모바일 장치 운영 체제(Android, iOS, Windows 10, Windows 8.1 및 Windows Phone)의 등록 및 프로비전 지원
- 모바일 장치에 대한 기본 장치 프로비저닝 옵션

**단점**

- 비모바일 장치에 대해 온-프레미스 관리 플랫폼을 사용하는 경우에만 모바일 장치를 프로비전하기 위한 추가 관리 인터페이스 필요
- 클라우드 기반 서비스 및 온-프레미스 관리 플랫폼에 대한 별도의 장치 규정 준수 및 보안 정책 제공
- 좀 더 간단한 장치 프로비저닝 옵션

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- Intune(클라우드 기반 장치 관리 서비스)와 System Center 2012 Configuration Manager 및 System Center 2012 R2 Configuration Manager(온-프레미스 장치 관리 플랫폼) 기본 통합
- 모든 주요 모바일 장치 운영 체제(Android, iOS 및 Windows Phone)의 등록과 프로비저닝을 지원하며 모든 주요 비모바일 장치 운영 체제에 대한 프로비저닝 포함
- Intune 연결을 통해 모바일 장치에 대한 고급 장치 프로비저닝 옵션 지원

**단점**

- 현재 ConfigMgr 인프라가 구성되지 않은 조직의 경우 Intune과 통합하기 전에 계획, 설치 및 구성이 필요합니다.
- Intune을 온-프레미스 ConfigMgr 인프라와 연결하기 위한 추가적인 구성이 필요합니다.

Intune에서 [모바일 장치 등록을 사용하도록 설정](/Intune/deploy-use/enroll-devices-in-microsoft-intune)하는 방법을 검토하고 모바일 장치 등록 및 프로비저닝 옵션을 자세히 알아보고, 이러한 요구 사항 및 절차를 비교하여 ConfigMgr 및 MDM for Office 365 [모바일 장치 등록을 사용하도록 설정](https://technet.microsoft.com/library/jj884158.aspx)해야 합니다.



<!--HONumber=Nov16_HO4-->


