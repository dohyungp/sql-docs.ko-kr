---
description: 구독 유효성 검사
title: 구독 유효성 검사 | Microsoft 문서
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.subscriptions.f1
helpviewer_keywords:
- Validate Subscriptions dialog box
ms.assetid: 0ca39a35-f22c-46c5-82a4-342e34bf5d1b
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: cf4b901c4d830bf333e3078b836eb775ceac6d3a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88470132"
---
# <a name="validate-subscriptions"></a>구독 유효성 검사
[!INCLUDE[sql-asdb](../../includes/applies-to-version/sql-asdb.md)]
  **구독 유효성 검사** 대화 상자를 사용하여 각 구독에 대한 배포 에이전트가 다음에 실행될 때 트랜잭션 게시에 대한 구독의 유효성을 검사할지 지정할 수 있습니다. 유효성 검사 결과는 복제 모니터에 표시됩니다. 자세한 내용은 [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md)을 참조하세요.  

[!INCLUDE[azure-sql-db-replication-supportability-note](../../includes/azure-sql-db-replication-supportability-note.md)]
  
## <a name="options"></a>옵션  
 **모든 SQL Server 구독 유효성 검사**  
 이 게시에 대한 모든 SQL Server 구독 데이터의 유효성을 검사하려면 선택합니다.  
  
 **다음 구독 유효성 검사**  
 모든 구독의 유효성을 검사하지 않으려면 선택합니다. 목록에서 유효성을 검사할 구독을 선택합니다.  
  
 **유효성 검사 옵션**  
 **구독 유효성 검사 옵션** 대화 상자에 액세스하려면 클릭합니다. 이 대화 상자를 사용하여 행 개수 유효성 검사 또는 이진 체크섬 유효성 검사를 사용할지 여부를 지정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [복제된 데이터의 유효성 검사](../../relational-databases/replication/validate-data-at-the-subscriber.md)  
  
  
