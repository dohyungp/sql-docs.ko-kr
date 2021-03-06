---
description: getColumnLabel 메서드(SQLServerResultSetMetaData)
title: getColumnLabel 메서드(SQLServerResultSetMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSetMetaData.getColumnLabel
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: cf67692c-24aa-49e6-8e88-a47d4e8c021c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f3ec52922e4772b93ffc62f7956a264ff831ffc7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88436575"
---
# <a name="getcolumnlabel-method-sqlserverresultsetmetadata"></a>getColumnLabel 메서드(SQLServerResultSetMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 열의 출력 및 표시에 사용되는 권장 제목을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.lang.String getColumnLabel(int column)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *column*  
  
 열 인덱스를 나타내는 **int**입니다.  
  
## <a name="return-value"></a>반환 값  
 열의 제목이 들어 있는 **문자열**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getColumnLabel 메서드는 java.sql.ResultSetMetaData 인터페이스의 getColumnLabel 메서드에 의해 지정됩니다.  
  
 이 메서드는 열의 별칭 이름을 반환합니다. 별칭 이름을 사용할 수 없으면 이 메서드는 열 이름을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerResultSetMetaData 메서드](../../../connect/jdbc/reference/sqlserverresultsetmetadata-methods.md)   
 [SQLServerResultSetMetaData 멤버](../../../connect/jdbc/reference/sqlserverresultsetmetadata-members.md)   
 [SQLServerResultSetMetaData 클래스](../../../connect/jdbc/reference/sqlserverresultsetmetadata-class.md)  
  
  
