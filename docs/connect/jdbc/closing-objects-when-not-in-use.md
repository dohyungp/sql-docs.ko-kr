---
description: 개체가 사용되고 있지 않을 때 닫기
title: 개체가 사용되고 있지 않을 때 닫기 | Microsoft Docs
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: ce8f9b35-c761-4b0c-9a46-985eef2c2e0b
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0c8e1242f5090e347dd3dd61d42fedd3698613cb
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88438455"
---
# <a name="closing-objects-when-not-in-use"></a>개체가 사용되고 있지 않을 때 닫기
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]의 개체, 특히 [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)이나 [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md), [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 또는 [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)와 같은 명령문 개체 중 하나를 사용할 경우 더 이상 필요하지 않으면 close 메서드를 사용하여 해당 개체를 명시적으로 닫아야 합니다. 이를 통해 Java Virtual Machine 가비지 수집기가 비울 때까지 기다리는 대신 가능한 빨리 드라이버 및 서버 리소스를 비워 성능이 향상됩니다.  
  
 개체 닫기는 스크롤 잠금을 사용할 때 서버에서 훌륭한 동시성을 유지 관리하는 데 특히 중요합니다. 마지막을 액세스한 인출 버퍼의 스크롤 잠금은 결과 집합이 닫힐 때까지 보존됩니다. 이와 유사하게 명령문 준비 핸들은 문이 닫힐 때까지 보존됩니다. 여러 명령문에 대한 연결을 다시 사용할 경우 범위 밖으로 벗어나게 하기 전에 명령문을 닫으면 서버가 준비 핸들을 이전에 정리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [JDBC 드라이버로 성능 및 안정성 개선](../../connect/jdbc/improving-performance-and-reliability-with-the-jdbc-driver.md)  
  
  
