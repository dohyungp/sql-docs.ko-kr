---
description: Close 메서드(ADO)
title: Close 메서드 (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::Close
- _Stream::Close
- _Record::Close
helpviewer_keywords:
- Close method [ADO]
ms.assetid: 3cdf27d1-a180-4cff-8e42-95dec5fb1b55
author: rothja
ms.author: jroth
ms.openlocfilehash: 7843642c38a30d854cb6729fd5a418de8c91f2c7
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88975394"
---
# <a name="close-method-ado"></a>Close 메서드(ADO)
열린 개체와 모든 종속 개체를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.Close  
```  
  
## <a name="remarks"></a>설명  
 **Close** 메서드를 사용 하 여 [연결](./connection-object-ado.md)된 시스템 리소스를 해제 하는 연결, [레코드](./record-object-ado.md), 레코드 [집합](./recordset-object-ado.md)또는 [스트림](./stream-object-ado.md) 개체를 닫을 수 있습니다. 개체를 닫으면 메모리가 제거 되지 않습니다. 속성 설정을 변경 하 고 나중에 다시 열 수 있습니다. 메모리에서 개체를 완전히 제거 하려면 개체를 닫은 다음 개체 변수를 *Nothing* (Visual Basic)으로 설정 합니다.  
  
## <a name="connection"></a>연결  
 **Close** 메서드를 사용 하 여 **연결** 개체를 닫으면 연결과 관련 된 모든 활성 **레코드 집합** 개체도 닫힙니다. 닫는 **connection** 개체와 연결 된 [Command](./command-object-ado.md) 개체는 유지 되지만 더 이상 **연결** 개체와 연결 되지 않습니다. 즉, 해당 [ActiveConnection](./activeconnection-property-ado.md) 속성은 **Nothing**으로 설정 됩니다. 또한 **명령** 개체의 [parameters](./parameters-collection-ado.md) 컬렉션은 공급자가 정의한 매개 변수를 지웁니다.  
  
 나중에 [Open](./open-method-ado-connection.md) 메서드를 호출 하 여 동일 하거나 다른 데이터 소스에 대 한 연결을 다시 설정할 수 있습니다. **연결** 개체가 닫혀 있는 동안 데이터 소스에 대 한 열린 연결이 필요한 메서드를 호출 하면 오류가 발생 합니다.  
  
 연결에서 열려 있는 **레코드 집합** 개체가 있는 동안 **연결** 개체를 닫으면 모든 **레코드 집합** 개체의 보류 중인 변경 내용이 롤백됩니다. 트랜잭션이 진행 되는 동안 **Close** 메서드를 호출 하 여 **연결** 개체를 명시적으로 닫으면 오류가 발생 합니다. 트랜잭션이 진행 되는 동안 **연결** 개체가 범위를 벗어나면 ADO에서 자동으로 트랜잭션을 롤백합니다.  
  
## <a name="recordset-record-stream"></a>레코드 집합, 레코드, 스트림  
 **Close** 메서드를 사용 하 여 **레코드 집합**, **레코드**또는 **스트림** 개체를 닫으면이 특정 개체를 통해 데이터에 대해 연결 된 데이터 및 모든 배타적 액세스가 해제 됩니다. 나중에 [Open](./open-method-ado-recordset.md) 메서드를 호출 하 여 동일 하거나 수정 된 특성으로 개체를 다시 열 수 있습니다.  
  
 **레코드 집합** 개체가 닫혀 있는 동안 라이브 커서를 필요로 하는 메서드를 호출 하면 오류가 발생 합니다.  
  
 즉시 업데이트 모드에서 편집이 진행 중인 경우 **Close** 메서드를 호출 하면 오류가 발생 합니다. 대신 [Update](./update-method.md) 또는 [CancelUpdate](./cancelupdate-method-ado.md) 메서드를 먼저 호출 합니다. 일괄 업데이트 모드에서 **레코드 집합** 개체를 닫으면 마지막 [UpdateBatch](./updatebatch-method.md) 호출 이후의 모든 변경 내용이 손실 됩니다.  
  
 [Clone](./clone-method-ado.md) 메서드를 사용 하 여 열려 있는 **레코드 집합** 개체의 복사본을 만드는 경우 원본 또는 클론을 닫아도 다른 복사본에는 영향을 주지 않습니다.  
  
## <a name="applies-to"></a>적용 대상  

:::row:::
    :::column:::
        [연결 개체(ADO)](./connection-object-ado.md)  
        [레코드 개체(ADO)](./record-object-ado.md)  
    :::column-end:::
    :::column:::
        [레코드 집합 개체(ADO)](./recordset-object-ado.md)  
        [스트림 개체(ADO)](./stream-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>참고 항목  
 [Open 및 Close 메서드 예제 (VB)](./open-and-close-methods-example-vb.md)   
 [Open 및 Close 메서드 예제 (VBScript)](./open-and-close-methods-example-vbscript.md)   
 [Open 및 Close 메서드 예제 (VC + +)](./open-and-close-methods-example-vc.md)   
 [Open 메서드 (ADO 연결)](./open-method-ado-connection.md)   
 [Open 메서드 (ADO 레코드 집합)](./open-method-ado-recordset.md)   
 [Save 메서드](./save-method.md)