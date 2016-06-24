---
# required metadata

title: 회사 메일 및 문서를 보호하기 위한 아키텍처 지침
description:
keywords:
author: karthikaraman
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: fc9c7d79-d2ca-4cb2-8456-c7a88cbbf6fd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# 회사 메일 및 문서를 보호하기 위한 아키텍처 지침
이 항목은 최종 사용자 환경이 단순하고 생산성에 영향을 주지 않도록 하면서 회사를 위한 데이터 보호 방법에 대해 개괄하는 것으로 시작합니다. 그런 다음 회사 메일에 안전하게 액세스하도록 돕고 Microsoft Enterprise Mobility Suite 솔루션을 사용하여 메일 및 첨부 파일에 있는 회사 데이터를 보호하는 데 도움이 될 수 있는 방법에 대해 구체적으로 살펴볼 것입니다.

이 섹션에서는 회사 메일 및 문서를 보호하기 위한 아키텍처에 대해 설명합니다. 솔루션 배포에 대한 지침은 [Learn more about how to deploy a solution for protecting company email and documents(회사 메일 및 문서를 보호하는 솔루션을 배포하는 방법에 대해 자세히 알아보기)](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md)를 참조하세요.

> [!TIP]
> [TechNet 갤러리](https://gallery.technet.microsoft.com/Managing-Access-and-Help-b7a05d0d/file/140056/1/Managing%20Access%20and%20Help%20Protect%20Corporate%20Email%20Data%20on%20Mobile%20Devices.pdf)에서 이 전체 항목의 다운로드 가능한 복사본을 가져오세요.

직원은 자신의 장치를 사용해 회사 리소스 및 생산성 도구에 액세스하고자 합니다. IT 부서는 직원들에게 이 기능을 제공함과 동시에 중요한 회사 데이터를 보호해야 합니다. BYOD([Bring Your Own Device](byod-design-considerations-guide.md))는 개인 장치에서 개인 데이터와 업무 데이터를 분리해야 하며 회사 데이터를 의도적 또는 실수로나 공유하면 안 된다는 점에서 구체적인 과제를 제시합니다.

**조사에 따르면 다음과 같습니다.**

-   전 세계 인력 중 37%는 모바일 환경을 사용함

-   2014년 3분기에 열어서 확인한 총 메일 중 53%는 휴대폰이나 태블릿에서 연 것으로 확인됨

-   작업자의 61%는 자신의 장치에서 개인 작업과 업무상의 작업을 함께 수행함

이와 관련하여 다음 사항을 고려해야 합니다.

-   모든 장치에서 가장 많이 사용되는 응용 프로그램은 전자 메일인 경우가 많습니다.

-   전자 메일과 전자 메일 첨부 파일의 내용을 IT 부서 관리 범위 외부의 다른 위치로 복사, 공유 또는 이동할 수 있으므로 회사의 보안이 위험해질 수 있습니다.

최종 사용자는 개인 장치를 사용하여 회사 업무를 수행하기를 원하며, 가장 흔히 액세스하는 응용 프로그램은 전자 메일이므로 IT에서 가장 먼저 수행해야 하는 단계는 전자 메일의 중요 데이터가 손상되지 않도록 하면서 최종 사용자가 자신의 장치에서 회사 전자 메일에 액세스할 수 있도록 하는 것입니다.

## 개요
Microsoft는 ID, 모바일 장치 관리, 앱 관리 및 데이터 보호를 위한 포괄적 솔루션인 EMS(Enterprise Mobility Suite)를 제공합니다. EMS는 IT 부서가 거의 모든 장치에서 전자 메일, 데이터 및 회사 응용 프로그램에 대한 액세스를 관리할 수 있도록 하는 계층형 보안 모델을 제공합니다.

EMS는 다음과 같은 클라우드 서비스로 구성됩니다.

![EMS의 일부인 클라우드 서비스를 보여주는 그래픽: Microsoft Azure AD Premium, Microsoft Intune 및 Microsoft Azure Rights Management](./media/ProtectEmail/Enterprise-Mobility-Suite.png)

EMS를 사용하면 회사 네트워크 내부와 외부에서 모두 데이터를 보호할 수 있습니다.

-   직원은 중요한 회사 정보 손상을 염려하지 않고도 원하는 장치에서 회사 전자 메일, 업무 관련 응용 프로그램 및 회사 데이터에 액세스할 수 있습니다.

-   회사 데이터는 모든 수준(사용자/장치/응용 프로그램 수준 및 최종적으로는 데이터 자체 수준)에서 보호됩니다.

-   IT 관리자는 신뢰할 수 있는 사용자만이 관리되는 장치와 규정 준수 장치 내의 관리되는 응용 프로그램 컨텍스트에서 회사 데이터에 액세스하도록 할 수 있습니다.

Intune에서 관리하는 앱에는 이 솔루션의 주요 요소인 Office 모바일 앱이 포함됩니다. Office 모바일 앱을 사용하면 데이터 유출을 방지하는 동시에 직원의 생산성을 높일 수 있습니다. 예를 들어 IT 관리자는 Dropbox 등의 개인 클라우드 저장소에 회사 데이터를 복사하지 못하도록 하는 정책을 설정할 수 있습니다.

직원이 다른 부서로 이동하거나 장치를 분실하는 경우 EMS는 장치에서 회사 데이터를 선택하여 원격으로 지우는 옵션을 제공합니다. 이 작업은 최종 사용자나 IT 관리자가 수행할 수 있습니다.

## EMS에서 데이터를 보호하는 방법
ID, 장치, 앱 및 데이터용 4계층 보안 모델은 필요한 사용자만 관리자가 구성한 준수 정책 집합을 충족하는 장치를 사용하여 관리되는 앱의 범위 내에서 회사 리소스에 액세스하는지를 확인합니다.

![ID, 장치, 앱 및 데이터에 대한 4개로 계층화된 보안 모델을 보여주는 그래픽](./media/ProtectEmail/Protecting_your_data.png)

데이터를 보호하려면 먼저 사용자 ID를 설정하고 유효성을 검사해야 합니다. 엔터프라이즈급 ID 및 액세스 관리 도구인 *Azure AD/*는 Single Sign-On, Multi-Factor Authentication, 셀프 서비스 암호 등의 다양한 기능을 제공합니다. 또한 보안 모델의 **ID 계층** 용 기능도 제공합니다.

이러한 기능을 통해 ID 기준을 설정한 IT 관리자는 *Microsoft Intune* 을 사용하여 모바일 장치가 등록되어 있고 관리되며 회사 정책을 준수하는지 확인할 수 있습니다. **장치 계층**에서 이러한 확인을 수행합니다.

세 번째 계층은 Intune에서 관리하는 앱 에코시스템이 포함되는 **앱 관리 계층**입니다. 이 에코시스템에서 사용자는 생산성을 높이고 Office 등 업무상 필요하며 평소 익숙하게 사용해 왔던 도구를 사용할 수 있고, IT 부서는 중요한 데이터를 관리되는 앱 에코시스템 내에 유지할 수 있습니다.

파일 수준에서 데이터를 보호하는*Azure RMS(Azure 권한 관리)* 를 통해 보안 모델이 완성됩니다. 데이터에 적용되는 보안 정책은 데이터를 이동하면 함께 이동하므로 데이터에 액세스하는 데 사용하는 장치와 관계없이 전송 중인 데이터와 보관 중인 데이터가 모두 안전하게 유지됩니다. 이러한 보호가 적용되는 계층이 보안 모델의 **데이터 계층** 입니다.

## 추가 정보
- 평가용 계정을 등록하고 시작하려면 이 비디오를[시청](https://www.youtube.com/watch?v=ltcZvm4VOFU) 하세요.

- [Mobile Device Management Design Considerations Guide(모바일 장치 관리 디자인 고려 사항 가이드)](mdm-design-considerations-guide.md)를 참고하여 모바일 장치 관리 디자인 요구 사항을 파악하세요.

- [Learn more about how to deploy a solution for protecting company email and documents(회사 메일 및 문서를 보호하는 솔루션을 배포하는 방법에 대해 알아보세요)](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md).

또한 EMS와 Azure Active Directory에 대해 자세히 알아보려면 다음 문서에서 자세한 정보를 얻을 수 있습니다.
- [EMS 아키텍처](https://azure.microsoft.com/en-us/documentation/infographics/enterprise-mobility/)

- [Azure Active Directory란?](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/)

- [Azure Active Directory가 Office 365, Microsoft Intune 및 다른 Microsoft 서비스를 지원하는 방법](https://azure.microsoft.com/en-us/documentation/articles/active-directory-administer/#what-is-an-azure-ad-tenant)

- [Azure Active Directory를 통해 ID를 관리하는 방법](https://azure.microsoft.com/en-us/documentation/articles/active-directory-administer/)

- [Azure 권한 관리란?](https://technet.microsoft.com/en-us/library/jj585026.aspx)

- [응용 프로그램에서 Azure 권한 관리를 지원하는 방법](https://technet.microsoft.com/en-us/library/jj585004.aspx)


<!--HONumber=Apr16_HO4-->


