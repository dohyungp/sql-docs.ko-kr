---
title: XML 열에서 뷰 만들기 | Microsoft 문서
description: xml 데이터 형식의 value() 메서드를 사용하여 xml 형식 열에서 값을 검색하는 뷰를 만드는 방법을 알아봅니다.
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: MightyPen
ms.author: genemi
ms.openlocfilehash: 5d4a9d8d0aa40f8454a2bd0fd089022630c34ca2
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85691531"
---
# <a name="create-views-over-xml-columns"></a>XML 열에서 뷰 만들기
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  **xml** 유형 열을 사용하여 뷰를 만들 수 있습니다. 다음 예에서는 `xml` xml **데이터 형식의** value() **메서드를 사용하여** 유형 열의 값을 검색하는 뷰를 만듭니다.  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 뷰에 대해 다음 쿼리를 실행합니다.  
  
```  
SELECT *   
FROM   MyView  
```  
  
 다음은 결과입니다.  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 다음은 **xml** 데이터 형식을 사용하여 뷰를 만드는 방법에 대한 설명입니다.  
  
-   xml 데이터 형식은 구체화된 뷰에서 만들 수 있습니다. 구체화된 뷰는 XML 데이터 형식의 메서드를 기반으로 할 수 없습니다. 하지만 기본 테이블에 있는 xml 유형의 열과는 다른 XML 스키마 컬렉션으로 캐스팅할 수 있습니다.  
  
-   분산형 분할 뷰에서는 **xml** 데이터 형식을 사용할 수 없습니다.  
  
-   뷰에 대해 실행하는 SQL 조건자는 뷰 정의의 XQuery에 밀어넣지 못합니다.  
  
-   뷰의 XML 데이터 형식 메서드는 업데이트할 수 없습니다.  
  
  
