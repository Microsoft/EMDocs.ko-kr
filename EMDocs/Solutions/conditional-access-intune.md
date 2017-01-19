---
title: "Microsoft Intune으로 조건부 액세스 사용"
description: "Intune에서 메일 및 기타 서비스 보안을 위해 조건부 액세스를 사용합니다."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28662db2-faea-425f-ada9-04cf1d976fc2
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 033720647c8c284a415bd79cbc58b65e41d3e177


---

# <a name="use-conditional-access-with-microsoft-intune"></a>Microsoft Intune으로 조건부 액세스 사용
이 솔루션을 통해 Intune에서 조건부 액세스를 사용하여 지정한 조건에 따라 메일과 기타 서비스를 보호합니다.

Intune으로 조건부 액세스 기능을 사용할 수는 방법에 대한 자세한 내용은 [Microsoft Intune으로 메일 및 O365 서비스에 대한 액세스 제한](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)을 참조하세요.

> [!TIP]
> [TechNet 갤러리](https://gallery.technet.microsoft.com/protect-company-data-and-8c5e08b4)에서 이 전체 항목의 다운로드 가능한 복사본을 가져오세요.

## <a name="before-you-begin"></a>시작하기 전에
다음과 같은 메일 입에서 Exchange Online 및 Exchange 온-프레미스에 대한 액세스를 제정할 수 있습니다.

-   Android 4.0 이상/Samsung Knox 4.0 Standard 이상용 기본 제공 앱

-   iOS 7.1 이상용 기본 제공 앱

-   Windows Phone 8.1 이상용 기본 제공 앱

-   Windows 8.1 이상에 설치된 메일 응용 프로그램

-   Android 및 iOS(Exchange Online만 해당)용 Microsoft Outlook 앱

조건부 액세스를 사용하기 전에 요구 사항을 올바로 갖추었는지 확인합니다.

## <a name="for-exchange-online"></a>Exchange Online:
Exchange Online에 대한 조건부 액세스에서는 다음을 실행하는 장치를 지원합니다.

-   Windows 8.1 이상(Intune에 등록된 경우)

-   Windows 7.0 이상(도메인에 가입된 경우)

-   Windows Phone 8.1 이상

-   iOS 7.1 이상

-   Android 4.0 이상, Samsung Knox Standard 4.0 이상

또한 AAD DRS(Azure Active Directory 장치 등록 서비스)로 장치를 등록해야 합니다.

Intune 및 Office 365 고객의 경우에는 AAD DRS가 자동으로 활성화됩니다. ADFS 장치 등록 서비스를 이미 배포한 고객의 온-프레미스 Active Directory에는 등록된 장치가 표시되지 않습니다.

-   Exchange Online(예: E3)을 포함하는 Office 365 구독을 사용해야 하고 사용자는 Exchange Online의 라이선스를 취득해야 합니다.

-   **Microsoft Intune 서비스 간 커넥터**(선택 사항)는 Intune을 Microsoft Exchange Online에 연결하며 Intune 콘솔을 통해 장치 정보를 관리할 수 있도록 합니다([Exchange ActiveSync와 Microsoft Intune을 사용한 모바일 장치 관리](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) 참조). 커넥터는 준수 정책 또는 조건부 액세스 정책을 사용하려는 경우 필요가 없지만 조건부 액세스의 영향을 평가하는 보고서를 실행하려는 경우에는 필요합니다.

    커넥터를 구성하는 경우 Intune의 일부 Exchange ActiveSync 정책은 Office 콘솔에 표시될 수 있지만 기본 정책으로 설정되지는 않으며 장치에 영향을 주지도 않습니다.

    > [!IMPORTANT]
    > Exchange Online과 Exchange 온-프레미스에 대해 모두 조건부 액세스를 사용하려는 경우에는 서비스 간 커넥터를 구성하지 마세요.

    이제 [Intune으로 Exchange Online을 배포](conditional-access-intune-exchange-online.md)하는 방법을 알아볼 준비가 되었습니다.

## <a name="for-exchange-server-on-premises"></a>Exchange Server 온-프레미스의 경우
Exchange 온-프레미스에 대한 조건부 액세스는 다음을 지원합니다.

-   Windows 8 이상(Intune에 등록된 경우)

-   Windows Phone 8 이상

-   EAS(Exchange ActiveSync) 전자 메일 클라이언트를 사용하는 모든 iOS 장치

-   Android 4 이상

추가 필수 구성 요소:

-   Exchange 버전은 Exchange 2010 이상이어야 합니다. Exchange Server CAS(클라이언트 액세스 서버) 구성이 지원됩니다.

    > [!TIP]
    > Exchange 환경이 CAS 서버 구성에 있다면 온-프레미스 Exchange 커넥터가 CAS 서버 중 하나를 가리키도록 구성해야 합니다.

-   Exchange ActiveSync는 인증서 기반 인증 또는 사용자 자격 증명 항목으로 구성할 수 있습니다.

-   Intune을 Microsoft Exchange Server 온-프레미스에 연결하는 **온-프레미스 Exchange 커넥터**를 사용해야 합니다. 이렇게 하면 Intune 콘솔을 통해 장치를 관리할 수 있습니다([Exchange ActiveSync와 Microsoft Intune을 사용한 모바일 장치 관리](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) 참조).

  > [!IMPORTANT]
> 최신 버전의 온-프레미스 Exchange 커넥터를 사용하고 있는지 확인합니다. Intune 콘솔에서 사용할 수 있는 온-프레미스 Exchange 커넥터는 Intune 테넌트에 고유하며 다른 테넌트에 사용할 수 없습니다. 또한 테넌트를 위한 Exchange Connector가 여러 컴퓨터 아닌 정확히 하나의 컴퓨터에 설치되어 있는지 확인해야 합니다.

  이제 [Intune으로 Exchange Server 온-프레미스를 배포](conditional-access-intune-exchange.md)하는 방법을 알아볼 준비가 되었습니다.



<!--HONumber=Jan17_HO2-->


