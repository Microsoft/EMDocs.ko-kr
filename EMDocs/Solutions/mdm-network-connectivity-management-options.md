---
# required metadata

title: 네트워크 연결 관리 옵션
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bc7cdb8f-3485-45ae-9493-f840ad9ed3ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 네트워크 연결 관리 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

인프라에 따라 모바일 장치는 종종 VPN으로 보호된 끝점으로 보호되는 다양한 인터넷 연결 서비스의 회사 리소스에 연결할 수 있습니다.

[Intune](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) 또는 ConfigMgr와의 [하이브리드 배포](https://technet.microsoft.com/library/dn261221.aspx)를 통해 Wi-Fi 프로필을 배포하여 Wi-Fi 네트워크를 프로비전할 수 있으므로 장치가 해당 범위 내에 있을 때 네트워크에 자동으로 연결될 수 있습니다. 예를 들어 회의실로 분할되는 Wi-Fi 네트워크에 연결되었다가 다른 위치로 로밍 시 Wi-Fi 네트워크 세그먼트에 연결되도록 모바일 장치를 구성할 수 있습니다. 사용자는 암호를 입력하거나 네트워크를 선택할 필요가 없으며 연결이 자동으로 작동합니다.

[Intune](/Intune/deployuse/vpn-connections-in-microsoft-intune) 및 [ConfigMgr](https://technet.microsoft.com/library/dn261217.aspx)는 모바일 장치로 직접 VPN 프로필을 배포하여 추가적인 구성 또는 수동 작업 없이 내부 회사 리소스에 액세스할 수 있도록 합니다. 또한 Intune은 형식 리소스 또는 액세스 방법을 기반으로 VPN 연결을 자동으로 시작하도록 모바일 장치를 구성할 수 있습니다. 그러나 다양한 유형의 모바일 장치 운영 체제에 대해 이 작업을 수행하기 위한 구성 요구 사항이 각기 다릅니다.

작업 3의 질문에 대한 답변은 회사 리소스에 장치를 연결하는 방법을 결정하는 데 도움이 됩니다. 현재 <token>Office 365용 MDM</token> 에서는 모바일 장치에 대한 무선 및 VPN 네트워크 리소스 관리를 지원하지 않습니다.

아래 목록에서는 Intune 독립 실행형 및 하이브리드 Intune 및 ConfigMgr를 사용하여 무선 및 VPN 네트워크를 관리할 때의 장단점을 보여 줍니다.

## Intune(독립 실행형)

**장점**

- 모든 주요 모바일 장치 운영 체제(Android, iOS, Windows 10, Windows 8.x, 및 Windows Phone)에서 무선 및 VPN 프로필 지원 
- Cisco, Juniper, Dell SonicWall, Checkpoint 등을 비롯하여 업계의 선두적인 VPN 연결 유형 지원
- 무선 및 VPN 프로필은 보안 향상을 위해 SCEP 인증서 프로필에 통합될 수 있음
- 다양한 유형의 사용자, 장치, 장치 운영 체제 또는 사용자 그룹 및 역할에 대한 사용자 지정된 무선 및 VPN 프로필 구성 지원
- Windows 10, Windows 8.1, Windows Phone 8.1 및 iOS에 대한 DNS 이름 기반 시작 지원
- Windows 10 및 Windows 8.1에 대한 응용 프로그램 ID 기반 시작 지원
- VPN 프로필에서 VPN을 통해 자동으로 회사 네트워크에 연결하는 앱 선택

**단점**

- VPN 프로필을 지원하려면 온-프레미스 VPN 인프라를 배포 및 유지해야 함

## Office 365용 MDM

MDM for Office 365에서는 Wi-Fi 및 VPN 정책이 지원되지 않음

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점 및 다음 장점
    - 기존 온-프레미스 엔터프라이즈 VPN 인프라에서 VPN 프로필 지원

**단점**

- VPN 프로필을 지원하려면 온-프레미스 VPN 인프라를 배포 및 유지해야 함 
- ConfigMgr에서 [Wi-Fi 프로필](https://technet.microsoft.com/library/dn408646.aspx) 및 [VPN 프로필](https://technet.microsoft.com/library/dn408643.aspx)을 관리하려면 특정 보안 권한이 부여되어야 함

다음을 검토하여 모바일 장치 메일 구성 관리 옵션에 대한 세부 정보를 살펴봅니다.

- Intune: [무선](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) 및 [VPN](/Intune/deployuse/vpn-connections-in-microsoft-intune) 프로필을 사용하도록 설정
- ConfigMgr: [무선](https://technet.microsoft.com/library/dn261221.aspx) 및 [VPN](https://technet.microsoft.com/library/dn261217.aspx) 프로필을 사용하도록 설정

<!--HONumber=Apr16_HO2-->


