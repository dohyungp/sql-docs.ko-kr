---
description: getDate 메서드(java.lang.String)(SQLServerResultSet)
title: getDate 메서드(java.lang.String) 열 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getDate (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 821058ae-cbe3-4a14-aa02-d55e45491437
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 774923c62c8fcbe70bfee39b975e14e47adebaf1
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88436355"
---
# <a name="getdate-method-javalangstring-sqlserverresultset"></a>getDate 메서드(java.lang.String)(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 행에서 지정된 열 이름의 값을 Java 프로그래밍 언어의 java.sql.Date 개체로 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.sql.Date getDate(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열 이름이 포함된 **문자열**입니다.  
  
## <a name="return-value"></a>반환 값  
 Date 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getDate 메서드는 java.sql.ResultSet 인터페이스의 getDate 메서드에 의해 지정됩니다.  
  
 이 메서드는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] datetime 또는 smalldatetime 데이터 형식의 유효한 날짜 부분을 반환합니다. 이때 시간 부분은 Java 기준 시간인 00:00(자정)으로 설정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [getDate 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getdate-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
