---
title: "리소스에 대한 액세스 제어"
description: "이 문서에서는 모바일 장치 관리 시나리오에 사용 해야 하는 액세스 제어에 대한 다양한 디자인 고려 사항을 제공합니다."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5967876b-3c08-4498-a0a6-0225b562d35f
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 782f6dac4a366312ce0a6d04735262908df6fe72
ms.contentlocale: ko-kr
ms.lasthandoff: 11/28/2016


---

# <a name="access-control-to-resources"></a>리소스에 대한 액세스 제어

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

이미 Active Directory를 사용하여 사용자를 인증하고 권한을 부여하는 조직은 Active Directory의 그룹을 사용하여 리소스에 대한 액세스를 분할하고 제어하는 방식으로 특정 리소스에 대한 액세스 제어를 관리합니다.  

특정 리소스에 대한 제어를 관리하려면 먼저 사용자의 액세스 권한을 인증하고 부여한 다음 사용자가 대상 리소스에 대해 갖는 제어 권한 유형이 유효한지 확인합니다. 아래 그림에서는 폴더에 액세스하는 사용자 Bob에 대해 이 정보가 표시됩니다.

![인증 흐름](./media/MDM_Figure_13.png)

## <a name="basic-authentication-and-authorization-flow"></a>기본 인증 및 권한 부여 흐름

기존 ACL(액세스 제어 목록)은 매우 제한적이며, 사용자가 이 리소스에 액세스 하려고 할 때의 위치와 같은 사용자 상태의 다른 측면을 고려하지 않습니다. 조직에서 리소스에 대한 액세스 권한을 부여하기 전에 좀 더 다양한 요인을 고려해야 할 경우 Windows Server 2012에서 기본적으로 사용할 수 있는 [동적 액세스 제어](https://technet.microsoft.com/library/dn408191.aspx)를 사용할 수 있습니다. Windows 10에서는 데이터에 대한 액세스를 제공하기 전에 IT에서 장치의 상태를 확인할 수 있는 상태 증명을 지원합니다. 원격 상태 증명 서비스에서는 측정값에 대한 여러 검사를 수행합니다. 부팅 상태(보안 부팅, 디버그 모드 등)와, 보안을 관리하는 구성 요소(BitLocker, Device Guard 등)의 상태를 포함하여 보안 관련 데이터 포인트의 유효성을 검사합니다. 그런 다음 상태 암호화 Blob를 장치로 다시 전송하여 장치의 상태를 전달합니다. 자세한 내용은 [Windows 10 기반 장치의 상태 제어](https://technet.microsoft.com/library/mt592023.aspx)를 읽어보세요.

Intune 관리자가 [Intune 관리 콘솔](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)에서 Windows 10 디바이스 상태 증명의 상태를 볼 수 있습니다. 디바이스 상태 증명을 사용하여 관리자는 클라이언트 컴퓨터가 신뢰할 수 있는 BIOS, TPM 및 소프트웨어 구성을 갖는지 확인할 수 있습니다. 디바이스 상태 증명을 지원하려면 클라이언트 장치에서 TPM 2가 설정된 Windows 10이 실행되고 있어야 합니다.

많은 회사들이 사설 클라우드를 유지하도록 허용하는 기술을 사용하여 자체적으로 클라우드 공급자 역할을 하고 있으므로 RBAC(역할 기반 액세스 제어)를 사용할 수도 있습니다. [Azure AD에서는 IT가 RBAC](http://azure.microsoft.com/documentation/articles/role-based-access-control-configure/)를 사용하여 리소스 액세스를 제어할 수 있습니다. 또한 Azure AD를 온-프레미스 Active Directory와 통합할 수 있으므로 둘을 함께 사용하여 사용자가 리소스에 액세스하는 방식을 판단할 수 있습니다.

리소스가 앱일 수도 있습니다. 즉, 리소스에 대한 액세스 제어를 구현하려면 MDM 솔루션에서 앱이 설치 및 액세스되는 방식을 제어할 수 있어야 합니다. [Intune의 모바일 응용 프로그램 관리 정책](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)을 사용하여 배포하는 앱의 기능을 회사의 규정 준수 및 보안 정책에 부합하게 수정할 수 있습니다.

아래 표를 참조하면 조직의 액세스 제어 요구 사항에 가장 잘 맞는 MDM 옵션을 선택하는 데 도움이 될 것입니다.

## <a name="intune-standalone"></a>Intune(독립 실행형)

**장점**

- 앱에 대한 액세스 제어(설치 및 관리)
- 상태 증명 서비스를 사용한 조건부 액세스

**단점**

- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 사용할 수 있는 추가 관리 인터페이스가 제공됨
- 일부 모바일 플랫폼에서 일부 정책을 사용할 수 없음

## <a name="mdm-for-office-365"></a>Office 365용 MDM

**장점**

- 메일, Office Mobile 및 Office 앱, 비즈니스용 OneDrive에 대한 액세스 제어

**단점**

- 리소스에 대해 부분적인 액세스 제어만 허용
- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 사용할 수 있는 추가 관리 인터페이스가 제공됨
- 일부 모바일 플랫폼에서 일부 정책을 사용할 수 없음

## <a name="hybrid-intune-with-configmgr"></a>하이브리드(ConfigMgr와 Intune)

**장점**

- 앱에 대한 액세스 제어(설치 및 관리)
- 상태 증명 서비스를 사용한 조건부 액세스

**단점**

- Intune 구독 구입 시 Azure AD 클라우드 서비스가 포함되지 않음

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security

**장점**

- 앱에 대한 액세스 제어(설치 및 관리)
- Azure AD Premium을 사용하여 RBAC 기반 액세스 제어 제공
- 상태 증명 서비스를 사용한 조건부 액세스

**단점**

- 조직에 최신 온-프레미스 ConfigMgr 인프라가 없는 경우 통합 전에 이 플랫폼의 계획, 설치 및 구성 필요

