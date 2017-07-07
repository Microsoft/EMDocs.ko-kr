---
title: "회사 전자 메일 첨부 파일 보호"
description: "MAM(모바일 응용 프로그램 관리) 정책을 사용하여 메일 및 메일 첨부 파일의 콘텐츠를 보호합니다."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1e630c1-7190-4ba9-b71d-ed9c2e93a6cc
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: a124d56eaa6cbca44551a7c3ea42166479523f9f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/07/2017


---

# <a name="protect-email-and-attachments-from-data-leakage"></a>전자 메일 및 첨부 파일의 데이터 유출 방지
[회사 메일 및 문서 보호](protect-corporate-email-documents.md)에서는 규격 장치만 회사 메일에 액세스하도록 하는 방법을 설명했습니다. 그러나 액세스를 보호하는 것만으로는 전자 메일 및 전자 메일 첨부 파일의 내용을 보호할 수 없습니다. 해당 내용을 복사/이동하거나 다른 위치에 저장하거나 다른 사용자와 공유할 수 있기 때문입니다. EMS는 MAM(모바일 응용 프로그램 관리) 정책을 사용하여 이 문제를 해결합니다.

관리되는 앱은 IT 관리자가 배포했으며 회사 보안 요구 사항을 따르는 앱입니다. IT 부서는 이러한 앱을 통해 배포, 인벤토리 또는 업데이트 등의 지속적 관리, 그리고 앱 및 앱과 연결된 데이터의 선택적 지우기를 직접 제어합니다. 또한 Intune에서는 MAM(모바일 응용 프로그램 관리) 정책 집합을 통해 다음과 같이 앱 기능을 수정하고 데이터 공유를 제한할 수 있습니다.

-   복사/붙여넣기를 차단하거나 관리되는 앱에서 MAM 정책이 없는 앱으로의 데이터 전송을 방지합니다.

-   개인 클라우드 저장소로의 백업과 다른 이름으로 저장 등을 방지합니다.

-   MAM으로 보호되는 앱에서 PIN/암호 또는 회사 자격 증명을 요구하여 앱 액세스를 보호합니다.

-   Intune Managed Browser 내에서 모든 웹 링크를 열도록 응용 프로그램을 구성합니다.

-   관리되는 앱과 연결된 데이터만 선택적으로 지웁니다. 장치를 분실 또는 도난당하거나 더 이상 IT 부서에서 관리하지 않는 경우에는 선택적 지우기를 통해 앱에서 회사 데이터를 모두 제거하여 개인 앱 데이터만 남겨 둘 수 있습니다. 이러한 방식을 다중 ID라고 합니다.

[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)을 사용하면 다음과 같은 방식으로 메일 보호를 확장할 수 있습니다.

-   적절한 사용자만 회사 내부나 외부에서 내용을 읽거나 볼 수 있도록 전자 메일 메시지를 암호화할 수 있습니다.

-   사용자는 전자 메일을 보호할 수 있으며, 받는 사람은 자신에게 전송된 보호된 전자 메일 메시지를 읽고 사용할 수 있습니다.

-   관리자는 다음을 수행하는 규칙을 설정할 수 있습니다.

    -   지정된 받는 사람 그룹에 대해 규칙을 자동으로 적용하거나 특정 부서용 템플릿을 만듭니다.

    -   규칙을 자동으로 검색해 중요한 내용이 포함된 전자 메일 메시지에 적용합니다. 규칙은 보낸 사람, 받는 사람, 메시지 제목 또는 내용을 기준으로 할 수 있습니다.

    -   중요한 내용을 검색한 다음 전자 메일을 보내기 전에 보호 규칙을 적용하라는 경고를 보낸 사람에게 표시합니다.

## <a name="managed-app-components"></a>관리되는 앱 구성 요소

-   **Microsoft Intune**에서는 정책을 구성하거나, 앱과 정책을 연결하거나, 앱 래핑 도구를 사용해 내부 앱이 모바일 응용 프로그램 관리 정책을 사용하도록 설정할 수 있습니다.

-   **회사 포털** 은 각 장치에서 기본적으로 실행되거나 브라우저를 기반으로 실행되는 앱입니다. IT 부서에서 사용자나 장치에 관리되는 앱을 배포하면 최종 사용자가 포털에서 해당 앱을 설치할 수 있습니다. 앱과 연결된 정책은 앱을 통해 장치에 적용됩니다.

![회사 포털 및 Microsoft Intune을 통해 관리되는 앱에 대한 정책을 처리하는 방법을 보여주는 그래픽](./media/ProtectEmail/CADataSheet-Diagram-Apps.png)

## <a name="the-it-admin-experience"></a>IT 관리자 환경
IT 관리자는 모바일 응용 프로그램 관리 정책을 만들고 앱에 정책을 연결한 다음 사용자나 장치에 앱을 배포합니다. 관리되는 앱을 장치에 설치하면 앱 제한이 적용됩니다. 관리되는 앱을 만들고 배포할 때는 추가적인 작업이 거의 또는 전혀 필요하지 않습니다.

-   앱 SDK가 이미 포함된 기존 앱이 있으면 앱에 대해 제한을 적용할 수 있습니다. 따라서 다른 처리는 수행하지 않아도 되며 iTunes 또는 Google Play와 같은 앱 스토어로 이동되는 링크만 추가하면 됩니다. 관리되는 앱 목록을 확인하려면 [이 문서](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners)를 참조하세요.

-   내부에서 만든 앱을 관리하려는 경우 Microsoft Intune 앱 래핑 도구를 사용해 앱을 다시 패키지하면 됩니다. 이 도구를 통해 앱을 다시 패키지하면 앱에 제한을 적용할 수 있습니다.

## <a name="the-end-user-experience"></a>최종 사용자 환경
최종 사용자는 관리되는 앱을 설치한 다음 업무용으로 사용할 수 있습니다. 이 경우 관리되는 앱 간에만 데이터를 이동하거나 공유할 수 있습니다. 관리되는 앱 에코시스템 외부로의 데이터 이동은 차단됩니다.

## <a name="where-to-go-from-here"></a>추가 정보
[회사 메일 및 문서](protect-corporate-email-documents.md) 및 메일 첨부 파일을 보호하는 방법에 대해 이해했으므로 [회사 메일을 보호하는 솔루션을 구현](implement-solution.md)하는 방법에 대해 알아볼 수 있습니다.

