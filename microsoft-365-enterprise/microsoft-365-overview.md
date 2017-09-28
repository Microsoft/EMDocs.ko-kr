---
title: Microsoft 365 Enterprise | Microsoft docs
description: "개요를 제공하고 Microsoft 365 Enterprise 서비스를 설명합니다."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/15/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 14f22a558e2e437f1491033eb33858b377eeca9d
ms.sourcegitcommit: 3ce5a7e7e86e286f2b82a970d7f0c8e6ff3028f3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2017
---
# <a name="microsoft-365-enterprise-overview"></a>Microsoft 365 Enterprise 개요
Microsoft 365 Enterprise는 대규모 조직을 위해 설계되었으며 Office 365 Enterprise, Window s 10 Enterprise 및 EMS(Enterprise Mobility + Security)와 통합하여 모든 사용자가 독창적이고 안전하게 함께 작업할 수 있도록 합니다. Microsoft 365 Enterprise에는 Windows 10 엔터프라이즈 버전 및 Office 365 ProPlus를 통한 Office 응용 프로그램이 포함됩니다.

Windows 10 및 Office 365 ProPlus 모두 3월과 9월에 새 기능 릴리스를 반기 채널을 통해 엔터프라이즈에 제공합니다. 반기 채널의 기능 릴리스는 18개월 동안 지원됩니다. Microsoft Intune 및 System Center Configuration Manager 모두 Windows 10과 Office 365 ProPlus를 배포하고 업데이트하는 기능을 제공합니다.

이 단원에서는 Microsoft 365 Enterprise에 포함된 EMS 및 Office 365 서비스에 대한 개요를 제공하고 조직의 필요에 따라 가장 잘 활용하는 방법을 이해하는 데 필요한 핵심 개념도 소개합니다. 이러한 서비스는 Microsoft 클라우드 엔터프라이즈 관리자가 회사 직원의 ID와 장치를 보호할 뿐만 아니라 회사 데이터(전송 중인 데이터 및 미사용 데이터 둘 다) 자체에 대한 액세스도 제어할 수 있는 기능을 제공합니다.

