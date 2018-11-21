---
title: 원본 환경 요구 사항
description: EMS용 FastTrack 센터 혜택을 사용하기 위한 원본 환경 요구 사항
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 65b7b77bb0afafc019c44c2fb980c18ee782471a
ms.sourcegitcommit: 06c39d619052a609c250b8b3978d9061841a6ff2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2018
ms.locfileid: "51859229"
---
# <a name="source-environment-expectations"></a>원본 환경 요구 사항

조직에서 [EMS(Enterprise Mobility + Security)용 FastTrack 센터 혜택](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md)을 통해 사용할 준비가 된 Microsoft Azure Active Directory Premium 및 Microsoft Intune을 가져올 때는 사용자 환경이 다음 섹션에서 설명하는 기대 사항에 부합해야 합니다.

단일 콘솔에서 다양한 ID 관리를 사용하는 EMS(Enterprise Mobility + Security) 또는 개별 서비스와 통합하려는 조직에 온-프레미스 Active Directory가 이미 있을 수 있습니다. EMS(Enterprise Mobility + Security)용 FastTrack Center 혜택은 Azure Active Directory를 기존 온-프레미스 Active Directory 환경과 통합하는 데 도움을 줍니다.

다음 표는 등록 시 기존 원본 환경에 대해 요구되는 사항을 보여 줍니다.

|활동|원본 환경 기대|
|------------|----------------------------------|
|Core 온보딩|기능적 포리스트 수준이 Windows Server 2008 이상으로 설정되어 있고 다음 포리스트 구성을 사용하는 Active Directory 포리스트:<br /><br />- 단일 Active Directory 포리스트<br />- 다중 Active Directory 포리스트 </br></br>**참고**: 모든 다중 포리스트 구성의 경우, AD FS(Active Directory Federation Services) 배포는 모든 다중 포리스트 구성에 대 한 FastTrack 센터 혜택에 대 한 범위를 벗어납니다.|
|Azure AD Premium 등록|온-프레미스 Active Directory 및 환경은 Azure AD Premium을 위해 준비되어 있으며, Azure AD 및 Azure AD Premium 기능과의 통합을 방지하는 식별된 문제 수정이 포함되어 있습니다.|
|Intune 온보딩| Intune으로 Wi-Fi 및 VPN 프로필 배포 계획을 세울 때 IT 관리자는 기존 인증 기관, Wi-Fi 및 VPN 인프라가 프로덕션 환경에서 이미 작동하고 있어야 합니다.<br /><br /> **참고**: 서비스 혜택에는 인증 기관, WiFi, VPN 인프라 또는 Apple MDM 푸시 인증서 등의 설정 또는 구성에 대한 지원이 포함되지 않습니다.  |
|공동 관리|공동 관리를 통해 IT 관리자는 온-프레미스 환경 준비를 담당하며, 여기에는 Configuration Manager와 Intune을 둘 다 사용하여 Windows 10 디바이스를 동시에 관리할 수 없는 문제의 해결이 포함될 수 있습니다.<br /><br />**참고**: FastTrack 서비스 혜택에는 Configuration Manager 사이트 서버 및/또는 구성 관리자 클라이언트를 Windows 10 디바이스로 공동 관리를 지원하는 데 필요한 최소 요구 사항에 맞게 설정하거나 업그레이드하는 작업에 대한 지원은 포함되지 않습니다. |
|Windows Defender ATP(Windows Defender Advanced Threat Protection)와 통합된 Intune|Windows Defender ATP 구독은 회사 보안 요구 사항을 기반으로 활성화되고 구성되었습니다.<br /><br />**참고**: FastTrack 서비스 혜택은 Intune을 Windows Defender ATP와 통합하고 Windows 10 위험 수준 평가를 기반으로 장치 준수 정책을 만드는 기능에 대한 지원을 제공합니다. FastTrack 서비스 혜택은 Windows Defender ATP 및 해당 Security Center 콘솔을 구매, 라이선싱, 활성화 또는 사용하는 기능을 지원하지 않습니다. |
|Windows Autopilot|IT 관리자는 IT 관리자를 대신하여 하드웨어 공급업체가 하드웨어 ID를 업로드하도록 하거나 Windows Autopilot 서비스로 하드웨어 ID를 업로드하여 조직에 디바이스를 등록하는 일을 담당합니다. |
|Intune에서 안전하게 iOS 및 Android용 Outlook 배포|<br /><br />-   Office 365용 Azure AD에서 사용하도록 설정된 사용자 ID.<br />-   할당된 사용자 라이선스로 구성된 Exchange Online 또는 Hybrid Exchange.<br />|

> [!NOTE]
> **자세히 알아보고 싶습니까?**
> [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility)

## <a name="next-steps"></a>다음 단계

[EMS용 FastTrack 센터 혜택 온보딩 및 마이그레이션 단계](fasttrack-center-benefit-process-for-ems-phases.md)
