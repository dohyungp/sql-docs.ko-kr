---
description: sys.dm_exec_background_job_queue_stats(Transact-SQL)
title: sys. dm_exec_background_job_queue_stats (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_exec_background_job_queue_stats
- sys.dm_exec_background_job_queue_stats
- dm_exec_background_job_queue_stats_TSQL
- sys.dm_exec_background_job_queue_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_exec_background_job_queue_stats dynamic management view
ms.assetid: 27f62ab5-46c4-417e-814d-8d6437034d1c
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: c79c0897f8be3997133cedaf54f42df55ea90486
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89534180"
---
# <a name="sysdm_exec_background_job_queue_stats-transact-sql"></a>sys.dm_exec_background_job_queue_stats(Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  비동기(백그라운드) 실행을 위해 제출된 각 쿼리 프로세서 작업에 대해 집계 통계를 제공하는 행을 반환합니다.  
  
> [!NOTE]  
>  또는에서이를 호출 하려면 [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] 이름 **sys. dm_pdw_nodes_exec_background_job_queue_stats**을 사용 합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**queue_max_len**|**int**|최대 큐 길이입니다.|  
|**enqueued_count**|**int**|큐에 성공적으로 게시된 요청 수입니다.|  
|**started_count**|**int**|실행이 시작된 요청 수입니다.|  
|**ended_count**|**int**|서비스에 성공하거나 실패한 요청 수입니다.|  
|**failed_lock_count**|**int**|잠금 경합이나 교착 상태로 인해 실패한 요청 수입니다.|  
|**failed_other_count**|**int**|다른 이유로 인해 실패한 요청 수입니다.|  
|**failed_giveup_count**|**int**|다시 시도 제한에 도달하여 실패한 요청 수입니다.|  
|**enqueue_failed_full_count**|**int**|큐가 꽉 차서 큐에 넣지 못한 시도 수입니다.|  
|**enqueue_failed_duplicate_count**|**int**|중복으로 큐에 넣는 시도 수입니다.|  
|**elapsed_avg_ms**|**int**|요청의 평균 경과 시간(밀리초)입니다.|  
|**elapsed_max_ms**|**int**|가장 긴 요청의 경과 시간(밀리초)입니다.|  
|**pdw_node_id**|**int**|**적용 대상**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] , [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> 이 배포가 설정 된 노드의 식별자입니다.|  
  
## <a name="remarks"></a>설명  
 이 뷰는 비동기 업데이트 통계 작업에 대해서만 정보를 반환합니다. 비동기 업데이트 통계에 대 한 자세한 내용은 [통계](../../relational-databases/statistics/statistics.md)를 참조 하세요.  
  
## <a name="permissions"></a>사용 권한

에 [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] 는 `VIEW SERVER STATE` 권한이 필요 합니다.   
[!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]Premium 계층에서는 데이터베이스에 대 한 권한이 필요 합니다 `VIEW DATABASE STATE` . [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)]표준 및 기본 계층에서는 **서버 관리자** 또는 **Azure Active Directory 관리자** 계정이 필요 합니다.   

## <a name="examples"></a>예제  
  
### <a name="a-determining-the-percentage-of-failed-background-jobs"></a>A. 실패한 백그라운드 작업의 백분율 확인  
 다음 예에서는 실행된 모든 쿼리에 대해 실패한 백그라운드 작업의 백분율을 반환합니다.  
  
```  
SELECT   
        CASE ended_count WHEN 0   
                THEN 'No jobs ended'   
                ELSE CAST((failed_lock_count + failed_giveup_count + failed_other_count) / CAST(ended_count AS float) * 100 AS varchar(20))   
        END AS [Percent Failed]  
FROM sys.dm_exec_background_job_queue_stats;  
GO  
```  
  
### <a name="b-determining-the-percentage-of-failed-enqueue-attempts"></a>B. 큐에 넣지 못한 시도의 백분율 확인  
 다음 예에서는 실행된 모든 쿼리에 대해 큐에 넣지 못한 시도의 백분율을 반환합니다.  
  
```  
SELECT   
        CASE enqueued_count WHEN 0   
                THEN 'No jobs posted'   
                ELSE CAST((enqueue_failed_full_count + enqueue_failed_duplicate_count) / CAST(enqueued_count + enqueue_failed_full_count + enqueue_failed_duplicate_count AS float) * 100 AS varchar(20))   
        END AS [Percent Enqueue Failed]  
FROM sys.dm_exec_background_job_queue_stats;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [실행 관련 동적 관리 뷰 및 함수&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


