---
description: sys.registered_search_property_lists(Transact-SQL)
title: sys. registered_search_property_lists (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- registered_search_property_lists_TSQL
- sys.registered_search_property_lists
- registered_search_property_lists
- sys.registered_search_property_lists_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- full-text search [SQL Server], search property lists
- sys.registered_search_property_lists catalog view
- search property lists [SQL Server], viewing
ms.assetid: 630d4caa-9bea-4cd3-a5b1-01098b0855fc
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
ms.openlocfilehash: 9137345d642f1bc599ace1645cd5e441b927c4fd
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88447857"
---
# <a name="sysregistered_search_property_lists-transact-sql"></a>sys.registered_search_property_lists(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  현재 데이터베이스에 각 검색 속성 목록당 한 개의 행을 포함합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**property_list_id**|**int**|속성 목록의 ID입니다.|  
|**name**|**sysname**|속성 목록의 이름입니다.|  
|**create_date**|**datetime**|속성 목록을 만든 날짜입니다.|  
|**modify_date**|**datetime**|ALTER 문을 사용하여 속성 목록을 마지막으로 수정한 날짜입니다.|  
|**principal_id**|**int**|속성 목록의 소유자입니다.|  
  
## <a name="remarks"></a>설명  
 자세한 내용은 [검색 속성 목록을 사용하여 문서 속성 검색](../../relational-databases/search/search-document-properties-with-search-property-lists.md)을 참조하세요.  
  
## <a name="permissions"></a>사용 권한  
 사용자가 소유하고 있거나 일부 REFERENCE 권한이 부여된 검색 속성만 검색 속성 목록에서 메타데이터를 볼 수 있도록 제한됩니다.  
  
> [!NOTE]  
>  검색 속성 목록 소유자는 목록에 대한 REFERENCE 또는 CONTROL 권한을 부여할 수 있습니다. CONTROL 권한을 가진 사용자는 다른 사용자에게 REFERENCE 권한을 부여할 수도 있습니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] 데이터베이스에 있는 검색 속성 목록의 ID와 이름을 표시합니다.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT property_list_id, name FROM sys.registered_search_property_lists;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [ALTER FULLTEXT INDEX&#40;Transact-SQL&#41;](../../t-sql/statements/alter-fulltext-index-transact-sql.md)   
 [sys.fulltext_indexes&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)  
  
  
