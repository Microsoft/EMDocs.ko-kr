---
title: "조직에서 관리하는 모바일 응용 프로그램을 사용하는 방법"
description: "조직에서 관리하는 모바일 앱을 사용하는 방법"
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: jeffgilb
ms.date: 09/28/2016
ms.topic: article
ms.prod: 
ms.service: ems
ms.technology: 
ms.assetid: 174348f0-dbc6-4204-8626-3c6f38b7bbde
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dab9c133dd5a79afef07291405c2ac25218ca715
ms.openlocfilehash: f9464790624d94d89c43aae3db35f58ffae6da01


---

# 조직에서 관리하는 모바일 앱을 사용하는 방법

## iOS 장치에서 OneDrive 액세스

이 섹션에서는 비즈니스용 OneDrive를 예제로 사용하여 사용자 환경이 Intune에서 관리하는 응용 프로그램에서 어떻게 약간 변경될 수 있는지를 보여 줍니다.

1.  **비즈니스용 OneDrive** 앱을 시작하여 로그인 페이지를 엽니다.

  ![iOS에 대한 비즈니스용 OneDrive 로그인 페이지를 보여 주는 스크린샷](./media/ft-useMngdApps-1-launchOnedrive.png)
> [!NOTE]
> 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다. 장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2.  회사 계정 사용자 이름을 입력합니다. 회사 자격 증명을 입력할 수 있도록 **O365 인증** 페이지로 리디렉션됩니다.

  ![Office 365 로그인 페이지에서 자격 증명을 입력하는 iOS 사용자를 보여 주는 스크린샷](./media/ft-useMngdApps-2-enterName.png)
3.  Azure AD에서 자격 증명이 인증되면 MAM 정책이 적용되며, **비즈니스용 OneDrive** 앱을 다시 시작하라는 메시지가 표시됩니다.

  ![OneDrive를 다시 시작해야 함을 보여 주는 스크린샷](./media/ft-useMngdApps-3-restart.png)
> [!NOTE]
> Intune에서 등록되지 않은 장치에서만 다시 시작 필요 대화 상자가 표시됩니다.

4.  **비즈니스용 OneDrive** 앱을 다시 시작합니다. 그러면 MAM 정책이 켜진 상태로 앱이 시작됩니다. 이제 앱에 대한 **PIN** 을 설정하라는 메시지가 표시됩니다. (해당 정책을 구성한 경우).

  ![iOS 사용자에게 앱의 PIN을 설정할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-useMngdApps-4-enterPIN.png)
5.  PIN을 설정하고 확인하면 **비즈니스용 OneDrive**의 파일에 액세스할 수 있습니다.

  ![iOS의 비즈니스용 OneDrive에서 액세스할 수 있는 다양한 파일을 보여 주는 스크린샷](./media/ft-useMngdApps-5-accessFiles.png)
> [!NOTE]
> 배포된 정책을 변경하는 경우 다음에 앱을 열 때 변경 내용이 적용됩니다.

## Android 장치의 OneDrive 액세스
이 섹션에서는 비즈니스용 OneDrive를 예제로 사용하여 사용자 환경이 Intune에서 관리하는 응용 프로그램에서 어떻게 약간 변경될 수 있는지를 보여 줍니다.
1.  **비즈니스용 OneDrive** 앱을 시작하여 로그인 페이지를 엽니다.
> [!NOTE]
> 개인 장치에서는 일반적으로 최종 사용자가 앱을 다운로드합니다. 장치가 MDM 솔루션에서 관리되는 경우 장치에 앱을 배포할 수 있습니다.

2.  회사 계정 사용자 이름을 입력합니다. 회사 자격 증명을 입력하도록 O365 인증 페이지로 리디렉션됩니다.

  ![Office 365 로그인 페이지에서 자격 증명을 입력하는 Android 사용자를 보여 주는 스크린샷](./media/ft-useMngdApps-6-enterCreds.png)
3.  Azure AD에서 자격 증명이 인증되면 회사 포털 앱을 설치하는 지침이 포함된 메시지가 표시됩니다(아직 장치에 설치되지 않은 경우). **앱 다운로드**를 탭하여 계속 진행합니다.
> [!NOTE]
> 회사 포털 앱에는 Android 장치에서 MAM 정책과 관련된 모든 앱이 필요합니다. Intune에 등록되지 않은 장치의 경우 앱을 장치에 설치해야 하지만 시작 또는 앱에 로그인이 필요하지 않습니다.

4.  이제 **Google Play** 스토어에 있으며, **회사 포털** 앱을 다운로드하고 설치할 수 있습니다.

  ![Android 사용자에게 Intune 회사 포털을 다운로드하기 위해 Google Play 스토어로 이동할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-useMngdApps-7-installPortal.png)

 회사 포털 앱은 데이터를 안전하게 보호하는 데 도움이 됩니다.
![Android 사용자에게 Intune 회사 포털을 설치할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-useMngdApps-8-intunePortal.png)
5.  설치를 완료한 후 **동의함**을 선택하여 약관에 동의합니다.
6.  **비즈니스용 OneDrive** 앱이 자동으로 시작됩니다.
7.  다음에 비즈니스용 OneDrive를 열면 정책 설정이 **비즈니스용 OneDrive** 앱 액세스 시 PIN을 요구하도록 설정된 경우 **PIN**을 설정하라는 메시지가 표시됩니다.

  ![Android 사용자에게 앱의 PIN을 설정할 것인지 묻는 메시지를 보여 주는 스크린샷](./media/ft-useMngdApps-9-setNewPIN.png)
8.  PIN이 설정 및 확인되고 나면 이제 앱 정책에 의해 관리되는 **비즈니스용 OneDrive**를 계속 사용할 수 있습니다.

### 더 자세한 내용을 원하세요?
[Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 참조하세요.



<!--HONumber=Nov16_HO3-->


