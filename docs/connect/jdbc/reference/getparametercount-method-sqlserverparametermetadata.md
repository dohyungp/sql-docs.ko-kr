---
description: getParameterCount 메서드(SQLServerParameterMetaData)
title: getParameterCount 메서드(SQLServerParameterMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerParameterMetaData.getParameterCount
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 7dbbdacb-74ef-42e7-9bdc-a3229505dad8
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0b79fbb9b2da9d72067931e3b741839a57b1dba6
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88435045"
---
# <a name="getparametercount-method-sqlserverparametermetadata"></a>getParameterCount 메서드(SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md) 개체에 포함된 정보와 관련된 [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 개체의 매개 변수 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public int getParameterCount()  
```  
  
## <a name="return-value"></a>Return Value  
 매개 변수 수를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getParameterCount 메서드는 java.sql.ParameterMetaData 인터페이스의 getParameterCount 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerParameterMetaData 메서드](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [SQLServerParameterMetaData 멤버](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [SQLServerParameterMetaData 클래스](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  
