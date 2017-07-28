---
title: "사용 제한된 공유 장치 솔루션 사용 설정 | Microsoft 문서"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d78e2b94-8ad3-4703-b7f0-db070288a20b
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 66586ce378ab3faff29286bd032ac4099647494b
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2017
---
# <a name="enable-a-limited-use-shared-device-solution-with-intune"></a>Intune으로 사용 제한된 공유 장치 솔루션 사용 설정
때로는 직원이 특정 설정 및 앱만 필요한 기본 작업을 완료하기 위해 앱 및 회사 데이터에 액세스하는 데 장치를 공유해야 합니다. 이러한 경우는 흔히 소매점, 제조 작업장 및 운송 산업에서 볼 수 있습니다. 또한 어떤 경우에는 직원이 아니라 고객이 컨퍼런스, 호텔 로비, 학교 또는 도서관과 같은 장소에서 공개적으로 액세스할 수 있는 장치를 사용하여 리소스에 대화형으로 액세스해야 하기도 합니다. 자체 실행 프레젠테이션만 표시하거나 오가는 사람에게 정적 정보만 제공해야 하는 경우도 할 수 있습니다.

또한 안전한 대화형 키오스크 사용자 환경을 제공하는 동시에 의심스러운 사용자 활동으로부터 회사 자산을 보호하기 위해 앱을 다른 옵션 없이 전체 화면으로 실행할 수도 있습니다. IT에서는 이 기능을 통해 직원이 생산성을 유지하며 고객의 요구를 충족하도록 지원하는 사용자 지정 가능한 환경과 함께 추가 보안을 제공할 수 있습니다.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Enterprise Mobility + Security는 어떤 이점이 있나요?
EMS를 통해 어디서든 생산적인 작업 공간을 조성하며 고객의 요구 사항을 충족하는 기능 및 환경을 제공할 수 있습니다. iOS, Mac OS, Android 또는 Windows Mobile 회사 소유 장치 중 무엇을 사용하든, Microsoft Intune을 통해 회사 데이터를 안전하게 보호하는 동시에 직원에게는 생산성을 제공하고 고객에게는 정보를 제공할 수 있습니다.

### <a name="recommended-solution"></a>권장 솔루션
Intune을 통해 iOS 또는 Android 모바일 장치에 키오스크 모드 구성 정책 설정을 활용하고 Windows Mobile 휴대폰에 할당된 액세스 권한을 활용하여 특정 앱 또는 기능만 작동하도록 장치를 잠글 수 있습니다. Intune 구성 정책은 모바일 장치 및 컴퓨터에서 기능을 제어하는 설정 그룹입니다. 권장 설정 또는 사용자 지정 설정이 포함된 템플릿을 사용하여 정책을 만든 후 장치 또는 사용자 그룹에 해당 정책을 배포할 수 있습니다. 예를 들어 지정한 하나의 관리되는 앱만 실행되도록 허용하는 장치에 키오스크 모드 구성 정책을 배포하거나 장치에서 볼륨 단추가 사용되지 않도록 설정할 수 있습니다. 이러한 설정은 POS 장치와 같이 한 가지 기능만 수행하도록 지정된 장치 또는 장치의 데모 모델에 사용할 수 있습니다.

### <a name="how-to-implement-this-solution"></a>이 솔루션을 구현하는 방법
이 솔루션의 나머지 부분은 구성 방법을 설명하는 다음과 같은 섹션으로 구분됩니다.
- **iOS에 대한 키오스크 모드**. 이 섹션에서는 키오스크 모드 Intune 구성 정책 설정을 사용하여 iOS 장치를 잠그는 방법을 보여 줍니다.
- **Android에 대한 키오스크 모드**. 이 섹션에서는 Samsung KNOX 장치에 키오스크 모드 Intune 구성 정책 설정을 사용하여 Android 장치를 잠그는 방법을 보여 줍니다.
- **Windows에 대한 할당된 액세스 정책**. 이 섹션에서는 할당된 액세스 환경을 제공하기 위해 EnterpriseAssignedAccess CSP(구성 서비스 공급자)를 사용하여 Windows 10 Mobile 장치를 잠그는 방법을 설명합니다.

