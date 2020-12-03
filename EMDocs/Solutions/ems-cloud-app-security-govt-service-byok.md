---
title: 사용자 고유의 키를 사용 하 여 미사용 데이터 Cloud App Security 암호화
description: 이 문서에서는 사용자 고유의 키를 사용 하 여 Cloud App Security에 저장 된 미사용 데이터를 암호화 하는 지침을 제공 합니다.
author: shsagir
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: conceptual
ms.date: 09/24/2020
ms.collection: M365-security-compliance
ms.openlocfilehash: f4e502abc8a1e814aede03c040f0cd351d86d139
ms.sourcegitcommit: 22a30b29ee806845df9fe1786551657d9963b89a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96536235"
---
# <a name="encrypt-cloud-app-security-data-at-rest-with-your-own-key-byok"></a>사용자 고유의 키를 사용 하 여 미사용 데이터 Cloud App Security 암호화 (BYOK)

*적용 대상: Microsoft Cloud App Security*

이 문서에서는 사용자 고유의 키를 사용 하 여 수집 되는 데이터를 암호화 하는 데 사용 되는 Cloud App Security를 구성 하는 방법을 설명 합니다. 클라우드 앱에 저장 된 데이터에 암호화를 적용 하는 방법에 대 한 설명서를 찾고 있는 경우 [Azure Information Protection 통합](/cloud-app-security/azip-integration)을 참조 하세요.

Cloud App Security는 보안과 개인 정보를 심각 하 게 보호 합니다. 따라서 Cloud App Security에서 데이터 수집을 시작 하면 데이터 [보안 및 개인 정보](/cloud-app-security/cas-compliance-trust) 보호 정책에 따라 자체 관리 되는 키를 사용 하 여 데이터를 보호 합니다. 또한 Cloud App Security를 사용 하면 사용자 고유의 Azure Key Vault 키로 암호화 하 여 미사용 데이터를 더욱 안전 하 게 보호할 수 있습니다.

> [!IMPORTANT]
> Azure Key Vault 키에 액세스 하는 데 문제가 있는 경우 Cloud App Security는 데이터를 암호화 하는 데 실패 하 고 테 넌 트는 한 시간 이내에 잠깁니다. 테 넌 트가 잠겨 있으면이에 대 한 모든 액세스는 원인이 해결 될 때까지 차단 됩니다. 키에 다시 액세스할 수 있게 되 면 테 넌 트에 대 한 모든 액세스가 복원 됩니다.

## <a name="prerequisites"></a>필수 구성 요소

Cloud App Security 테 넌 트와 연결 된 테 넌 트의 Azure Active Directory (Azure AD)에서 **Microsoft Cloud App Security BYOK** 앱을 등록 해야 합니다.

### <a name="to-register-the-app"></a>앱을 등록 하려면

1. [Graph 용 PowerShell Azure Active Directory를](/powershell/azure/active-directory/install-adv2)설치 합니다.

1. PowerShell 터미널을 열고 다음 명령을 실행 합니다.

    ``` Powershell
    Connect-AzureAD
    New-AzureADServicePrincipal -AppId 6a12de16-95c8-4e42-a451-7dbbc34634cd
    Set-AzureADServicePrincipal -ObjectId <object_id> -AccountEnabled true
    ```

    여기서 *<object_id>* 는 이전 명령 ()에서 반환 된 개체 id입니다 `New-AzureADServicePrincipal` .

> [!NOTE]
>
> - Cloud App Security는 모든 새 테 넌 트에 대해 미사용 데이터를 암호화 합니다.
> - 48 시간 이상 Cloud App Security에 있는 모든 데이터는 암호화 됩니다.

## <a name="deploy-your-azure-key-vault-key"></a>Azure Key Vault 키 배포

1. **일시 삭제** 및 **보호** 해제 옵션을 사용 하 여 [새 Key Vault](/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key-vault) 을 만듭니다.

1. 액세스 정책을 만들고 다음 정보를 입력 한 다음 **추가** 를 클릭 합니다.
    1. **키 사용 권한** 을 클릭 하 고 드롭다운 메뉴에서 다음 사용 권한을 선택 합니다.

        | 섹션 | 필요한 사용 권한 |
        | --- | --- |
        | 키 관리 작업 | -목록 |
        | 암호화 작업 | -키 래핑<br />-래핑 해제 키 |

        ![키 사용 권한 선택을 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-access-policy-key-perms.PNG)

    2. **보안 주체 선택** 에서 **Microsoft Cloud App Security-byok** 를 선택 합니다.

        ![액세스 정책 추가 페이지를 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-add-access-policy.PNG)

    3. **저장** 을 클릭합니다.