|서비스|설명|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD는 다단계 인증, 장치 등록, 셀프 서비스 암호 관리, 셀프 서비스 그룹 관리, 역할 기반 액세스 제어, 응용 프로그램 사용 모니터링, 다양한 감사, 보안 모니터링 및 경고 등 전체 ID 관리 기능을 제공합니다.|
|[Azure AD ID 보호](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|이 서비스를 사용하면 조직의 ID에 영향을 미치는 잠재적인 취약점을 검색하고 낮음, 보통 및 높음 로그인 위험 및 사용자 위험에 대해 조건부 액세스 정책을 통해 자동화된 응답을 구성할 수 있습니다.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|이 서비스를 사용하면 조직은 권한 있는 작업에 영구 액세스 권한이 있는 사용자 수를 최소화할 수 있습니다. Azure AD Privileged Identity Management는 적격 관리자 개념을 소개합니다. 적격 관리자는 매일이 아니라 가끔 권한 있는 액세스가 필요한 사용자여야 합니다. 역할은 사용자가 액세스를 필요로 할 때까지 비활성화 상태이다가 활성화 프로세스를 완료하면 미리 결정된 시간 동안 활성 관리자가 됩니다.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection은 EMS E5 제품의 일환으로 제공되는 클라우드 기반 솔루션으로 조직에서 문서와 메일을 분류하고 레이블을 지정하며 보호하는 데 도움이 됩니다. 이 기능은 규칙 및 조건을 정의하는 관리자는 자동으로, 사용자는 수동으로 수행할 수 있으며, 사용자가 권장 사항을 제공받은 경우에는 자동 또는 수동으로 수행할 수 있습니다. Azure Information Protection 레이블을 사용하여 문서와 전자 메일을 분류할 수 있습니다. 이 작업을 수행하면 데이터가 저장된 위치나 데이터를 공유한 사용자가 누구인지와 관계없이 항상 분류를 식별할 수 있게 됩니다. <br><br>Azure Information Protection 정책 설정은 [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)로 보호됩니다. 레이블이 적용되는 방법과 마찬가지로 Rights Management를 사용하여 적용된 보호 기능은 조직, 네트워크, 파일 서버, 응용 프로그램 내/외의 위치와 관계없이 문서와 메일에 계속 적용됩니다.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune은 직원이 회사 데이터를 보호하면서 생산성을 높일 수 있도록 하는 클라우드 기반 엔터프라이즈 이동성 관리(EMM) 서비스입니다. Intune은 ID 및 액세스 제어에 대해 Azure AD와 긴밀하게 통합되며 장치 및 응용 프로그램 관리에 사용됩니다. [Intune의 장치 관리](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) 기능은 Windows PC를 비롯하여 사용자의 장치를 구성하고 보호하는 데 사용됩니다. <br><br>Intune 장치 관리 기능은 사용자가 개인 휴대폰, 태블릿 또는 PC를 등록할 수 있는 [BYOD(Bring Your Own Device)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 등록과 자동 등록, 공유 장치 또는 사전 승인된 등록 요구 사항 구성 같은 관리 시나리오를 사용할 수 있는 [COD(회사 소유 장치)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 등록을 모두 지원합니다. 추가 보안을 위해 장치를 등록하려면 MFA가 필요할 수 있습니다. 관리로 등록되면 Intune은 장치 기능 및 설정을 구성하여 회사 리소스에 대해 보안 액세스를 사용할 수 있습니다.|


다음은 Windows 10, Office 365 ProPlus, Microsoft Intune 및 System Center Configuration Manager의 최신 버전입니다.

|     |**반기 채널(대상 지정)**|**반기 채널**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update(출시 예정)|버전 1703|
|**Office 365 ProPlus**|버전 1708|버전 1705|
|**Intune**|해당 없음|버전 1708|
|**System Center Configuration Manager**|기술 미리 보기 버전 1708|버전 1706<sup>*</sup>|

<sup>*</sup> System Center Configuration Manager 현재 분기의 업데이트 1706은 버전 1606, 1610 또는 1702를 실행하는 이전에 설치된 사이트에 대한 콘솔 내 업데이트로 제공됩니다.

> [!NOTE]
> Microsoft Azure 서비스도 정기적으로 업데이트되지만 버전 번호에서 참조되지 않습니다. Azure 서비스의 최신 업데이트와 향후 예정 사항을 검토하려면 [클라우드 플랫폼 로드맵](https://www.microsoft.com/cloud-platform/roadmap)을 참조하세요.

이러한 버전에서 사용할 수 있는 기능에 대한 자세한 내용은 다음 문서를 참조하세요.
- [Windows 10의 새로운 기능](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10 릴리스 정보](https://technet.microsoft.com/windows/release-info)
- [Windows 10 업데이트 기록](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365 클라이언트 업데이트 채널 릴리스](https://technet.microsoft.com/office/mt465751)
- [Microsoft Intune의 새로운 기능](https://docs.microsoft.com/intune/whats-new)
- [System Center Configuration Manager의 새로운 기능](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [System Center Configuration Manager용 기술 미리 보기 1708의 기능](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="security-best-practices-and-recommendations"></a>보안 모범 사례 및 권장 사항
모든 고객 환경에 꼭 맞는 단일 권장 사항은 없지만 [권장 보안 정책 및 구성](microsoft-365-policies-configurations.md) 문서에서는 이해가 필요한 중요 보안 모범 사례 개념을 소개합니다. 또한 직원들의 보안과 생산성을 모두 유지하기 위해 Microsoft 클라우드 내에서 정책 및 구성을 적용하는 방법에 대한 일반적인 Microsoft 권장 사항에 대해서도 다룹니다.


## <a name="deploy-windows-10-and-office-365-proplus"></a>Windows 10 및 Office 365 ProPlus 배포
Windows 10 및 Office 365 ProPlus를 배포하고 Microsoft Azure AD(Azure Active Directory) 또는 온-프레미스 AD DS(Active Directory Domain Services)에 통합하는 방법을 알아보세요. Windows 10, Office 365 ProPlus 및 다른 기간 업무 앱을 새 장치에 배포하거나 Intune, System Center Configuration Manager 및 그룹 정책을 사용하여 기존 장치를 Windows 10으로 업그레이드하고 장치를 관리하세요.

자세한 내용은 다음 문서를 참조하십시오.
- [Windows 10 배포 고려 사항](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Office 365 ProPlus의 배포 가이드](https://support.office.com/article/f99f8cd0-e648-4834-8f45-f5637351899d)
- [엔터프라이즈에서 Office 365 ProPlus를 배포하는 모범 사례 가이드](https://support.office.com/article/31a384ca-650c-4265-b76c-a87b414fd8b8)
- [Intune을 사용하여 Office 365 ProPlus 앱을 Windows 10 장치에 배포](https://docs.microsoft.com/intune/apps-add-office365)

Microsoft 365를 통한 배포 지원은 [FastTrack에 문의하세요](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Windows 10 및 Office 365 ProPlus로의 업데이트 관리
다음 링크에서는 Windows 10 및 Office 365 ProPlus의 품질과 기능 업데이트를 최대한 제어할 수 있는 방법을 소개합니다. 대역폭 사용량을 효율적으로 제어하고 최신 기능, 기능 및 보안 업데이트를 통해 Windows 및 Office를 최신 상태로 유지하는 방법을 알아보세요.

자세한 내용은 다음 문서를 참조하십시오.
- [Windows as a service 개요](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Office 365 ProPlus의 업데이트 채널 개요](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
- [Intune을 통한 소프트웨어 업데이트 관리](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [System Center Configuration Manager를 사용하여 Windows 10 업데이트 배포](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Configuration Manager를 사용하여 Office 365 ProPlus 관리](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft는 Windows 업데이트 관리를 위해 현재 Configuration Manager를 사용하는 조직이 Windows 10 클라이언트 컴퓨터에 대해서도 계속 동일한 작업을 수행하도록 권장합니다.

## <a name="next-steps"></a>다음 단계
[Microsoft 365 Enterprise 서비스에 대한 자세한 정보](services-overview.md)

[Microsoft 365 Enterprise 제품 페이지](https://www.microsoft.com/microsoft-365/enterprise)

[클라우드 플랫폼 로드맵](https://www.microsoft.com/cloud-platform/roadmap)