## <a name="kiosk-mode-for-ios"></a>iOS에 대한 키오스크 모드
Intune에서는 관리되는 iOS 장치를 잠글 수 있도록 하는 키오스크 모드 구성 설정을 비롯하여 iOS 장치에서 구성할 수 있는 광범위한 기본 제공 일반 설정을 제공합니다.  

키오스크 모드로 iOS(8.0 이상) 장치를 구성하려면 먼저, Mac 장치에서 [Apple Configurator 도구](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)를 사용하거나 등록 프로필을 배포하여 [Apple DEP(장치 등록 프로그램)를 통해 구매한 iOS 장치를 등록](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)해 장치를 감독 모드로 설정해야 합니다. 이 작업을 완료했으면 키오스크 모드 구성 설정을 배포하여 Intune 구성 정책으로 앱 및 장치 설정을 제어할 수 있습니다.

Intune 관리자 콘솔에서 Intune 관리 콘솔의 정책 노드와 iOS로 차례로 이동한 후 새 **iOS 일반 구성(iOS 8.0 이상)** 정책을 만들고 키오스크 모드 설정을 정의합니다. 이러한 설정에서 가장 중요한 작업은 장치가 키오스크 모드에 있을 때 실행되도록 허용할 관리되는 앱을 정의하는 것입니다.

![iOS 키오스크 모드 정책 설정](..\Solutions\media\limited-use-devices\kiosk-mode-policy.png)

Apple 앱 스토어에서 앱 또는 관리되는 앱을 지정할 수 있지만, 키오스크 모드 정책을 적용한 후에는 다른 앱을 장치에서 실행할 수 없게 됩니다. 또한 정책을 배포할 때 정책은 감독 모드의 iOS 장치에만 적용됩니다.

> [!NOTE]
> 구성 정책을 배포한 후 지정한 앱을 설치하면 장치를 다시 시작할 때까지 키오스크 모드가 시작되지 않습니다.

## <a name="kiosk-mode-for-android"></a>Android에 대한 키오스크 모드
Android KNOX 표준(4.0 이상) 장치를 잠그는 작업은 iOS 장치를 키오스크 모드로 설정하는 것과 비슷한 방식으로 수행합니다. Intune 관리자 콘솔에서 Intune 관리 콘솔의 정책 노드와 Android로 차례로 이동한 후 새 **일반 구성(Android 4 이상, Samsung KNOX Standard 4.0 이상)** 정책을 만들고 키오스크 모드 설정을 정의합니다.

Android KNOX 장치 구성에 사용할 수 있는 설정이 많지 않지만, 여전히 가장 중요한 것은 키오스크 모드에 있을 때 실행되도록 허용할 관리되는 앱입니다. 스토어 앱은 이러한 장치에서 사용할 수 없으며, 주의하지 않으면 배포한 정책이 BYOD 개인 장치를 비롯하여 정책을 수신하는 모든 Samsung KNOX 장치에서 실행됩니다. 이런 이유로 키오스크 장치로 관리해야 하는 회사 소유 장치에 대해 대량 등록을 관리하는 직원에게만 Android 장치에 대한 키오스크 모드 설정을 배포해야 합니다.

> [!NOTE]
> 구성 정책을 배포한 후 지정한 앱을 설치하면 장치를 다시 시작할 때까지 키오스크 모드가 시작되지 않습니다.

## <a name="assigned-access-policies-for-windows"></a>Windows에 대한 할당된 액세스 정책
또한 Windows 10 Mobile(버전 1511 이상) 장치를 키오스크 장치로 구성할 수 있지만, 일반 구성 정책 대신 사용자 지정 Windows 구성 정책을 사용합니다. 이러한 종류의 정책을 통해 [Windows 10 OMA-URI 설정](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings)을 활용하여 Intune으로 장치 구성 설정을 관리할 수 있습니다.

