---
description: 변경 집합 적용 및 업데이트(Master Data Services)
title: 변경 집합 적용 및 업데이트
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 3a6a3cf2-1e77-43d3-a64a-855ae51258e7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 06373651ed453c412360e2cf6201c61752e637be
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88456839"
---
# <a name="apply-and-update-a-changeset-master-data-services"></a>변경 집합 적용 및 업데이트(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  변경 집합은 마스터 데이터에 대해 보류 중인 변경 내용의 컬렉션입니다. 변경 집합을 로컬로 적용하면 변경 집합에서 보류 중인 변경 내용을 확인, 추가, 업데이트 및 삭제할 수 있습니다.  
  
## <a name="prerequisites"></a>사전 요구 사항  
  
-   **탐색기** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다. 자세한 내용은 [기능 영역 권한&#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md)을 참조하세요.  
  
-   엔터티 또는 엔터티의 특성 중 하나에 대한 업데이트 이상의 권한이 있어야 합니다.  
  
-   자신이 소유한 변경 집합 또는 승인을 위해 제출된 변경 집합(엔터티 관리자인 경우)만 볼 수 있습니다.  
  
-   자신이 소유한 변경 집합은 열림 또는 거부됨 상태일 때만 수정할 수 있습니다.  
  
## <a name="to-apply-and-update-a-changeset"></a>변경 집합을 적용 및 업데이트하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 홈 페이지에서 모델 및 버전을 선택하고 **탐색기**를 클릭합니다.  
  
2.  **엔터티** 메뉴에서 엔터티를 클릭합니다.  
  
3.  오른쪽 창에서 **변경 집합** 을 선택하고 확인 및 변경할 변경 집합을 두 번 클릭합니다.  
  
4.  **적용**을 클릭합니다.  
  
     보류 중인 변경 내용이 표의 엔터티 멤버에 적용됩니다. 보류 중인 변경 내용은 강조 표시됩니다.  
  
     멤버를 만들고 삭제하고 업데이트하면 변경 집합이 변경됩니다.  
  
5.  보류 중인 변경 내용을 되돌리려면 **변경 집합** 창에서 표를 마우스 오른쪽 단추로 클릭하고 **되돌리기**를 클릭합니다.  
  
## <a name="next-steps"></a>다음 단계  
 [변경 집합 커밋 또는 제출&#40;Master Data Services&#41;](../master-data-services/commit-or-submit-a-changeset-master-data-services.md)  
  
## <a name="see-also"></a>참고 항목  
 [변경 집합 &#40;MDS(Master Data Services)를 만듭니다&#41;](../master-data-services/create-a-changeset-master-data-services.md)   
 [변경 집합 승인 또는 거부&#40;Master Data Services&#41;](../master-data-services/approve-or-reject-a-changeset-master-data-services.md)  
  
  
