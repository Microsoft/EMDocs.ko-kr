---
title: 원본 환경 요구 사항
description: EMS용 FastTrack 센터 혜택을 사용하기 위한 원본 환경 요구 사항
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: beee0fe5a4b0907b6584f22d9c2a9967f83e5161
ms.sourcegitcommit: ffa46a69834de317e99a58146492e06c6aa4901a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="source-environment-expectations"></a>원본 환경 요구 사항

조직에서 [EMS(Enterprise Mobility + Security)용 FastTrack 센터 혜택](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)을 통해 사용할 준비가 된 Microsoft Azure Active Directory Premium 및 Microsoft Intune을 가져올 때는 사용자 환경이 다음 섹션에서 설명하는 기대 사항에 부합해야 합니다.

단일 콘솔에서 풍부한 ID 관리를 활용하기 위해 EMS 또는 개별 서비스에 통합하려 환경에 온-프레미스 Active Directory가 이미 있을 수도 있습니다. EMS용 FastTrack 센터 혜택은 Azure Active Directory를 기존 온-프레미스 Active Directory 환경과 통합하는 데 도움을 줍니다.

다음 표에서는 등록 시 기존 원본 환경에 대해 요구되는 사항을 보여 줍니다.

|활동|원본 환경 기대|
|------------|----------------------------------|
|코어 등록|기능적 포리스트 수준이 Windows Server 2008 이상으로 설정되어 있고 다음 포리스트 구성을 사용하는 Active Directory 포리스트:<br /><br />- 단일 Active Directory 포리스트<br />- 다중 Active Directory 포리스트 </br></br>**참고**: 모든 다중 포리스트 구성의 경우, AD FS(Active Directory Federation Services) 배포는 모든 다중 포리스트 구성에 대 한 FastTrack 센터 혜택에 대 한 범위를 벗어납니다.|
|Azure AD Premium 등록|온-프레미스 Active Directory 및 환경은 Azure AD Premium을 위해 준비되어 있으며, Azure AD 및 Azure AD Premium 기능과의 통합을 방지하는 식별된 문제 수정이 포함되어 있습니다.|
|Intune, 클라우드만 또는System Center Configuration Manager와 통합, 등록|Intune과 연결된 Configuration Manager 2012 R2 이상을 사용하여 장치를 관리하려면 IT 관리자가 [관리자 검사 목록: Microsoft Intune을 사용하여 모바일 장치를 관리하도록 Configuration Manager 구성](https://technet.microsoft.com/library/jj943763.aspx)을 수행해야 합니다.</br></br> **참고**: 서비스 혜택에는 Configuration Manager와 통합된 Microsoft Intune에 필요한 최소 요구 사항에 맞게 Configuration Manager를 설정 또는 업그레이드하기 위한 지원이 포함되어 있지 않습니다.</br></br>Wi-Fi 및 VPN 프로필 배포의 경우 IT 관리자는 기존 인증 기관, Wi-Fi 및 VPN 인프라가 프로덕션 환경에서 이미 작업 중인 상태로 설정해야 합니다.</br></br> **참고**: 서비스 혜택에는 인증 기관, Wi-Fi 또는 VPN 인프라 구성 또는 설치 지원이 포함되지 않습니다. |

> [!NOTE]
> **자세히 알아보고 싶습니까?**
> [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility)

## <a name="next-steps"></a>다음 단계

[EMS용 FastTrack 센터 혜택 온보딩 및 마이그레이션 단계](fasttrack-center-benefit-process-for-ems-phases.md)
