---
title: 사용자 고유의 키로 데이터 암호화 문제 해결
description: 이 문서에서는 Cloud App Security 미사용 데이터를 암호화 하는 데 사용 되는 Azure Key Vault 키에 액세스 하지 못하게 하는 문제 목록을 제공 합니다.
keywords: ''
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 09/24/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.openlocfilehash: ef46f49db6ef22c35326c5fda1a8349c934408d2
ms.sourcegitcommit: c4d433c095ec8bc733daa06f5544d4b04e0323d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91214912"
---
# <a name="troubleshooting-data-encryption-with-your-own-key"></a>사용자 고유의 키로 데이터 암호화 문제 해결

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 Cloud App Security 미사용 데이터를 암호화 하는 데 사용 되는 Azure Key Vault 키에 액세스 하지 못하게 하는 문제 목록을 제공 합니다.

> [!IMPORTANT]
> Azure Key Vault 키에 액세스 하는 데 문제가 있는 경우 Cloud App Security는 데이터를 암호화 하는 데 실패 하 고 테 넌 트는 한 시간 이내에 잠깁니다. 테 넌 트가 잠겨 있으면이에 대 한 모든 액세스는 원인이 해결 될 때까지 차단 됩니다. 키에 다시 액세스할 수 있게 되 면 테 넌 트에 대 한 모든 액세스가 복원 됩니다.

## <a name="troubleshooting"></a>문제 해결

다음 표에서는 데이터 암호화가 실패할 수 있는 가능한 시나리오와이를 해결 하기 위해 수행할 수 있는 작업을 보여 줍니다.

| 시나리오 | 동작 |
| --- | --- |
| <a name="missing-kv-key-permissions"></a>**Key Vault 또는 키 권한이 없습니다.** | 선택한 Key Vault의 액세스 정책에서 다음 키 권한이 선택 되어 있는지 확인 합니다.<br />**키 관리 작업** 아래<br />-목록<br />**암호화 작업** 에서<br />-키 래핑<br />-래핑 해제 키<br /><br />선택한 키에 대해 RSA 암호화를 사용 하 고 있으며 다음 작업이 허용 되는지 확인 합니다.<br />-키 래핑<br />-래핑 해제 키<br /> |
| <a name="firewall-block"></a>**키에 대 한 액세스를 차단 하 Azure Key Vault 방화벽** | 선택한 Key Vault에서 방화벽이 다음 IP 주소를 사용 하 여 구성 되었는지 확인 합니다.<br />- 13.66.200.132<br />- 23.100.71.251<br />- 40.78.82.214<br />- 51.105.4.145<br />- 52.166.166.111 |
| <a name="key-not-enabled"></a>**암호화 키를 사용할 수 없습니다.** | 선택한 키의 설정에서 키를 사용할 수 있는지 확인 합니다.<br />![키 사용 옵션을 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-key-enabled.PNG) |
| <a name="key-not-active"></a>**암호화 키가 활성화 되어 있지 않습니다.** | 선택한 키의 설정에서 활성화 날짜 및 시간이 현재 날짜 및 시간 보다 이전 인지 확인 합니다.<br />![키 활성화 날짜를 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-key-activation-date.PNG) |
| <a name="key-expired"></a>**암호화 키가 만료 되었습니다.** | 선택한 키의 설정에서 만료 날짜 및 시간이 전달 되지 않았는지 확인 합니다.<br />![키 만료 날짜를 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-key-expiration-date.PNG) |
| <a name="key-not-found"></a>**암호화 키를 찾을 수 없거나 삭제 되었습니다.** | 선택한 키가 Key Vault에 있는지 확인 합니다. 키가 삭제 된 경우 복구 하 고 다시 사용 하도록 설정 합니다. 키를 다른 Key Vault 이동 했으면 선택한 Key Vault 다시 이동 합니다. |

문제가 발생하는 경우 지원받을 수 있습니다. 제품 문제에 대해 도움이나 지원을 받으려면 [지원 티켓을 여세요](/cloud-app-security/support-and-ts.md).
