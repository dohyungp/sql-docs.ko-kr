---
description: sys. pdw_diag_events (Transact-sql)
title: sys. pdw_diag_events (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 59bb3e9c-2829-49a0-b382-652ed1f54f88
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: c38eb1e89f3e06bee1f3ec2841efc72845a96386
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88490292"
---
# <a name="syspdw_diag_events-transact-sql"></a>sys. pdw_diag_events (Transact-sql)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  시스템의 진단 세션에 포함할 수 있는 이벤트에 대 한 정보를 보관 합니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|**name**|**nvarchar(255)**|특정 진단 이벤트의 이름입니다.||  
|**source**|**nvarchar(255)**|이벤트 원본 (엔진, 일반, dms 등)||  
|**is_enabled**|**bit**|이벤트를 게시할지 여부를 나타냅니다.||  
  
## <a name="see-also"></a>참고 항목  
 [SQL Data Warehouse 및 병렬 Data Warehouse 카탈로그 뷰](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  