> [!TIP]
> [CSP(구성 서비스 공급자)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers)는 Windows 10에서 OMR-URI 장치 구성 설정을 공개합니다.

할당된 액세스 환경을 제공하기 위해 [EnterpriseAssignedAccess CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp)를 사용하여 Windows 10 장치를 잠급니다. 또한 해당 CSP를 사용하여 장치에서 언어 또는 테마와 같은 기타 설정을 구성하거나 사용자 지정 레이아웃을 구성할 수도 있습니다.

Windows 장치에 대한 정책을 만들려면 Intune 관리 콘솔의 정책 노드와 Windows로 차례로 이동한 후 새 **사용자 지정 구성(Windows 10 Desktop 및 Mobile 이상)** 정책을 만들어야 합니다. 여기에서 CSP 정보를 제공하고 이 정책의 배포 대상으로 지정된 Windows 장치에 적용할 설정을 정의하는 유효한 XML 파일을 가져와야 합니다.  

![OMA URI 설정](..\Solutions\media\limited-use-devices\settings.png)

단순 할당된 액세스 정책을 만들려면 이름의 기본 메타데이터와 설명을 지정하고, 데이터 형식을 **문자열(XML)**로 설정하고, *대/소문자 구분* OMA-URI 값에 **./Vendor/MSFT/EnterpriseAssignedAccess/AssignedAccess/AssignedAccessXml**을 입력합니다. 다음 예제 .XML에서는 허용 목록에 지정된 응용 프로그램(이 경우 Microsoft Edge)만 장치에서 사용할 수 있도록 장치를 잠급니다. 허용 목록의 해당 [Windows 10 Mobile 앱 제품 ID](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp#productid)로 식별되지 않는 앱은 장치에 설치된 상태 그대로 유지되지만, 뷰에 표시되지 않으며 시작이 차단됩니다. 필수 .XML 데이터를 입력하려면 다음 샘플 정보가 포함된 새 .XML 파일을 가져오거나 해당 데이터를 복사하여 한 줄 형식의 XML로 **값** 텍스트 영역에 붙여넣기만 하면 됩니다.


> [!IMPORTANT]
> 제공된 형식이 지정된 XML 샘플을 값 상자에 붙여넣을 때 전체 XML이 한 줄로 형식이 지정되어 있는지 확인해야 합니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<HandheldLockdown version="1.0">
   <Default>
      <ActionCenter enabled="false" />
      <Apps>
         <!-- Microsoft Edge -->
         <Application productId="{395589FB-5884-4709-B9DF-F7D558663FFD}" autoRun="true">
            <PinToStart>
               <Size>Medium</Size>
               <Location>
                  <LocationX>0</LocationX>
                  <LocationY>0</LocationY>
               </Location>
            </PinToStart>
         </Application>
      </Apps>
      <Buttons>
         <ButtonLockdownList>
            <!-- Lockdown all buttons -->
            <Button name="Search">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
            <Button name="Camera">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
         </ButtonLockdownList>
         <ButtonRemapList />
      </Buttons>
      <MenuItems>
         <DisableMenuItems />
      </MenuItems>
      <Settings>
         <System name="Microsoft.WiFi" />
         <System name="Microsoft.About" />
         <System name="Microsoft.Feedback" />
         <System name="Microsoft.CompanyAccount" />
         <System name="Microsoft.VPN" />
      </Settings>
      <StartScreenSize>Small</StartScreenSize>
   </Default>
</HandheldLockdown>

```
정책이 생성되면 키오스크 장치로 구성하려는 Windows 장치 그룹에 해당 정책을 배포합니다.

> [!IMPORTANT]
> 할당된 액세스 정책이 올바른 그룹에 배포되었는지 확인합니다. 장치를 초기화하는 방법 외에는 할당된 액세스 정책을 되돌릴 방법은 없습니다.

### <a name="learn-more"></a>자세한 정보
[EMS(Enterprise Mobility + Security) 사용 시작](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