1. [새 RSA 키](/azure-stack/user/azure-stack-key-vault-manage-portal#create-a-key)를 만들고 다음을 수행한 후 **추가** 를 클릭 합니다.

    > [!NOTE]
    > RSA 키만 지원 됩니다.

    1. **허용 된 작업** 에서 다음 옵션을 선택 합니다.

        - 키 래핑
        - 키 래핑 취소

    2. **키 식별자** URI를 복사 합니다. 나중에 필요 합니다.

    ![키 설정 페이지를 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-key-perms.PNG)

1. 선택한 네트워크에 대해 방화벽을 사용 하는 경우 필요에 따라 지정 된 키에 대 한 Cloud App Security 액세스를 제공 하도록 다음 방화벽 설정을 구성 하 고 **저장** 을 클릭 합니다.
    1. 가상 네트워크가 선택 되어 있지 않은지 확인 합니다.
    1. 다음 IP 주소를 추가 합니다.
        - 13.66.200.132
        - 23.100.71.251
        - 40.78.82.214
        - 51.105.4.145
        - 52.166.166.111
    1. **신뢰할 수 있는 Microsoft 서비스에서이 방화벽을 무시 하도록 허용을** 선택 합니다.

    ![방화벽 구성을 보여 주는 스크린샷](media/cloud-app-security-byok/byok-kv-firewall.PNG)

## <a name="enable-data-encryption-in-cloud-app-security"></a>Cloud App Security에서 데이터 암호화 사용

데이터 암호화를 사용 하도록 설정 하면 즉시 Azure Key Vault 키를 사용 하 여 미사용 데이터를 암호화 Cloud App Security. 키가 암호화 프로세스에 필수적 이므로 지정 된 Key Vault 및 키를 항상 액세스할 수 있는지 확인 하는 것이 중요 합니다.

### <a name="to-enable-data-encryption"></a>데이터 암호화를 사용 하도록 설정 하려면

1. Cloud App Security의 메뉴 모음에서 설정 코그 ![ 설정 아이콘을 클릭 ](media/cloud-app-security-byok/byok-kv-settings-icon.png) 하 고 **설정** 을 선택 합니다.

1. **데이터 암호화** 탭을 선택 합니다.

1. **데이터 암호화 사용** 을 클릭 합니다.

1. **Azure Key Vault 키 uri** 상자에 앞에서 복사한 키 식별자 uri 값을 붙여넣습니다.

    > [!NOTE]
    > Cloud App Security는 URI로 지정 된 키 버전과 관계 없이 항상 최신 키 버전을 사용 합니다.

1. URI 유효성 검사가 완료 되 면 **사용** 을 클릭 합니다.

> [!NOTE]
> 데이터 암호화를 사용 하지 않도록 설정 하면 Cloud App Security는 미사용 데이터에서 고유한 키를 사용 하 여 암호화를 제거 합니다. 그러나 데이터는 Cloud App Security의 관리 키로 암호화 된 상태로 유지 됩니다.
>
> **데이터 암호화를 사용 하지 않도록 설정 하려면:** **데이터 암호화** 탭으로 이동 하 여 **데이터 암호화 사용 안 함** 을 클릭 합니다.

## <a name="key-roll-handling"></a>키 롤링 처리

데이터 암호화를 위해 구성 된 키의 새 버전을 만들 때마다 Cloud App Security가 자동으로 최신 버전의 키를 롤백합니다.

## <a name="how-to-handle-data-encryption-failures"></a>데이터 암호화 실패를 처리 하는 방법

Azure Key Vault 키에 액세스 하는 데 문제가 있는 경우 Cloud App Security는 데이터를 암호화 하는 데 실패 하 고 테 넌 트는 한 시간 이내에 잠깁니다. 테 넌 트가 잠겨 있으면이에 대 한 모든 액세스는 원인이 해결 될 때까지 차단 됩니다. 키에 다시 액세스할 수 있게 되 면 테 넌 트에 대 한 모든 액세스가 복원 됩니다. 데이터 암호화 실패를 처리 하는 방법에 대 한 자세한 내용은 [고유한 키를 사용 하 여 데이터 암호화 문제 해결](ems-cloud-app-security-govt-service-byok-troubleshoot.md)을 참조 하세요.
