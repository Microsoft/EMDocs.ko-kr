---
title: "Windows Phone에서의 조건부 액세스를 위한 최종 사용자 환경"
description: "Windows Phone을 등록하는 최종 사용자 환경입니다."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 906566e0-f05e-4af5-b4d5-0efb083dca76
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 46c8690074703d4e7de667cea115ca6db7818984
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="windows-phone"></a>Windows Phone

등록 프로세스 및 사용자에게 표시되는 화면은 최종 사용자 장치에서 실행 중인 OS 버전에 따라 약간 달라집니다.  이 항목에서는 Windows Phone을 등록하는 최종 사용자 환경을 설명합니다.

## <a name="enrolling"></a>등록

1.  사용자가 이미 Intune에 등록했으며 규정을 준수하는 경우에는 Windows 장치에서 차이가 없으며 계속해서 메일에 액세스할 수 있습니다. 아직 Intune에 등록하지 않은 사용자는 다음 샘플과 비슷한 격리 메일을 수신합니다.

    ![Windows Phone에서 사용자가 받는 격리 메일을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows-quarantineEmail.png)

    사용자가 **지금 시작** 을 클릭하면 장치 등록이 시작됩니다.

2.  회사 액세스 설정 화면에서 사용자가 **시작** 을 클릭하여 장치를 설정하고 장치가 규격 장치인지 여부를 확인하여 시작합니다.

    ![Windows Phone의 회사 액세스 설정 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows1-company-Access-Setup.png)

3.  사용자가 장치 등록 화면에서 **Confirm Enrollment** (등록 확인)를 클릭하여 장치 등록을 시작합니다.

    ![Windows Phone의 장치 등록 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows3-enroll-Device.png)

    등록 도중 모바일 장치 관리 프로필이 설치되어 IT 관리자가 장치를 원격으로 관리할 수 있게 됩니다. 사용자에게 작업 공간 연결 권한을 부여하는 인증서를 수락하라는 메시지가 표시될 수 있습니다.

    ![Windows Phone의 Workplace Join을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows4-workplaceJoin1.png)

4.  사용자가 Office에서 사용하는 메일 주소를 사용해서 로그인합니다. 로그인하고 나면 장치 등록을 계속하기 위해 **Confirm Enrollment** (등록 확인)를 한 번 더 클릭해야 할 수 있습니다.

    ![Windows Phone에서 Workplace Join이 진행 중임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows5-workplaceJoin2.png)

    장치가 등록되었는지 확인됩니다.

    ![Windows Phone에서 장치 등록이 시작되는 것을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows6-checking-Enrollment.png)

5.  그런 다음 사용자는 장치를 선택하고 **선택**를 선택하여 등록 프로세스를 완료합니다. 사용자 장치가 표시되지 않는 경우 **내 장치가 목록에 보이지 않습니다.** 를 선택하여 다시 시도할 수 있습니다.

    ![사용자가 장치가 Windows Phone용인지 확인해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows7-confirm-Device.png)

    장치가 회사 정책을 준수하는지 확인됩니다.

    ![Windows Phone이 규정을 준수하는지 확인 중임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows9-checking-Compliance.png)

6.  준수 문제가 있는 경우 사용자에게 문제를 해결(예: 유효한 암호 만들기)하라는 메시지가 표시되고 그런 다음 **준수 확인** 을 클릭하여 계속하도록 안내됩니다.

    ![Windows Phone에서 사용자가 규정 준수 문제를 해결해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows13-resolve-Compliance.png)

    규정 준수가 확인되면 사용자에게 등록 활성화 중이라는 메시지가 표시됩니다.

    ![Windows Phone에서 등록 활성화가 시작되는 것을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows10-activating-Enrollment.png)

7.  등록이 활성화되면 사용자가 **계속** 을 클릭하여 프로세스를 완료합니다. 그런 다음 사용자는 **완료** 를 클릭하여 설정을 종료합니다.

    ![Windows Phone에서 회사 액세스 설정이 완료되었음을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows11-COMPLETE.png)

    사용자 등록 및 준수 확인이 완료되면 몇 분 이내에 메일 액세스를 사용할 수 있게 됩니다.

사용자가 위 단계를 따라 등록하고 준수 상태가 되었는데도 여전히 모바일 장치에서 메일에 액세스할 수 없다면 다음과 같은 추가 단계에 따라 문제를 해결할 수 있습니다.

-   첫째, 장치가 등록되었는지 확인합니다. 등록되지 않았다면 사용자는 위의 단계를 따릅니다.

-   **준수 확인**을 클릭하여 장치의 준수 상태를 확인합니다. 규정 준수 오류가 식별되면 사용자는 이를 해결하는 방법과 관련한 모바일 장치별 지침에 따릅니다(예: 암호 재설정).

-   지원 센터에 전화합니다.

## <a name="issues-and-solutions"></a>문제 및 해결 방법
기본적으로 8시간마다 장치를 검사하여 여전히 규격 장치인지 확인됩니다. 이전에 규격이던 장치가 나중에 비규격 장치로 판단되는 경우(예: 준수 정책 추가 또는 변경 시) 사용자는 다음 단계를 따라 장치를 준수 상태로 되돌릴 수 있습니다.

1.  장치가 비규격 상태임을 알리는 메일 알림이나 장치 메시지가 사용자에게 수신됩니다. 이때 장치는 Exchange에서 격리됩니다.

2.  사용자가 메일에 액세스하려고 시도하면 Intune 회사 포털에서 회사 액세스 설정 화면으로 리디렉션되어 미준수 상태임을 알리는 메시지를 보게 됩니다.

    ![Windows Phone이 비준수 상태임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Windows14-OutOfCompliance.png)

3.  사용자가 **계속** 을 클릭하면 메일 액세스를 차단하는 준수 문제가 표시됩니다.

4.  문제를 해결한 후 사용자는 **준수 확인** 을 클릭하여 문제가 해결되었는지 확인합니다.

5.  문제가 해결되었다면 사용자는 **계속** 을 클릭하여 프로세스를 마칩니다. 몇 분 내에 메일에 다시 액세스할 수 있습니다.

### <a name="where-to-go-from-here"></a>추가 정보
최종 사용자 환경은 다른 모바일 장치와 약간 다릅니다. [Android](end-user-experience-conditional-access-android.md) 및 [iOS](end-user-experience-conditional-access-ios.md)의 최종 사용자 환경에 대한 자세한 정보를 확인할 수 있습니다.
