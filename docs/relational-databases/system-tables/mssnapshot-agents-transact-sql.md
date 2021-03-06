---
description: MSsnapshot_agents(Transact-SQL)
title: MSsnapshot_agents (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSsnapshot_agents
- MSsnapshot_agents_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSsnapshot_agents system table
ms.assetid: aeae0a2e-4c21-4c45-be65-1e426fa52bdd
author: markingmyname
ms.author: maghan
ms.openlocfilehash: c5b83521f64253aaa5d4eb6dfd6d5e49eb5d71b4
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89524164"
---
# <a name="mssnapshot_agents-transact-sql"></a>MSsnapshot_agents(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSsnapshot_agents** 테이블에는 로컬 배포자와 연결 된 각 스냅숏 에이전트에 대 한 행이 하나씩 포함 되어 있습니다. 이 테이블은 배포 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**id**|**int**|스냅샷 에이전트의 ID입니다.|  
|**name**|**nvarchar (100)**|스냅샷 에이전트의 이름입니다.|  
|**publisher_id**|**smallint**|게시자의 ID입니다.|  
|**publisher_db**|**sysname**|게시자 데이터베이스의 이름입니다.|  
|**게시물**|**sysname**|게시의 이름입니다.|  
|**publication_type**|**int**|게시의 유형입니다.<br /><br /> **0** = 트랜잭션<br /><br /> **1** = 스냅숏<br /><br /> **2** = 병합.|  
|**local_job**|**bit**|로컬 배포자에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 작업이 있는지 여부를 나타냅니다.|  
|**job_id**|**binary(16)**|작업 ID입니다.|  
|**profile_id**|**int**|[Transact-sql&#41;테이블 &#40;MSagent_profiles](../../relational-databases/system-tables/msagent-profiles-transact-sql.md) 구성 ID입니다.|  
|**dynamic_filter_login**|**sysname**|SUSER_SNAME를 평가 하는 데 사용 되는 값은 파티션을 정의 하는 매개 변수가 있는 필터에서 [transact-sql&#41;함수 &#40;](../../t-sql/functions/suser-sname-transact-sql.md) 합니다. 이 열은 분할된 스냅샷에 사용됩니다.|  
|**dynamic_filter_hostname**|**sysname**|HOST_NAME를 평가 하는 데 사용 되는 값은 파티션을 정의 하는 매개 변수가 있는 필터에서 [transact-sql&#41;함수 &#40;](../../t-sql/functions/host-name-transact-sql.md) 합니다. 이 열은 분할된 스냅샷에 사용됩니다.|  
|**publisher_security_mode**|**smallint**|에이전트가 게시자에 연결할 때 사용하는 보안 모드로 다음 중 하나일 수 있습니다.<br /><br /> **0**  =  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인증<br /><br /> **1**  =  [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 인증입니다.|  
|**publisher_login**|**sysname**|게시자에 연결할 때 사용하는 로그인입니다.|  
|**publisher_password**|**nvarchar (524)**|게시자에 연결할 때 사용하는 암호의 암호화된 값입니다.|  
|**job_step_uid**|**uniqueidentifier**|에이전트가 시작되는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트 작업 단계의 고유 ID입니다.|  
|**job_login**|**sysname**||  
|**job_password**|**nvarchar (524)**||  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블 ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
