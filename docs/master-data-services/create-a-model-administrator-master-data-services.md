---
description: 모델 관리자 만들기(Master Data Services)
title: 모델 관리자 만들기
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], creating
ms.assetid: dae17afc-3b39-490e-b51f-2d8da26d429e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9049dc6e40cb7bba60b68e8185e887fe27f4a5ec
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88390089"
---
# <a name="create-a-model-administrator-master-data-services"></a>모델 관리자 만들기(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 하나 이상의 모델에 있는 모든 개체에 대한 모든 권한을 사용자나 그룹에 부여하려면 모델 관리자를 만들면 됩니다.  
  
> [!TIP]  
>  관리를 간소화 하려면 Windows 또는 로컬 그룹을 만들고이를 모델 관리자로 구성 합니다. 그러면 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에 액세스하지 않고 그룹에서 사용자를 추가하고 제거할 수 있습니다.  
  
## <a name="prerequisites"></a>사전 요구 사항  
 이 절차를 수행하려면  
  
-   **사용자 및 그룹 권한** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다.  
  
-   모델 관리자여야 합니다. 자세한 내용은 [관리자 &#40;MDS(Master Data Services)&#41;](../master-data-services/administrators-master-data-services.md)를 참조 하세요.  
  
### <a name="to-create-a-model-administrator"></a>모델 관리자를 만들려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 **사용자 및 그룹 권한**을 클릭합니다.  
  
2.  **사용자** 또는 **그룹** 페이지에서 편집하려는 사용자나 그룹의 행을 선택합니다.  
  
3.  **선택한 사용자 편집**을 클릭합니다.  
  
4.  **모델** 탭을 클릭합니다.  
  
5.  또는 **모델** 목록에서 모델을 선택합니다.  
  
6.  **편집**을 클릭합니다.  
  
7.  사용 권한을 부여할 모델을 클릭합니다.  
  
8.  메뉴에서 **관리**를 선택합니다.  
  
9. 그룹 또는 사용자를 관리자로 만들 각 모델에 대해 7단계와 8단계를 수행합니다.  
  
10. **저장**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리자는 MDS(Master Data Services) &#40;&#41;](../master-data-services/administrators-master-data-services.md)   
 [모델 개체 사용 권한 할당 &#40;MDS(Master Data Services)&#41;](../master-data-services/assign-model-object-permissions-master-data-services.md)   
 [계층 멤버 권한 할당 &#40;MDS(Master Data Services)&#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [모델 개체 사용 권한 &#40;MDS(Master Data Services)&#41;](../master-data-services/model-object-permissions-master-data-services.md)   
 [계층 멤버 권한&#40;Master Data Services&#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
