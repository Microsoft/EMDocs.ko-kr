---
title: "iOS 장치에서의 조건부 액세스를 위한 최종 사용자 환경"
description: "iOS 장치를 등록하는 최종 사용자 환경입니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c641ea8-2c0e-490e-b1de-831336f46d19
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 807b5875e12b4303c8d349adaf0702d2fd75d9f1
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="ios"></a>iOS

등록 프로세스 및 사용자에게 표시되는 화면은 최종 사용자 장치에서 실행 중인 OS 버전에 따라 약간 달라집니다. 이 항목에서는 iOS 장치를 등록하는 최종 사용자 환경을 설명합니다.

## <a name="enrolling"></a>등록

1.  사용자가 이미 Intune에 등록했으며 규정을 준수하는 경우에는 iOS 장치에서 차이가 없으며 계속해서 메일에 액세스할 수 있습니다. 아직 등록하지 않은 경우에는 사용자가 메일 앱을 시작하면 다음과 비슷한 격리 메시지가 나타납니다.

    ![iOS 장치에서 사용자가 받는 격리 메일을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-Get-Started.PNG)

    사용자가 **지금 시작** 을 클릭하면 장치 등록이 시작됩니다.

2.  사용자에게 각 앱 스토어에서 Intune 회사 포털 앱을 설치하라는 메시지가 표시됩니다.

    ![iOS 장치의 Intune 회사 포털을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-intune-Company-Portal.png)

    앱이 설치된 후 사용자가 앱을 열고 회사 자격 증명을 사용하여 로그인합니다.

3.  회사 액세스 설정 화면에서 사용자가 **시작** 을 클릭하여 장치를 설정하고 장치가 규격 장치인지 여부를 확인하여 시작합니다.

    ![iOS 장치의 회사 액세스 설정 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-company-AccessSetup.png)

4.  사용자가 장치 등록 화면에서 **등록** 을 클릭하여 장치 등록을 시작합니다.

    ![iOS 장치의 장치 등록 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-device-Enrollment.png)

    등록 도중 모바일 장치 관리 프로필이 설치되어 IT 관리자가 장치를 원격으로 관리할 수 있게 됩니다. 메시지가 나타나면 사용자가 암호를 입력합니다.

5.  사용자가 회사 액세스 설정 화면에서 **계속** 을 클릭해 장치 규정 준수 검사를 시작합니다.

    ![iOS 장치에서 장치 등록에 성공했으며 사용자가 규정 준수를 확인해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-device-Compliance-Check.png)

    준수 문제가 있는 경우 예를 들어 유효한 암호를 만드는 등의 방법으로 문제를 해결하라는 메시지가 사용자에게 표시되고 **준수 확인** 을 클릭하여 계속하도록 안내됩니다.

    ![iOS 장치에서 사용자가 규정 준수 문제를 해결해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

6.  장치가 완전한 준수 상태가 되면 사용자가 **계속** 을 클릭하여 진행합니다.

    ![iOS 장치가 준수 상태이며 설치가 완료되었음을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    사용자 등록 및 준수 확인이 완료되면 몇 분 이내에 메일 액세스를 사용할 수 있게 됩니다.

사용자가 위 단계를 따라 등록하고 준수 상태가 되었는데도 여전히 모바일 장치에서 메일에 액세스할 수 없다면 다음과 같은 추가 단계에 따라 문제를 해결할 수 있습니다.

-   첫째, 장치가 등록되었는지 확인합니다. 등록되지 않았다면 사용자는 위의 단계를 따릅니다.

-   **준수 확인**을 클릭하여 장치의 준수 상태를 확인합니다. 규정 준수 오류가 식별되면 사용자는 이를 해결하는 방법과 관련한 모바일 장치별 지침에 따릅니다(예: 암호 재설정).

-   지원 센터에 전화합니다.

## <a name="issues-and-solutions"></a>문제 및 해결 방법
기본적으로 8시간마다 장치를 검사하여 여전히 규격 장치인지 확인됩니다. 이전에 규격이던 장치가 나중에 비규격 장치로 판단되는 경우(예: 준수 정책 추가 또는 변경 시) 사용자는 다음 단계를 따라 장치를 준수 상태로 되돌릴 수 있습니다.

1.  장치가 비규격 상태임을 알리는 메일 알림이나 장치 메시지가 사용자에게 수신됩니다. 이때 장치는 Exchange에서 격리됩니다.

2.  사용자가 메일에 액세스하려고 시도하면 Intune 회사 포털에서 회사 액세스 설정 화면으로 리디렉션되어 미준수 상태임을 알리는 메시지를 보게 됩니다.

    ![iOS 장치가 비준수 상태임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-fallOut-Compliance.png)

3.  사용자가 **계속** 을 클릭하면 메일 액세스를 차단하는 준수 문제가 표시됩니다.

    ![iOS 장치에서 사용자가 규정 준수 문제를 해결해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

4.  문제를 해결한 후 사용자는 **준수 확인** 을 클릭하여 문제가 해결되었는지 확인합니다.

5.  문제가 해결되었다면 사용자는 **계속** 을 클릭하여 프로세스를 마칩니다.

    ![iOS 장치가 준수 상태이며 설치가 완료되었음을 보여 주는 스크린샷](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    몇 분 내에 메일에 다시 액세스할 수 있습니다.

### <a name="where-to-go-from-here"></a>추가 정보
최종 사용자 환경은 다른 모바일 장치와 약간 다릅니다. [Android](end-user-experience-conditional-access-android.md) 및 [Windows Phone](end-user-experience-conditional-access-winphone.md)의 최종 사용자 환경에 대한 자세한 정보를 확인할 수 있습니다.
