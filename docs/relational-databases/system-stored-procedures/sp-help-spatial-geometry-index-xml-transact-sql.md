---
description: sp_help_spatial_geometry_index_xml(Transact-SQL)
title: sp_help_spatial_geometry_index_xml (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_help_spatial_geometry_index_xml_TSQL
- sp_help_spatial_geometry_index_xml
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_spatial_geometry_index_xml procedure
ms.assetid: 9668ae6d-9ed5-418e-bb9a-9e7b66f7dd16
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 7bc4e0df3bfcffa7bdfd84b681c33ed179af75b9
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89546072"
---
# <a name="sp_help_spatial_geometry_index_xml-transact-sql"></a>sp_help_spatial_geometry_index_xml(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **기 하 도형** 공간 인덱스에 대해 지정 된 속성 집합의 이름과 값을 반환 합니다. 인덱스의 핵심 속성 집합만 반환하거나 인덱스의 속성을 모두 반환하도록 선택할 수 있습니다.  
  
 결과는 선택한 속성의 이름과 값을 표시하는 XML 조각으로 반환됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_spatial_geometry_index [ @tabname =] 'tabname'   
     [ , [ @indexname = ] 'indexname' ]   
     [ , [ @verboseoutput = ]'{ 0 | 1 }]   
     [ , [ @query_sample = ] 'query_sample' ]   
     [ ,.[ @xml_output = ] 'xml_output' ]   
```  
  
## <a name="arguments"></a>인수  
 [공간 인덱스 저장 프로시저의 인수 및 속성을](../../relational-databases/system-stored-procedures/spatial-index-stored-procedures-arguments-and-properties.md)참조 하세요.  
  
## <a name="properties"></a>속성  
 [공간 인덱스 저장 프로시저의 인수 및 속성을](../../relational-databases/system-stored-procedures/spatial-index-stored-procedures-arguments-and-properties.md)참조 하세요.  
  
## <a name="permissions"></a>사용 권한  
 사용자는 **public** 역할의 멤버 여야 합니다. 서버 및 개체에 대한 READ ACCESS 권한이 필요합니다.  
  
## <a name="remarks"></a>설명  
 NULL 값이 포함된 속성은 XML 반환 집합에 포함되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `sp_help_spatial_geometry_index_xml` 를 사용 하 여 ** \@ qs**의 지정 된 쿼리 샘플에 대 한 테이블 **geometry_col** 에 정의 된 **SIndx_SpatialTable_geometry_col2** 공간 인덱스를 조사 합니다. 이 예에서는 지정된 인덱스의 핵심 속성을 선택한 속성의 이름과 값을 표시하는 XML 조각으로 반환합니다.  
  
 그러면 [XQuery](../../xquery/xquery-basics.md) 가 결과 집합에서 실행 되어 특정 속성을 반환 합니다.  
  
```  
DECLARE @qs geometry  
        ='POLYGON((-90.0 -180.0, -90.0 180.0, 90.0 180.0, 90.0 -180.0, -90.0 -180.0))';  
DECLARE @x xml;  
EXEC sp_help_spatial_geometry_index_xml 'geometry_col', 'SIndx_SpatialTable_geometry_col2', 0, @qs, @x output;  
SELECT @x.value('(/Primary_Filter_Efficiency/text())[1]', 'float');  
```  
  
 [Sp_help_spatial_geometry_index](../../relational-databases/system-stored-procedures/sp-help-spatial-geometry-index-transact-sql.md)와 마찬가지로이 저장 프로시저는 공간 인덱스의 속성에 대 한 간단한 프로그래밍 방식의 액세스를 제공 하 고 결과 집합을 XML로 보고 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="see-also"></a>참고 항목  
 [공간 인덱스 저장 프로시저의 인수 및 속성](../../relational-databases/system-stored-procedures/spatial-index-stored-procedures-arguments-and-properties.md)   
 [공간 인덱스 저장 프로시저](https://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)   
 [sp_help_spatial_geometry_index](../../relational-databases/system-stored-procedures/sp-help-spatial-geometry-index-transact-sql.md)   
 [공간 인덱스 개요](../../relational-databases/spatial/spatial-indexes-overview.md)   
 [공간 데이터&#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)   
 [XQuery 기본 사항](../../xquery/xquery-basics.md)   
 [XQuery 언어 참조](../../xquery/xquery-language-reference-sql-server.md)  
  
  
