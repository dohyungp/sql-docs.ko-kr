---
description: setMaxFieldSize 메서드(SQLServerStatement)
title: setMaxFieldSize 메서드(SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.setMaxFieldSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 38f7fc1d-acad-4d10-9fc8-3c0669d93b07
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b63564218687d9cc12973d044f04c94ec056f615
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88431695"
---
# <a name="setmaxfieldsize-method-sqlserverstatement"></a>setMaxFieldSize 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  문자 또는 이진 값을 저장하는 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 열의 최대 바이트 수에 대한 제한을 지정된 바이트 수로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setMaxFieldSize(int max)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *max*  
  
 바이트의 최대 길이를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 setMaxFieldSize 메서드는 java.sql.Statement 인터페이스의 setMaxFieldSize 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
