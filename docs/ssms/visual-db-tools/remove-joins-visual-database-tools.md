---
description: 조인 제거(Visual Database Tools)
title: 조인 제거
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.openlocfilehash: b13ffa676da9c96baa120ced607ca7607dea96d9
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88497132"
---
# <a name="remove-joins-visual-database-tools"></a>조인 제거(Visual Database Tools)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
내부 조인 또는 외부 조인을 통해 테이블을 더 이상 조인하지 않으려면 테이블 간의 조인을 제거하면 됩니다. 예를 들어 [쿼리 및 뷰 디자이너](../../ssms/visual-db-tools/query-and-view-designer-tools-visual-database-tools.md) 가 두 테이블 간에 자동으로 만든 조인을 제거할 수 있습니다.  
  
> [!NOTE]  
> 쿼리에서 조인을 제거해도 데이터베이스에서의 기본 관계는 변경되지 않습니다.  
  
조인된 두 테이블이 쿼리의 일부이고 두 테이블 간의 조인 조건을 모두 제거하는 경우 결과 쿼리는 두 테이블의 결과 즉, CROSS JOIN이 됩니다.  
  
### <a name="to-remove-a-join"></a>조인을 제거하려면  
  
-   [다이어그램 창](../../ssms/visual-db-tools/diagram-pane-visual-database-tools.md)에서 제거할 조인의 조인 선을 선택한 다음 Delete 키를 누릅니다. 한 번에 조인 선을 여러 개 선택하여 삭제할 수 있습니다.  
  
쿼리 및 뷰 디자이너는 조인 선을 제거하고 [SQL 창](../../ssms/visual-db-tools/sql-pane-visual-database-tools.md)에서 문을 변경합니다.  
  
## <a name="see-also"></a>참고 항목  
[테이블 자동 조인&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/join-tables-automatically-visual-database-tools.md)  
[테이블 수동 조인&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/join-tables-manually-visual-database-tools.md)  
[조인을 사용한 쿼리&#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/query-with-joins-visual-database-tools.md)  
  
