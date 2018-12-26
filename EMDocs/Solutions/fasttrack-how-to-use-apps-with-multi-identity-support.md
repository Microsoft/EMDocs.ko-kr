---
title: 다중 ID를 지원하는 애플리케이션을 사용하는 방법
description: 다중 ID를 지원하는 앱을 사용하는 방법
keywords: ''
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.assetid: 586ecd93-b097-42a0-9229-bcf3b781021c
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 93c2572546cab512623cb96412ee064da8a3c233
ms.sourcegitcommit: 75ba5494047b2405c0fb6bfcf20b962c45ec658b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51196443"
---
# <a name="how-to-use-apps-with-multi-identity-support"></a>다중 ID를 지원하는 앱을 사용하는 방법

이 시나리오에서는 Microsoft Word를 예제로 사용합니다. Office 365에 포함된 다른 앱에도 이와 동일한 단계를 적용할 수 있습니다.

1. 디바이스에서 **Word** 앱을 엽니다. 이 예제에서는 iOS 디바이스를 사용합니다.
2. **새로 만들기**를 탭하여 새 Word 문서를 만듭니다.

   ![사용자가 “새로 만들기"를 선택하여 Word 문서 만들기를 시작하는 것을 보여 주는 스크린샷](./media/ft-multiID-1-createDoc.png)

3. 원하는 문장을 입력하고 **저장**을 탭합니다. 문서를 저장하는 위치에 대한 두 가지 옵션 즉, 개인 위치와 회사 위치가 제공됩니다. 문서가 회사용인지 또는 개인용인지 아직 설정하지 않았으므로 이 단계에서는 앱 정책이 활성화되지 않았습니다.

   ![사용자가 새 Word 문서에서 새 문장을 입력한 것을 보여 주는 스크린샷](./media/ft-multiID-2-saveDoc.png)

4. **회사 위치**(예: 비즈니스용 OneDrive)에 문서를 저장합니다. 비즈니스용 OneDrive는 회사 위치로 인식되므로 이제 문서에는 회사 데이터로 태그가 지정되고 정책 제한이 적용됩니다.
5. 이제 방금 회사 위치에 저장한 문서를 열고 텍스트를 복사합니다. 개인 **Facebook** 계정을 열고 복사한 텍스트를 붙여넣으려고 합니다. 새 Facebook 게시물에 콘텐츠를 붙여넣을 수 없습니다. 붙여넣기 옵션이 회색으로 표시되지는 않지만 **붙여넣기**를 누를 때 아무 작업도 수행되지 않습니다. 이는 정책 제한에서 회사 데이터가 개인 앱에서 공유되지 않도록 하기 때문입니다.

   ![사용자가 새 Word 문서에서 텍스트를 복사하고 있는 것을 보여 주는 스크린샷 ](./media/ft-multiID-3-copyText.png)

   ![사용자가 Facebook에 텍스트를 붙여 넣지 못하고 있는 것을 보여 주는 스크린샷](./media/ft-multiID-4-pasteInFB.png)
6. 다음으로 2단계와 3 단계를 반복하여 다른 새 Word 문서를 만듭니다. 원하는 문장을 입력하고 이번에는 개인 위치(예: **OneDrive - 개인**)에 저장합니다. 문서는 개인으로 태그가 지정되고 회사 정책 제한이 적용되지 않습니다.

   ![사용자가 새 Word 문서에 문장을 입력한 것을 보여 주는 스크린샷](./media/ft-multiID-5-createDoc.png)

7. 방금 개인 위치에 저장한 문서를 열고 텍스트를 복사합니다. 다시 한 번 **Facebook**을 열고 복사한 텍스트를 붙여넣습니다. 이 문서는 개인으로 태그가 지정되었으므로 콘텐츠를 Facebook 게시물에 붙여넣을 수 있어야 합니다.

   ![사용자가 Facebook에 텍스트를 붙여 넣을 수 있는 것을 보여 주는 스크린샷](./media/ft-multiID-6-copyText.png)

## <a name="want-to-learn-more"></a>더 자세한 내용을 원하세요?

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx)를 참조하세요.
