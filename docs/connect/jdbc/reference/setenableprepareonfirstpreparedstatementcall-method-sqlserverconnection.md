---
description: setEnablePrepareOnFirstPreparedStatementCall 메서드(SQLServerConnection)
title: setEnablePrepareOnFirstPreparedStatementCall 메서드(SQLServerConnection) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.setEnablePrepareOnFirstPreparedStatementCall
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ''
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7b631c70f7b146f16b2daf41333316376c2b409a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88431925"
---
# <a name="setenableprepareonfirstpreparedstatementcall-method-sqlserverconnection"></a>setEnablePrepareOnFirstPreparedStatementCall 메서드(SQLServerConnection)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

 특정 연결 인스턴스에 대한 동작을 지정합니다. 값이 false일 경우에는 첫 번째 실행에서 sp_executesql이 호출되고 문은 준비되지 않습니다. 두 번째 실행에서는 sp_prepexec가 호출되고 준비된 문 핸들이 실제로 설정됩니다. 다음 실행에서는 sp_execute를 호출합니다. 이렇게 하면 문이 한 번만 실행될 때 준비된 문 닫기에서 sp_unprepare를 사용할 필요가 없습니다.

## <a name="syntax"></a>구문  
  
```  
  
public void setEnablePrepareOnFirstPreparedStatementCall(boolean enablePrepareOnFirstPreparedStatementCall)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *enablePrepareOnFirstPreparedStatementCall*  
  
 **enablePrepareOnFirstPreparedStatementCall** 연결 속성의 새 값입니다.  
 
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
 
## <a name="remarks"></a>설명  
 이 메서드는 JDBC 드라이버 버전 6.4 이상 버전에서 사용할 수 있습니다.
 
## <a name="see-also"></a>참고 항목  
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
