---
description: sys.traces(Transact-SQL)
title: sys. 추적 (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- traces
- sys.traces_TSQL
- sys.traces
- traces_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.traces catalog view
ms.assetid: 4a03be22-b7da-4e2a-97ff-94bed890a620
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 31de0333847573b46872cfa5a3441dd92820151f
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89544961"
---
# <a name="systraces-transact-sql"></a>sys.traces(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **Sys. 추적** 카탈로그 뷰에는 시스템에서 현재 실행 중인 추적이 포함 되어 있습니다. 이 보기는 **fn_trace_getinfo** 함수를 대체 하기 위한 것입니다.  
  
 지원 되는 추적 이벤트의 전체 목록은 [SQL Server 이벤트 클래스 참조](../../relational-databases/event-classes/sql-server-event-class-reference.md)를 참조 하세요.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 대신 확장 이벤트 카탈로그 뷰를 사용하십시오.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|추적 ID입니다.|  
|**status**|**int**|추적 상태입니다.<br /><br /> 0 = 중지됨<br /><br /> 1 = 실행 중|  
|**path**|**nvarchar(260)**|추적 파일의 경로입니다. 이 값은 행 집합 추적의 경우 Null입니다.|  
|**max_size**|**bigint**|최대 추적 파일 크기 한도(MB)입니다. 이 값은 행 집합 추적의 경우 Null입니다.|  
|**stop_time**|**datetime**|실행 중인 추적을 중지할 시간입니다.|  
|**max_files**|**int**|최대 롤오버 파일 수입니다. 최대값을 설정하지 않으면 이 값은 Null입니다.|  
|**is_rowset**|**bit**|1 = 행 집합 추적입니다.|  
|**is_rollover**|**bit**|1 = 롤오버 옵션이 설정되어 있습니다.|  
|**is_shutdown**|**bit**|1 = 종료 옵션이 설정되어 있습니다.|  
|**is_default**|**bit**|1 = 기본 추적입니다.|  
|**buffer_count**|**int**|추적에서 사용하는 메모리 내 버퍼 수입니다.|  
|**buffer_size**|**int**|각 버퍼의 크기(KB)입니다.|  
|**file_position**|**bigint**|마지막 추적 파일 위치입니다. 이 값은 행 집합 추적의 경우 Null입니다.|  
|**reader_spid**|**int**|행 집합 추적 판독기 세션 ID입니다. 이 값은 파일 추적의 경우 Null입니다.|  
|**start_time**|**datetime**|추적 시작 시간입니다.|  
|**last_event_time**|**datetime**|마지막 이벤트 발생 시간입니다.|  
|**event_count**|**bigint**|발생한 총 이벤트 수입니다.|  
|**dropped_event_count**|**int**|삭제된 총 이벤트 수입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [개체 카탈로그 뷰 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [trace_categories &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [trace_columns &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [trace_events &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [trace_event_bindings &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [trace_subclass_values &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
