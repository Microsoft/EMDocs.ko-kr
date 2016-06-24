---
# required metadata

title: Enterprise Mobility Suite에 대한 FastTrack 센터 혜택 프로세스 - 원본 환경 기대 사항
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Enterprise Mobility Suite에 대한 FastTrack 센터 혜택 프로세스 - 원본 환경 기대 사항
조직에서 [EMS(Enterprise Mobility Suite)에 대한 FastTrack 센터 혜택](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)을 사용하여 Azure Active Directory Premium, Microsoft Intune 및/또는 Azure Rights Management를 가져올 때는 사용자 환경이 다음 섹션에서 설명하는 기대 사항에 부합해야 합니다.

FastTrack 등록 프로세스의 다른 부분에 대한 자세한 내용은 [EMS(Enterprise Mobility Suite)에 대한 FastTrack Center 혜택 프로세스](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md)를 참조하세요.

단일 콘솔에서 풍부한 ID 관리를 활용하기 위해 EMS 또는 개별 서비스에 통합하기를 원하는 현재 환경에 Microsoft Active Directory 온-프레미스가 이미 있을 수도 있습니다. FastTrack 센터 혜택으로 Microsoft Active Directory Premium을 기존 온-프레미스 구현과 통합하는 데 도움을 드립니다. 통합이 필요한 경우 원본 환경이 해당 응용 프로그램에 대해 최소 수준이어야 합니다.

다음 표에서는 기존 원본 환경에서 등록에 대해 기대되는 사항을 보여 줍니다.

|활동|원본 환경 기대|
|------------|----------------------------------|
|코어 등록|기능적 포리스트 수준이 Windows Server 2008 이상으로 설정되어 있고 다음 포리스트 구성을 사용하는 Active Directory 포리스트:<br /><br />- 단일 Active Directory 포리스트<br />- 다중 Active Directory 포리스트 </br></br>**참고**: 모든 다중 포리스트 구성의 경우, AD FS 배포는 FastTrack 센터 혜택의 범위에 속하지 않습니다.|
|Microsoft Azure Active Directory Premium 등록|온-프레미스 Active Directory 및 환경은 Azure Active Directory Premium을 위해 준비되어 있으며, Azure Active Directory 및 Azure Active Directory Premium 기능과의 통합을 방지하는 식별된 문제 수정이 포함되어 있습니다.|
|Microsoft Intune, 클라우드만 또는System Center Configuration Manager와 통합, 등록|IT 관리자는 Microsoft Intune과 연결된 System Center Configuration Manager 2012 R2 이상 버전을 사용하여 장치를 관리하려면 [관리자 검사 목록: Microsoft Intune을 사용하여 모바일 장치를 관리하도록 Configuration Manager 구성](https://technet.microsoft.com/library/jj943763.aspx)을 따라야 합니다.</br></br> **참고**: 서비스 혜택에는 System Center Configuration Manager와 통합된 Microsoft Intune에 필요한 최소 요구 사항에 맞게 System Center Configuration Manager를 설정 또는 업그레이드하기 위한 지원은 포함되어 있지 않습니다.|

FastTrack 온보딩 프로세스의 다음 부분인 [온보딩 프로세스의 단계](fasttrack-center-benefit-process-for-ems-phases.md)를 읽어 보세요.

### 더 자세한 내용을 원하세요?
[Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 참조하세요.



<!--HONumber=Jun16_HO1-->


