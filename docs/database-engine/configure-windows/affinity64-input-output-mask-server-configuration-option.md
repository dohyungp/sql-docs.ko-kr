---
title: affinity64 I/O mask 서버 구성 옵션 | Microsoft Docs
description: affinity64 I/O mask 옵션에 대해 알아봅니다. 이 옵션을 사용하여 SQL Server 디스크 I/O를 지정된 CPU 하위 집합에 바인딩하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- binding processors [SQL Server]
- affinity64 I/O mask option
ms.assetid: d304eae7-5116-40ee-a0fa-0a3c0bc20c01
author: markingmyname
ms.author: maghan
ms.openlocfilehash: c056959118deba7473471808db228d646fc7f64c
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85724010"
---
# <a name="affinity64-input-output-mask-server-configuration-option"></a>affinity64 Input-Output mask 서버 구성 옵션
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **affinity64 I/O mask** 는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affinity I/O mask **옵션과 유사한 방식으로** 디스크 I/O를 지정한 CPU 하위 집합으로 바인딩합니다. **affinity I/O mask** 를 사용하여 처음 32개의 프로세서를 바인딩한 다음 **affinity64 I/O mask** 를 사용하여 컴퓨터의 남은 프로세서를 바인딩하세요. **affinity64 I/O mask**를 다시 구성하는 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스를 다시 시작해야 합니다. 이 옵션은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]64비트 버전에서만 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선호도 입력-출력 마스크 서버 구성 옵션](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)   
 [리소스 사용 모니터링&#40;시스템 모니터&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)   
 [서버 구성 옵션&#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE&#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)  
  
  
