---
description: systranschemas(Transact-SQL)
title: systranschemas (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- systranschemas
- systranschemas_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- systranschemas system table
ms.assetid: 864c3966-cb61-4f2b-8939-ccda112de853
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0f034b802eca4a3349b69067d10280b886ffb22a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88446522"
---
# <a name="systranschemas-transact-sql"></a>systranschemas(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **Systranschemas** 테이블은 트랜잭션 및 스냅숏 게시에 게시 된 아티클의 스키마 변경을 추적 하는 데 사용 됩니다. 이 테이블은 게시 및 구독 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**tabid**|**int**|스키마가 변경된 테이블 아티클을 식별합니다.|  
|**startlsn**|**binary**|스키마 변경 시작 부분의 LSN 값입니다.|  
|**endlsn**|**binary**|스키마 변경 끝 부분의 LSN 값입니다.|  
|**typeid**|**int**|스키마 변경의 유형입니다.|  
  
## <a name="see-also"></a>관련 항목  
 [복제 테이블&#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  
