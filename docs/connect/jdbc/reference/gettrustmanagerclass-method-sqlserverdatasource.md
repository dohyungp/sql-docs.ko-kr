---
description: getTrustManagerClass 메서드(SQLServerDataSource)
title: getTrustManagerClass 메서드(SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getTrustManagerClass
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ''
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7c09a848670270cc4c22903207637b96ddb1fddc
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88433985"
---
# <a name="gettrustmanagerclass-method-sqlserverdatasource"></a>getTrustManagerClass 메서드(SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  TrustManagerClass 연결 속성의 문자열 값을 반환합니다.
  
## <a name="syntax"></a>구문  
  
```  
  
public java.lang.String getTrustManagerClass()  
```  
  
## <a name="return-value"></a>Return Value  
 **문자열**은 TrustManagerClass 연결 속성 값을 포함하거나 값이 설정되어 있지 않은 경우 Null입니다.  
  
## <a name="remarks"></a>설명  
 TrustManagerClass 속성이 설정되어 있지 않은 경우 [getTrustManagerClass](../../../connect/jdbc/reference/gettrustmanagerclass-method-sqlserverdatasource.md) 메서드는 Null을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerDataSource 멤버](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 클래스](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
