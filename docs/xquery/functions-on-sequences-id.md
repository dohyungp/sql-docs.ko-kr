---
title: id 함수 (XQuery) | Microsoft Docs
description: 'XQuery id 함수를 사용 하 여 제공 된 xs: IDREF 값을 사용 하 여 XML 인스턴스의 요소 시퀀스를 문서 순서로 반환 하는 방법에 대해 알아봅니다.'
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql
ms.reviewer: ''
ms.technology: xml
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:id function
- id function
ms.assetid: de99fc60-d0ad-4117-a17d-02bdde6512b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0dacb3e54898ece6222d2f9eb3d7a546c8aa7b76
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85753557"
---
# <a name="functions-on-sequences---id"></a>시퀀스 함수 - id
[!INCLUDE [SQL Server Azure SQL Database ](../includes/applies-to-version/sqlserver.md)]

  *$Arg*에 제공 된 하나 이상의 XS: IDREF 값과 일치 하는 XS: ID 값이 포함 된 요소 노드의 시퀀스를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
fn:id($arg as xs:IDREF*) as element()*  
```  
  
## <a name="arguments"></a>인수  
 *$arg*  
 하나 이상의 xs:IDREF 값입니다.  
  
## <a name="remarks"></a>설명  
 함수 결과는 후보 xs:IDREF 목록에 있는 하나 이상의 xs:IDREF에 일치하는 xs:ID 값이 있는 문서 순서대로 된 XML 인스턴스의 요소 시퀀스입니다.  
  
 요소와 일치하는 xs:IDREF 값이 없으면 이 함수는 빈 시퀀스를 반환합니다.  
  
## <a name="examples"></a>예제  
 이 항목에서는 데이터베이스의 다양 한 **xml** 유형 열에 저장 된 xml 인스턴스에 대 한 XQuery 예를 제공 [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] 합니다.  
  
### <a name="a-retrieving-elements-based-on-the-idref-attribute-value"></a>A. IDREF 특성 값을 기반으로 요소 검색  
 다음 예에서는 fn: id를 사용 하 여 `employee` IDREF manager 특성에 따라 <> 요소를 검색 합니다. 이 예에서 관리자 특성은 IDREF 유형 특성이고 eid 특성은 ID 유형 특성입니다.  
  
 특정 관리자 특성 값의 경우 **id ()** 함수는 `employee` id 유형 특성 값이 입력 IDREF 값과 일치 하는 <> 요소를 찾습니다. 즉, 특정 직원에 대해 **id ()** 함수는 employee manager를 반환 합니다.  
  
 다음은 이 예에서 수행된 작업입니다.  
  
-   XML 스키마 컬렉션이 생성됩니다.  
  
-   형식화 된 **xml** 변수는 xml 스키마 컬렉션을 사용 하 여 생성 됩니다.  
  
-   이 쿼리는 <> 요소의 **manager** IDREF 특성에서 참조 하는 ID 특성 값을 가진 요소를 검색 `employee` 합니다.  
  
```  
-- If exists, drop the XML schema collection (SC).  
-- drop xml schema collection SC  
-- go  
  
create xml schema collection SC as  
'<schema xmlns="http://www.w3.org/2001/XMLSchema" xmlns:e="emp" targetNamespace="emp">  
            <element name="employees" type="e:EmployeesType"/>  
            <complexType name="EmployeesType">  
                 <sequence>  
                      <element name="employee" type="e:EmployeeType" minOccurs="0" maxOccurs="unbounded" />  
                 </sequence>  
            </complexType>    
  
            <complexType name="EmployeeType">  
                        <attribute name="eid" type="ID" />  
                        <attribute name="name" type="string" />  
                        <attribute name="manager" type="IDREF" />  
            </complexType>         
</schema>'  
go  
```  
  
```  
declare @x xml(SC)  
set @x='<e:employees xmlns:e="emp">  
<employee eid="e1" name="Joe" manager="e10" />  
<employee eid="e2" name="Bob" manager="e10" />  
<employee eid="e10" name="Dave" manager="e10" />  
</e:employees>'  
  
