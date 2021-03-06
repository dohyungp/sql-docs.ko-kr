---
title: 네임 스페이스 uri 함수 (XQuery) | Microsoft Docs
description: XQuery에서 네임 스페이스 uri 함수를 사용 하 여 지정 된 QName의 네임 스페이스 URI를 반환 하는 방법에 대해 알아봅니다.
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:namespace-uri function
- namespace-uri function
ms.assetid: 9b48d216-26c8-431d-9ab4-20ab187917f4
author: rothja
ms.author: jroth
ms.openlocfilehash: 58522408e025b45c2424272942055bb7e0d374d4
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86920059"
---
# <a name="functions-on-nodes---namespace-uri"></a>노드 함수 - namespace-uri
[!INCLUDE[sqlserver](../includes/applies-to-version/sqlserver.md)]

  *$Arg* 에 지정 된 QName의 네임 스페이스 URI를 xs: string으로 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
fn:namespace-uri() as xs:string  
fn:namespace-uri($arg as node()?) as xs:string  
```  
  
## <a name="arguments"></a>인수  
 *$arg*  
 네임스페이스 URI 부분이 검색되는 노드 이름입니다.  
  
## <a name="remarks"></a>설명  
  
-   인수가 생략된 경우 기본값은 컨텍스트 노드입니다.  
  
-   SQL Server에서 인수가 없는 **fn: namespace-uri ()** 는 컨텍스트 종속 조건자의 컨텍스트에서만 사용할 수 있습니다. 특히 사용 시 대괄호([])로 묶어야 합니다.  
  
-   *$Arg* 빈 시퀀스인 경우 길이가 0 인 문자열이 반환 됩니다.  
  
-   *$Arg* 이 확장 된 QName이 네임 스페이스에 없는 element 또는 attribute 노드인 경우 함수는 길이가 0 인 문자열을 반환 합니다.  
  
## <a name="examples"></a>예  
 이 항목에서는 AdventureWorks 데이터베이스의 다양 한 **xml** 유형 열에 저장 된 xml 인스턴스에 대 한 XQuery 예를 제공 합니다.  
  
### <a name="a-retrieve-namespace-uri-of-a-specific-node"></a>A. 특정 노드의 네임스페이스 URI 검색  
 다음은 형식화되지 않은 XML 인스턴스에 대해 지정된 쿼리입니다. 쿼리 식 `namespace-uri(/ROOT[1])`은 지정된 노드의 네임스페이스 URI 부분을 검색합니다.  
  
```  
set @x='<ROOT><a>111</a></ROOT>'  
SELECT @x.query('namespace-uri(/ROOT[1])')  
```  
  
 지정된 QName에 네임스페이스 URI 부분이 없고 로컬 이름 부분만 있는 경우 결과는 길이가 0인 문자열입니다.  
  
 다음 쿼리는 명령으로 형식화 된 **xml** 열에 대해 지정 됩니다. 식은 `namespace-uri(/AWMI:root[1]/AWMI:Location[1])` `Location` <> 요소의 첫 번째 <> 요소 자식의 네임 스페이스 URI를 반환 합니다 `root` .  
  
```  
SELECT Instructions.query('  
declare namespace AWMI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" ;  
     namespace-uri(/AWMI:root[1]/AWMI:Location[1])') as Result  
FROM Production.ProductModel  
WHERE ProductModelID=7  
```  
  
 다음은 결과입니다.  
  
```  
https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions  
```  
  
### <a name="b-using-namespace-uri-without-argument-in-a-predicate"></a>B. 조건자의 인수 없이 namespace-uri() 사용  
 다음 쿼리는 형식화된 CatalogDescription xml 열에 대해 지정되었습니다. 이 식은 네임스페이스 URI가 `https://www.adventure-works.com/schemas/OtherFeatures`인 모든 요소 노드를 반환합니다. 네임 스페이스**uri ()** 함수는 인수 없이 지정 되 고 컨텍스트 노드를 사용 합니다.  
  
```  
SELECT CatalogDescription.query('  
declare namespace p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
   /p1:ProductDescription//*[namespace-uri() = "https://www.adventure-works.com/schemas/OtherFeatures"]  
') as Result  
FROM Production.ProductModel  
WHERE ProductModelID=19  
```  
  
 다음은 결과 중 일부입니다.  
  
```  
<p1:wheel xmlns:p1="https://www.adventure-works.com/schemas/OtherFeatures">High performance wheels.</p1:wheel>  
<p2:saddle xmlns:p2="https://www.adventure-works.com/schemas/OtherFeatures">  
  <p3:i xmlns:p3="http://www.w3.org/1999/xhtml">Anatomic design</p3:i> and made from durable leather for a full-day of riding in comfort.</p2:saddle>  
...  
```  
  
 이전 쿼리의 네임스페이스 URI를 `https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain`으로 바꿀 수 있습니다. 그런 다음 `ProductDescription` 확장 된 QName의 네임 스페이스 URI 부분을 포함 하는 <> 요소의 모든 요소 노드 자식을 받게 됩니다 `https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain` .  
  
### <a name="implementation-limitations"></a>구현 시 제한 사항  
 제한 사항은 다음과 같습니다.  
  
-   **네임 스페이스 uri ()** 함수는 Xs: anyURI 대신 xs: string 형식의 인스턴스를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [노드의 함수](https://msdn.microsoft.com/library/09a8affa-3341-4f50-aebc-fdf529e00c08)   
 [로컬 이름 함수 &#40;XQuery&#41;](../xquery/functions-on-nodes-local-name.md)  
  
  
