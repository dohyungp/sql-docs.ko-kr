---
description: sp_dbremove(Transact-SQL)
title: sp_dbremove (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_dbremove
- sp_dbremove_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_dbremove
ms.assetid: a8513f4a-c025-49c8-99c3-4c83cb7f51ed
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1303996a3ca68c5cc244ed24d0405169a19e4779
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89549896"
---
# <a name="sp_dbremove-transact-sql"></a>sp_dbremove(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  데이터베이스 및 이에 연관된 모든 파일을 제거합니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 대신 [DROP DATABASE](../../t-sql/statements/drop-database-transact-sql.md) 를 사용 하는 것이 좋습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_dbremove [ @dbname = ] 'database' [ , [ @dropdev = ] 'dropdev' ]   
```  
  
## <a name="arguments"></a>인수  
`[ @dbname = ] 'database'` 제거할 데이터베이스의 이름입니다. *데이터베이스* 는 **sysname**이며 기본값은 NULL입니다.  
  
`[ @dropdev = ] 'dropdev'` 이전 버전과의 호환성을 위해서만 제공 되며 현재는 무시 되는 플래그입니다. *dropdev* 에는 **dropdev**값이 있습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="result-sets"></a>결과 집합  
 None  
  
## <a name="permissions"></a>사용 권한  
 **sysadmin** 고정 서버 역할의 멤버 자격이 필요합니다.  
  
## <a name="examples"></a>예  
 다음 예에서는 `sales`라는 데이터베이스 및 이와 연관된 모든 파일을 제거합니다.  
  
```  
EXEC sp_dbremove sales;  
```  
  
## <a name="see-also"></a>참고 항목  
 [ALTER DATABASE &#40;Transact-SQL &#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [CREATE DATABASE&#40;SQL Server Transact-SQL&#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md)   
 [DBCC&#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)   
 [sp_detach_db&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-detach-db-transact-sql.md)  
  
  