select @x.value(' declare namespace e="emp";   
 (fn:id(e:employees/employee[@name="Joe"]/@manager)/@name)[1]', 'varchar(50)')   
Go  
```  
  
 쿼리는 "Dave"를 값으로 반환합니다. 즉 Dave가 Joe의 관리자라는 의미입니다.  
  
### <a name="b-retrieving-elements-based-on-the-orderlist-idrefs-attribute-value"></a>B. OrderList IDREFS 특성 값을 기반으로 요소 검색  
 다음 예에서는 <> 요소의 OrderList 특성이 `Customer` IDREFS 유형 특성입니다. 특정 고객에 대한 주문 ID를 나열합니다. 각 주문 id에는 `Order` 주문 값을 제공 하는> <<> 요소 자식이 있습니다 `Customer` .  
  
 쿼리 식 `data(CustOrders:Customers/Customer[1]/@OrderList)[1]`은 첫 번째 고객에 대한 IDRES 목록에서 첫 번째 값을 검색합니다. 그런 다음이 값은 **id ()** 함수에 전달 됩니다. 그런 다음이 함수는 `Order` OrderID 특성 값이 **id ()** 함수의 입력과 일치 하는 <> 요소를 찾습니다.  
  
```  
drop xml schema collection SC  
go  
create xml schema collection SC as  
'<schema xmlns="http://www.w3.org/2001/XMLSchema" xmlns:Customers="Customers" targetNamespace="Customers">  
            <element name="Customers" type="Customers:CustomersType"/>  
            <complexType name="CustomersType">  
                        <sequence>  
                            <element name="Customer" type="Customers:CustomerType" minOccurs="0" maxOccurs="unbounded" />  
                        </sequence>  
            </complexType>  
             <complexType name="OrderType">  
                <sequence minOccurs="0" maxOccurs="unbounded">  
                            <choice>  
                                <element name="OrderValue" type="integer" minOccurs="0" maxOccurs="unbounded"/>  
                            </choice>  
                </sequence>                                             
                <attribute name="OrderID" type="ID" />  
            </complexType>  
  
            <complexType name="CustomerType">  
                <sequence minOccurs="0" maxOccurs="unbounded">  
                            <choice>  
                                <element name="spouse" type="string" minOccurs="0" maxOccurs="unbounded"/>  
                                <element name="Order" type="Customers:OrderType" minOccurs="0" maxOccurs="unbounded"/>  
                            </choice>  
                </sequence>                                             
                <attribute name="CustomerID" type="string" />  
                <attribute name="OrderList" type="IDREFS" />  
            </complexType>  
 </schema>'  
go  
declare @x xml(SC)  
set @x='<CustOrders:Customers xmlns:CustOrders="Customers">  
                <Customer CustomerID="C1" OrderList="OrderA OrderB"  >  
                              <spouse>Jenny</spouse>  
                                <Order OrderID="OrderA"><OrderValue>11</OrderValue></Order>  
                                <Order OrderID="OrderB"><OrderValue>22</OrderValue></Order>  
  
                </Customer>  
                <Customer CustomerID="C2" OrderList="OrderC OrderD" >  
                                <spouse>John</spouse>  
                                <Order OrderID="OrderC"><OrderValue>33</OrderValue></Order>  
                                <Order OrderID="OrderD"><OrderValue>44</OrderValue></Order>  
  
                        </Customer>  
                <Customer CustomerID="C3"  OrderList="OrderE OrderF" >  
                                <spouse>Jane</spouse>  
                                <Order OrderID="OrderE"><OrderValue>55</OrderValue></Order>  
                                <Order OrderID="OrderF"><OrderValue>55</OrderValue></Order>  
                </Customer>  
                <Customer CustomerID="C4"  OrderList="OrderG"  >  
                                <spouse>Tim</spouse>  
                                <Order OrderID="OrderG"><OrderValue>66</OrderValue></Order>  
                        </Customer>  
                <Customer CustomerID="C5"  >  
                </Customer>  
                <Customer CustomerID="C6" >  
                </Customer>  
                <Customer CustomerID="C7"  >  
                </Customer>  
</CustOrders:Customers>'  
select @x.query('declare namespace CustOrders="Customers";  
  id(data(CustOrders:Customers/Customer[1]/@OrderList)[1])')  
  
-- result  
<Order OrderID="OrderA">  
  <OrderValue>11</OrderValue>  
</Order>  
```  
  
### <a name="implementation-limitations"></a>구현 시 제한 사항  
 제한 사항은 다음과 같습니다.  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]는 **id ()** 의 두 인수 버전을 지원 하지 않습니다.  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]**id ()** 의 인수 형식이 XS: IDREF *의 하위 형식 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시퀀스 함수](https://msdn.microsoft.com/library/672d2795-53ab-49c2-bf24-bc81a47ecd3f)  
  
  
