---
title: sys. dm_pdw_nodes_exec_query_plan (Transact-sql) | Microsoft Docs
description: 계획 핸들로 지정 된 일괄 처리에 대 한 XML 형식의 실행 계획을 반환 하는 동적 관리 뷰입니다. 계획 핸들로 지정된 계획은 캐시되거나 현재 실행 중일 수 있습니다.
ms.custom: ''
ms.date: 10/14/2019
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: ''
author: XiaoyuMSFT
ms.author: xiaoyul
monikerRange: =azure-sqldw-latest || = sqlallproducts-allversions
ms.openlocfilehash: 6a11571ab7e4de54dbae73ae1f1252c88c2e2dca
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87395942"
---
# <a name="syspdw_nodes_dm_exec_query_plan-transact-sql"></a>sys. pdw_nodes_dm_exec_query_plan (Transact-sql)
[!INCLUDE [asa](../../includes/applies-to-version/asa.md)]

계획 핸들로 지정한 일괄 처리에 대한 XML 형식의 실행 계획을 반환합니다. 계획 핸들로 지정된 계획은 캐시되거나 현재 실행 중일 수 있습니다.  

## <a name="table-returned"></a>반환 된 테이블  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**pdw_node_id**|**int**|노드와 연결 된 고유 숫자 ID입니다.| 
|**dbid**|**smallint**|이 계획에 해당하는 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 컴파일할 당시 유효했던 컨텍스트 데이터베이스의 ID입니다. 계획 되지 않은 SQL 문 및 준비 된 SQL 문의 경우 문이 컴파일된 데이터베이스의 ID입니다.<br /><br /> 열이 Null 값을 허용합니다.|  
|**objectid**|**int**|이 쿼리 계획에 대한 저장 프로시저나 사용자 정의 함수와 같은 개체의 ID입니다. 임시 및 준비된 일괄 처리의 경우 이 열은 **Null**입니다.<br /><br /> 열이 Null 값을 허용합니다.|  
|**number**|**smallint**|번호가 매겨진 저장 프로시저 정수입니다. 임시 및 준비된 일괄 처리의 경우 이 열은 **Null**입니다.<br /><br /> 열이 Null 값을 허용합니다.| 
|**됨**|**bit**|해당 저장 프로시저가 암호화되었는지 여부를 나타냅니다.<br /><br /> 0 = 암호화되지 않음<br /><br /> 1 = 암호화됨<br /><br /> 열은 Null을 허용하지 않습니다.|  
|**query_plan**|**xml**|*Plan_handle*지정 된 쿼리 실행 계획의 컴파일 시간 실행 계획 표현을 포함 합니다. 실행 계획은 XML 형식입니다. 임시 [!INCLUDE[tsql](../../includes/tsql-md.md)] 문, 저장 프로시저 호출, 사용자 정의 함수 호출 등이 포함된 각 일괄 처리에 대해 계획 하나가 생성됩니다.<br /><br /> 열이 Null 값을 허용합니다.|  
  
## <a name="remarks"></a>설명  
[Dm_exec_query_plan](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-plan-transact-sql?view=sql-server-ver15) 적용 됩니다.  
  
## <a name="permissions"></a>사용 권한  
 서버에 대 한 **sysadmin** 서버 역할 또는 `VIEW SERVER STATE` 권한이 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;SQL Data Warehouse 및 병렬 데이터 웨어하우스 동적 관리 뷰](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  

 ## <a name="next-steps"></a>다음 단계
 더 많은 개발 팁은 [SQL Data Warehouse 개발 개요](https://docs.microsoft.com/azure/sql-data-warehouse/sql-data-warehouse-overview-develop)를 참조하세요.