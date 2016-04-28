---
# required metadata

title: 인증서 관리 옵션
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: c3d350b5-4437-4f3d-907f-57ce6a819a74

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 인증서 관리 옵션

>[!NOTE]
>이 항목은 좀 더 큰 디자인 고려 사항 가이드의 일부입니다. 이 가이드의 맨 처음부터 시작하려면 [기본 항목](mdm-design-considerations-guide.md)을 확인하세요. 이 전체 가이드의 다운로드 가능 복사본을 가져오려면 [TechNet 갤러리](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)를 방문하세요.

디지털 인증서 관리 및 인증서 프로필 사용은 [Intune](/Intune/deployuse/secure-resource-access-with-certificate-profiles) 독립 실행형과 [하이브리드 Intune 및 ConfigMgr](https://technet.microsoft.com/library/dn261202.aspx) 배포 시나리오에서 모두 지원됩니다. 이러한 기능을 사용하면 모바일 장치가 조직의 NDES 서버에서 추가 인증서를 가져오도록 하는 SCEP(단순 인증서 등록 프로토콜) 기반 프로필뿐만 아니라 신뢰할 수 있는 루트 인증서를 모바일 장치에 배포할 수 있습니다.

SCEP는 기본적으로 iOS, Windows 10 및 8.1, Windows Phone 10 및 8.1에서 지원되며, Android용 Microsoft Intune 회사 포털 앱을 통해서도 지원되므로 이 등록 프로토콜을 사용하면 모바일 장치에서 개인 키를 직접 생성하게 되는 이점이 있습니다. ConfigMgr 또는 Intune에서는 개인 키가 절대 생성, 캐시 또는 저장되지 않으므로 모바일 장치 보안을 유지하는 데 도움이 됩니다.

아래 그림에서는 Intune 및 ConfigMgr에서 NDES를 통해 SCEP를 사용하여 모바일 장치에 대해 보안 인증서 프로비저닝을 제공하는 방법을 보여 줍니다.

![보안 인증서 프로비저닝](./media/MDM_Figure_07.png)

**보안 인증서 프로비저닝**

1. SCEP 등록을 위한 인증서의 속성을 포함하는 정책이 Intune 서비스에서 만들어집니다.
2. Intune에서 이 정책을 플랫폼 모바일 장치 관리 프로토콜(예: Windows 10 및 Windows 8.1용 OMA DM)로 변환하고 장치로 전송
3. 모바일 장치가 정책을 받고 NDES에서 등록 요청 시작
4. NDES가 ConfigMgr로 요청 전달
5. ConfigMgr에서는 SCEP 요청의 요청 특성이 인증과 일치하는지 비교하고 NDES로 다시 확인을 보냅니다.
6. NDES는 CA에 인증서 발급 요청을 보내고 NDES 역할로 인증서를 보냅니다.
7. NDES 역할은 장치에 인증서를 보냅니다.

작업 3의 질문에 대한 답변에 따라, 모바일 장치 관리 솔루션에서 인증서를 관리하는 방식을 결정할 수 있습니다. 현재 MDM for Office 365에서는 모바일 장치에 대한 인증서 프로필 관리를 지원하지 않습니다. 

아래 목록은 Intune과 하이브리드 Intune 및 ConfigMgr 배포 시나리오에 대한 인증서 프로필 관리 장단점을 이해하는 데 도움이 됩니다.

## Intune(독립 실행형)

**장점**

- 모든 주요 모바일 장치 운영 체제(Android, iOS, Windows 10, Windows 8.x, 및 Windows Phone)에서 인증서 프로필 지원
- 플랫폼이 SCEP(단순 인증서 등록 프로토콜) 지원
- 인증서 프로필은 수동으로 인증서를 설치하거나 승인되지 않은 보안 프로세스를 사용하지 않고도 회사 리소스에 액세스할 수 있도록 자동으로 모바일 장치를 구성할 수 있습니다.
- 장치가 관리에서 사용 중지되거나, 선택적으로 초기화되거나, 관리 계층서 차단될 때 인증서가 자동으로 취소될 수 있음

**단점**

- 인증서 프로필을 사용하려면 일부 기존 온-프레미스 인프라가 있어야 합니다. 다음 온-프레미스 인프라를 Intune에 통합해야 합니다.
 - 네트워크 장치 등록 서비스를 실행하는 서버
 - 엔터프라이즈 인증 기관
 - NDES를 실행하는 서버에 설치된 Intune NDES 커넥터

## Office 365용 MDM

- MDM for Office 365에서는 인증서 프로필을 지원하지 않습니다.

## 하이브리드(ConfigMgr와 Intune)

**장점**

- Intune 독립 실행형의 모든 장점 및 다음 장점
 - 비모바일 장치에 대한 인증서도 지원

**단점**

- 인증서 프로필을 사용하려면 일부 기존 온-프레미스 인프라가 있어야 합니다. 
- 다음 온-프레미스 인프라를 Intune에 통합해야 합니다.
 - 네트워크 장치 등록 서비스를 실행하는 서버
 - 엔터프라이즈 인증 기관
 - NDES를 실행하는 서버에 설치된 Intune NDES 커넥터

모바일 장치 인증서 관리 옵션에 대한 자세한 내용을 보려면 [인증서 프로필을 사용하도록 설정](/Intune/deployuse/secure-resource-access-with-certificate-profiles)하는 방법을 읽고 이러한 요구 사항 및 절차를 System Center 2012 R2 Configuration Manager의 [인증서 프로필을 사용하도록 설정](https://technet.microsoft.com/library/dn261202.aspx)과 비교합니다.

<!--HONumber=Apr16_HO2-->


