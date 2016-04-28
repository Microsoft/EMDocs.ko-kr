---
# required metadata

title: 사고 대응 요구 사항 파악
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 1072858e-dc0a-44ad-a512-d938f20310b6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 데이터 암호화

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

저장된 데이터 및 전송 중인 데이터 암호화를 위한 요구 사항과 관련된 작업 1의 질문에 답변했으므로 이제 각 요구 사항을 해결하는 데 사용할 수 있는 옵션을 평가해 보겠습니다. 데이터가 저장된 상태에서도 아래 그림과 같이 여러 다른 방법으로 암호화할 수 있습니다.

![모바일 장치 디스크](./media/MDM_Figure_09.png)

## 다양한 암호화 수준

전체 디스크 암호화나, 앱에서 처리되는 데이터에 따른 암호화를 사용할 수 있습니다. [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx)에서는 모바일 장치에서 파일 암호화를 수행하는 정책을 적용할 수 있습니다. 자동으로 암호화되는 모바일 장치(예: Windows Phone 8 장치)도 있고, 다른 옵션이 사용되도록 설정된 경우에만 데이터를 암호화하는 모바일 장치도 있습니다. 예를 들어 iOS 장치의 경우 장치에서 암호를 요구하도록 설정을 구성한 후에만 암호화가 자동으로 수행됩니다. 

Windows 10 Mobile에서는 BitLocker 기술 기반의 장치 암호화를 통해 운영 체제와 데이터 저장소 파티션을 포함한 모든 내부 저장소를 암호화합니다. 사용자가 장치 암호화를 활성화하거나, IT 부서에서 MDM 도구를 통해 회사 관리 장치에 대한 암호화를 활성화하여 적용할 수 있습니다. 장치 암호화가 실행되면 휴대전화에 저장된 모든 데이터가 자동으로 암호화됩니다. Windows 10 Mobile 장치에서 암호화를 실행하면 장치 분실 또는 도난 시 저장된 데이터의 기밀 유지에 도움이 됩니다. 자세한 내용은 Windows 10 Mobile 보안 가이드를 읽어보세요.

>[!TIP]ConfigMgr를 사용하여 암호화가 설정될 수 있는 모바일 장치에 대한 자세한 내용을 보려면 [Configuration Manager의 모바일 장치에 대한 호환성 설정](https://technet.microsoft.com/library/dn376523.aspx)을 읽어보세요.

Intune 모바일 응용 프로그램 관리 정책과 연결된 앱의 경우에는 Microsoft에서 암호화 기능을 제공합니다. 데이터는 모바일 응용 프로그램 관리 정책의 설정에 따라 파일 I/O 작업 중에 동기식으로 암호화됩니다. Android 장치에서 관리되는 앱은 플랫폼 암호화 라이브러리를 활용하는 CBC(암호화 블록 체인) 모드에서 FIPS 140-2가 인증되지 않은 AES-128 암호화를 사용합니다. 

이 옵션을 사용하면 SD 카드와 같은 외부 미디어에 저장된 데이터를 포함하여 특정 앱에 연결된 모든 데이터가 암호화되도록 지정할 수 있습니다. 동일한 기능을 [MDM for Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)에서도 사용할 수 있습니다. 

비즈니스용 OneDrive와 같은 공용 클라우드 저장소 서비스를 Intune 독립 실행형 및 [System Center 2012 R2 Configuration Manager SP1](https://technet.microsoft.com/library/mt131422.aspx)과도 통합할 수 있습니다. 비즈니스용 OneDrive 앱을 사용자 장치에 배포할 수 있으며 이 경우 사용자의 비즈니스용 OneDrive 계정에 있는 모든 문서가 암호화됩니다. 

대부분의 MDM 솔루션은 SSL을 사용하여 전송 중인 데이터를 보호하므로 기존 PKI를 사용하여 인증서를 발급할지 또는 타사 공급업체 CA(인증 기관)를 사용할지를 결정해야 합니다. 타사 CA를 사용할 경우의 장점은 자신의 장치를 사용하여 회사 리소스에 액세스하는 사용자는 잘 인식된 공용 CA를 자동으로 신뢰하게 된다는 것입니다. 

## Intune(독립 실행형)

**장점** 

- Intune 관리 정책에 의해 제어되는 앱과 연결된 데이터 암호화

**단점** 

- 모바일 장치 저장소용 네이티브 암호화를 포함하지 않음
- 현재 온-프레미스 MDM 플랫폼과 제대로 통합되지 않으므로 사용할 수 있는 추가 관리 인터페이스가 제공됨

## Office 365 MDM

**장점**

- 모바일 장치 플랫폼 기능을 기반으로 데이터 암호화

**단점**

- 조직에 최신 온-프레미스 ConfigMgr 인프라가 없는 경우 통합 전에 이 플랫폼의 계획, 설치 및 구성 필요

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 관리 정책에 의해 제어되는 앱과 연결된 데이터 암호화
- 모바일 장치 저장소 암호화
- 모바일 장치에서 암호화될 수 있는 대상과 암호화 방법을 보다 구체적으로 제어(암호화 알고리즘의 선택 가능)

**단점**

- 조직에 최신 온-프레미스 ConfigMgr 인프라가 없는 경우 통합 전에 이 플랫폼의 계획, 설치 및 구성 필요

Intune 및 ConfigMgr 기능을 결합하여 데이터 보호 기능을 강화하고 암호화를 구성하는 방법을 자세히 알아보려면 [Configuration Manager 및 Intune을 사용하여 모바일 장치의 암호화 관리](http://blogs.technet.com/b/pauljones/archive/2014/08/04/managing-encryption-on-mobile-devices-with-configuration-manager-and-intune.aspx)를 읽어보세요.


<!--HONumber=Apr16_HO2-->


