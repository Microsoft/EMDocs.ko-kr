---
title: "조건부 액세스를 위한 최종 사용자 환경"
description: "장치를 등록하고 규정 준수 문제를 해결하는 최종 사용자 환경입니다."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 3e186dd2-e17c-40d8-b160-48038b2c6593
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7c389de59d0ca6b33fbd4d872cb77236930d55bf
ms.openlocfilehash: 2972c5cfbfcc261138716aaa212728c74672c0eb


---

# 조건부 액세스를 위한 최종 사용자 환경
사용자가 처음으로 장치에서 전자 메일에 액세스하거나 이후 전자 메일을 동기화할 때는 장치 등록과 준수 상태를 확인합니다. 등록 또는 준수 문제 해결 프로세스는 안내 방식 환경에서 진행됩니다. 즉, 장치를 등록하고 정책을 준수하는 데 필요한 단계가 최종 사용자에게 표시되므로 IT 지원 센터에 도움을 요청할 필요가 없습니다.

-   **장치가 등록되지 않은 경우** 로그인 페이지에 액세스가 거부되었으며 장치를 등록하라는 메시지가 표시됩니다. 등록한 장치는 Azure Active Directory에 자동으로 등록됩니다. Intune은 장치의 정책 준수 여부를 확인하여 미준수 문제를 해결할 수 있는 수정 단계를 제공합니다. 장치가 정책을 준수하는 것이 확인되면 Intune은 Azure Active Directory에 대해 장치 준수 상태를 설정합니다.

-   **장치가 등록은 되어 있지만 정책을 준수하지 않는 경우**문제 수정을 위한 단계를 확인할 수 있는 링크가 장치로 전송됩니다. 최종 사용자가 암호나 암호화를 설정하는 등의 방법으로 문제를 해결하면 준수 정책을 관리하는 Intune이 Azure AD에서 장치의 준수 상태를 업데이트합니다.

장치가 등록되어 있으며 정책을 준수하는 것으로 평가되면 몇 분 내에 전자 메일이 동기화됩니다.

## Android

[이 항목](end-user-experience-conditional-access-android.md)에서는 조건부 액세스를 사용하도록 설정한 후에 최종 사용자가 Android 모바일 장치를 사용해 메일에 액세스하려고 처음 시도하는 경우 등록 환경에 대해 설명합니다.

## iOS

[이 항목](end-user-experience-conditional-access-ios.md)에서는 조건부 액세스를 사용하도록 설정한 후에 최종 사용자가 최초로 iOS 모바일 장치에서 메일 액세스를 시도하는 때의 최종 사용자 환경에 대해 설명합니다.

## Windows Phone

[이 항목](end-user-experience-conditional-access-winphone.md)에서는 조건부 액세스를 사용하도록 설정한 이후에 최종 사용자가 Windows Phone을 사용해 메일에 액세스하려고 시도하는 경우 최종 사용자 환경에 대해 설명합니다.



<!--HONumber=Jul16_HO3-->


