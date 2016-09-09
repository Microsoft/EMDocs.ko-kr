---
title: "Android 장치에서의 조건부 액세스를 위한 최종 사용자 환경"
description: "Android 장치를 등록하는 최종 사용자 환경입니다."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b5e4330-6fa5-445c-b73e-86ce5b9c7964
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 8cf46358bb945c711b62dc7b05fcb8267c911782


---

# Android

등록 프로세스 및 사용자에게 표시되는 화면은 최종 사용자 장치에서 실행 중인 OS 버전에 따라 약간 달라집니다. 이 항목에서는 Android 장치를 등록하는 최종 사용자 환경을 설명합니다.

## 등록

1.  메일에 액세스하려고 하면 먼저 다음 샘플과 유사한 격리 메일을 수신합니다.

    ![Android 장치에서 사용자가 받는 격리 메일을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-quarantine-Email.png)

    사용자가 **지금 시작** 을 클릭하면 장치 등록이 시작됩니다.

    > [!NOTE]
    > 사용자가 장치의 기본 브라우저를 설정하지 않은 경우에는 장치 등록 도중 및 등록 활성화 도중에 브라우저 창을 여는 링크를 허용하라는 메시지가 나타납니다. 메시지가 나타나면 매번 동일한 브라우저를 선택해야 하며 그러지 않으면 등록 프로세스가 실패합니다.

2.  사용자에게 각 앱 스토어에서 Intune 회사 포털 앱을 설치하라는 메시지가 표시됩니다.

    ![Android 장치의 Intune 회사 포털을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-Portal.png)

    앱이 설치된 후 사용자가 앱을 열고 회사 자격 증명을 사용하여 로그인합니다.

3.  회사 액세스 설정 화면에서 사용자가 **시작** 을 클릭하여 장치를 설정하고 장치가 규격 장치인지 여부를 확인하여 시작합니다.

    ![Android 장치의 회사 액세스 설정 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-company-Access-Setup.PNG)

4.  사용자가 장치 등록 화면에서 **등록** 을 클릭하여 장치 등록을 시작합니다.

    ![Android 장치의 장치 등록 화면을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-device-Enroll.png)

5.  메시지가 나타나면 사용자는 **활성화** 를 클릭하여 장치 관리자를 활성화해야 하며 그러지 않으면 장치 등록 절차가 취소됩니다.

    ![Android 장치에서 사용자가 장치 관리자를 활성화해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-activate-DeviceAdmin.PNG)

    장치 등록이 시작됩니다. 장치에 따라 등록 도중에 인증서 설치 프롬프트 또는 삼성 KNOX 개인정보취급(처리)방침 프롬프트가 나타날 수 있습니다. 이는 IT 관리자가 원격으로 장치를 관리하는 데 필요합니다. 장치가 Intune에 등록되고 Azure Active Directory를 사용하여 장치 ID를 설정합니다.

    ![Android 장치에서 장치 등록이 시작되는 것을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-enrolling-Device.png)

6.  등록이 성공적으로 완료되면 사용자가 **계속** 을 클릭하여 장치에서 준수 검사를 시작합니다.

    ![Android 장치에서 장치 등록에 성공했음을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-enroll-Success.png)

    준수 문제가 있는 경우 사용자에게 문제를 해결(예: 유효한 암호 만들기)하라는 메시지가 표시되고 그런 다음 **준수 확인** 을 클릭하여 계속하도록 안내됩니다.

    ![Android 장치에서 사용자가 규정 준수 문제를 해결해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

7.  장치가 완전한 준수 상태가 되면 사용자가 **계속** 을 클릭하여 등록 활성화를 시작합니다. 그러면 AAD 장치 ID가 Exchange에서 제공된 EAS ID와 연결됩니다.

    > [!NOTE]
    > Android에서는 등록 활성화 도중에 기본 브라우저가 몇 초 정도 나타납니다. 사용자가 아직 기본 브라우저를 선택하지 않은 경우에는 브라우저를 선택하라는 메시지가 표시됩니다. 회사 액세스 설정을 완료하는 동안 메시지가 표시될 때마다 사용자가 동일한 브라우저를 선택해야 합니다.

    ![Android 장치가 준수 상태임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-compliance-Successful.PNG)

8.  등록 활성화가 완료되고 사용자가 **완료** 를 클릭하여 등록 및 준수 증명 프로세스를 종료합니다.

    ![Android 장치에서 회사 액세스 설정이 완료되었음을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-all-Successful2.PNG)

    사용자 등록 및 준수 확인이 완료되면 몇 분 이내에 메일 액세스를 사용할 수 있게 됩니다.

사용자가 위 단계를 따라 등록하고 준수 상태가 되었는데도 여전히 모바일 장치에서 메일에 액세스할 수 없다면 다음과 같은 추가 단계에 따라 문제를 해결할 수 있습니다.

1.  첫째, 장치가 등록되었는지 확인합니다. 등록되지 않았다면 사용자는 위의 단계를 따릅니다.

2.   **준수 확인**을 클릭하여 장치의 준수 상태를 확인합니다. 규정 준수 오류가 식별되면 사용자는 이를 해결하는 방법과 관련한 모바일 장치별 지침에 따릅니다(예: 암호 재설정).

3.  지원 센터에 전화합니다.

## 문제 및 해결 방법
기본적으로 8시간마다 장치를 검사하여 여전히 규격 장치인지 확인됩니다. 이전에 규격이던 장치가 나중에 비규격 장치로 판단되는 경우(예: 준수 정책 추가 또는 변경 시) 사용자는 다음 단계를 따라 장치를 준수 상태로 되돌릴 수 있습니다.

1.  장치가 비규격 상태임을 알리는 메일 알림이나 장치 메시지가 사용자에게 수신됩니다. 이때 장치는 Exchange에서 격리됩니다.

2.  사용자가 메일에 액세스하려고 하면 준수 문제를 해결해야 액세스할 수 있음을 알리는 격리 메일을 받게 됩니다. 사용자가 이 격리 메일의 하이퍼링크를 클릭하면 (기본 브라우저 및 Google Play를 통해) Intune 회사 포털의 회사 액세스 설정 화면으로 리디렉션되어 여기서 장치가 비규격 상태임을 확인하게 됩니다.

    ![Android 장치가 비준수 상태임을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-outOfCompliance.png)

3.  사용자가 **계속** 을 클릭하면 메일 액세스를 차단하는 준수 문제가 표시됩니다.

    ![Android 장치에서 사용자가 규정 준수 문제를 해결해야 함을 보여 주는 스크린샷](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

4.  문제를 해결한 후 사용자는 **준수 확인** 을 클릭하여 문제가 해결되었는지 확인합니다.

5.  문제가 해결되었다면 사용자는 **계속** 을 클릭하여 프로세스를 마칩니다. 몇 분 내에 메일에 다시 액세스할 수 있습니다.

### 추가 정보
최종 사용자 환경은 다른 모바일 장치와 약간 다릅니다. [iOS](end-user-experience-conditional-access-ios.md) 및 [Windows Phone](end-user-experience-conditional-access-winphone.md)의 최종 사용자 환경에 대한 자세한 정보를 확인할 수 있습니다.



<!--HONumber=Sep16_HO1-->


