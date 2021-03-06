---
description: Read 메서드
title: Read 메서드 | Microsoft Docs
ms.prod: sql
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Stream::raw_Read
- _Stream::Read
helpviewer_keywords:
- Read method [ADO]
ms.assetid: 838502de-80f1-4eeb-8838-dd3d9403e567
author: rothja
ms.author: jroth
ms.openlocfilehash: 6d4b0ab7c3cc77c1f83eac4c3a30e9f637d950ba
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88989904"
---
# <a name="read-method"></a>Read 메서드
이진 [스트림](./stream-object-ado.md) 개체에서 지정 된 바이트 수를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Variant = Stream.Read ( NumBytes)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *NumBytes*  
 선택 사항입니다. 파일에서 읽을 바이트 수 또는 기본값 인 [Streamreadenum](./streamreadenum.md) 값 **adreadall**을 지정 하는 **Long** 값입니다.  
  
## <a name="return-value"></a>반환 값  
 **Read** 메서드는 **stream** 개체에서 지정 된 바이트 수 또는 전체 스트림을 읽고 결과 데이터를 **Variant**로 반환 합니다.  
  
## <a name="remarks"></a>설명  
 *NumBytes* 가 **스트림에**남아 있는 바이트 수보다 많은 경우 남은 바이트만 반환 됩니다. 읽은 데이터는 *NumBytes*에서 지정한 길이와 일치 하도록 채워지지 않습니다. 읽을 바이트가 남아 있지 않으면 null 값이 있는 변형이 반환 됩니다. **Read** 는 뒤로 읽을 때 사용할 수 없습니다.  
  
> [!NOTE]
>  *NumBytes* 는 항상 바이트를 측정 합니다. 텍스트 **스트림** 개체 (adTypeText[형식](./type-property-ado-stream.md) ) **adTypeText**의 경우 [ReadText](./readtext-method.md)를 사용 합니다.  
  
## <a name="applies-to"></a>적용 대상  
 [스트림 개체(ADO)](./stream-object-ado.md)  
  
## <a name="see-also"></a>참고 항목  
 [ReadText 메서드](./readtext-method.md)