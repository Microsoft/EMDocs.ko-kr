---
title: "Intune 및 Exchange Server 온-프레미스로 조건부 액세스 사용"
description: "Intune 솔루션을 사용하여 Exchange 온-프레미스를 배포합니다."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2a64e898-4c60-48bf-ae14-b05e091e0533
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: d5771b3b16e26eb909d507641eec46285e328ed6


---

# Intune을 사용하여 Exchange 온-프레미스 배포

[회사 메일 및 문서를 보호하기 위한 아키텍처 지침](architecture-guidance-for-protecting-company-email-and-documents.md)을 참고했으므로 솔루션 배포를 진행할 준비가 되었습니다.

Intune에서 모바일 장치를 직접 관리하려면 사용자가 Intune에 장치를 등록해야 합니다.

## 배포 단계
Intune 솔루션을 사용하여 Exchange 온-프레미스를 배포하려면 다음 단계를 따르세요.

### 1단계: Microsoft Intune 온-프레미스 Exchange Server 커넥터 설치 및 구성

사용자가 등록하지 않은 모바일 장치에 대해 Exchange 커넥터를 사용하여 Exchange ActiveSync 관리를 사용하도록 설정할 수 있습니다. Exchange 커넥터는 사용자를 Exchange 배포에 연결해주므로 Intune 콘솔을 통해 모바일 장치를 관리할 수 있습니다.

[온-프레미스 또는 Hosted Exchange용 Microsoft Intune On-Premises Connector 구성](/intune/deploy-use/intune-on-premises-exchange-connector)의 단계를 수행하여 Microsoft Intune Exchange Connector를 다운로드하여 설치하고 구성합니다.

> [!IMPORTANT]
> Intune 계정마다 하나의 Exchange 연결을 설정할 수 있습니다. 추가 연결을 구성하면 원래 연결이 새 연결로 바뀝니다.

### 2단계: 규정 준수 정책 만들기 및 사용자에게 배포
규정 준수 정책은 장치가 조건부 액세스 정책을 준수하는 것으로 간주되기 위해 준수해야 하는 규칙 및 설정을 정의합니다. [Microsoft Intune에서 규정 준수 정책 만들기](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune)의 단계에 따라 규정 준수 정책을 만들고 배포합니다.

더 이상 회사에 속하지 않아 iOS 장치에서 모든 회사 메일을 제거하는 기능을 원하는 경우 메일 프로필을 만들고 배포한 다음 메일 프로필이 Intune에서 관리되도록 지정하는 규정 준수 정책을 설정해야 합니다. 이 규정 준수 정책에서 대상으로 하는 사용자 집합과 동일한 사용자 집합에 메일 프로필을 배포해야 합니다.
![전자 메일 프로필을 Intune에서 관리해야 한다고 지정할 수 있는 규정 준수 정책 만들기 마법사의 "규칙" 페이지를 보여주는 스크린샷입니다.](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

이 규정 준수 정책을 지정하는 경우 이미 메일 계정을 설정한 사용자는 수동으로 해당 계정을 제거해야 하며, Intune에서 [조건부 액세스를 위한 최종 사용자 환경](end-user-experience-conditional-access.md)에 설명된 등록 프로세스를 통해 다시 추가합니다.

> [!IMPORTANT]
> 규정 준수 정책을 배포하지 않은 상태에서 Exchange 조건부 액세스 정책을 사용하도록 설정하면 대상으로 지정된 모든 장치에 액세스가 허용됩니다.

### 3단계: 조건부 액세스 정책에 의한 영향을 받는 사용자 식별
Exchange Server 커넥터를 성공적으로 구성하면 Intune에 등록되지 않는 장치를 저장하기 시작하지만, Exchange Active Sync를 사용하여 조직의 Exchange 리소스에 연결되지는 않습니다.  

[조건부 액세스 정책의 영향 평가](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)의 지침에 따라 조건부 액세스 정책에 의한 영향을 받는 사용자를 식별할 수 있습니다.


### 4단계: 조건부 액세스 정책에 대한 사용자 그룹 구성
정책 유형에 따라 서로 다른 사용자 그룹을 대상으로 조건부 액세스 정책을 구성합니다. 이러한 그룹에는 정책의 대상이 되거나 정책에서 제외되는 사용자가 포함됩니다. 사용자가 정책의 대상인 경우 해당 사용자가 사용하는 각 장치가 규정을 준수해야 전자 메일에 액세스할 수 있습니다.

자세한 내용은 [조건부 액세스 정책에 대한 사용자 그룹 구성](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)을 참조하세요.

### 5단계: 조건부 액세스 정책 구성
다음과 같은 흐름을 사용하여 Exchange 온-프레미스 환경에 대한 조건부 액세스 정책에 의해 장치를 허용할지 또는 차단할지를 평가합니다.

![Exchange Server 온-프레미스에 대한 조건부 액세스 정책에서 장치를 허용할지 여부를 평가하는 방법을 보여주는 순서도입니다.](./media/ProtectEmail/conditional-access-8-2.png)

[조건부 액세스 정책 구성](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access)에서 제공하는 정보에 따라 조건부 액세스 정책을 설정합니다.

## 보고

### 준수 및 조건부 액세스 정책 모니터링
Exchange에서 차단된 장치를 보려면:

Intune 대시보드에서 **Exchange에서 차단된 장치** 타일을 클릭하여 차단된 장치 수와 자세한 정보에 대한 링크를 표시합니다.
![Intune 대시보드에서 "Exchange에서 차단된 장치" 타일을 보여 주는 스크린샷입니다.](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)

## 추가 정보
모바일 장치의 회사 메일 및 메일 데이터를 보호하기 위한 솔루션을 배포한 후에 [조건부 액세스의 최종 사용자 환경](end-user-experience-conditional-access.md)에 대해 자세히 알아볼 수 있습니다. 이렇게 하면 최종 사용자가 특정 장치를 등록할 때 발생할 수 있는 문제에 대비하는 데 도움이 됩니다.



<!--HONumber=Sep16_HO1-->


