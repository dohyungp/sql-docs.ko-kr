---
description: sp_help_spatial_geometry_histogram(Transact-SQL)
title: sp_help_spatial_geometry_histogram (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_help_spatial_geometry_histogram
- sp_help_spatial_geometry_histogram_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_spatial_geometry_histogram
ms.assetid: 036aaf61-df3e-40f7-aa4e-62983c5a37bd
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b74fa91b13b3b7f432a4b647f063a91a76e8c56a
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89535248"
---
# <a name="sp_help_spatial_geometry_histogram-transact-sql"></a>sp_help_spatial_geometry_histogram(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  공간 인덱스의 경계 상자 및 표 매개 변수의 키 지정을 용이하게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_help_spatial_geometry_histogram [ @tabname =] 'tabname'   
     [ , [ @colname = ] 'columnname' ]   
     [ , [ @resolution = ] 'resolution' ]  
     [ , [ @xmin = ] 'minx' ]   
     [ , [ @ymin = ] 'miny' ]   
     [ ,.[ @xmax = ] 'maxx' ]  
     [ , [ @ymax = ] 'maxy' ]  
     [ , [ @sample = ] 'sample' ]  
```  
  
## <a name="arguments"></a>인수  
`[ @tabname = ] 'tabname'` 공간 인덱스가 지정 된 테이블의 정규화 된 이름 또는 정규화 되지 않은 이름입니다.  
  
 따옴표는 정규화된 테이블이 지정된 경우에만 필요합니다. 데이터베이스 이름을 포함한 정규화된 이름인 경우 반드시 현재 데이터베이스의 이름을 사용해야 합니다. *tabname* 은 **sysname**이며 기본값은 없습니다.  
  
`[ @colname = ] 'colname'` 지정 된 공간 열의 이름입니다. *colname* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @resolution = ] 'resolution'` 경계 상자를 확인 하는 것입니다. 유효한 값은 10부터 5000까지입니다. *resolution* 은 **tinyint**이며 기본값은 없습니다.  
  
`[ @xmin = ] 'xmin'` 은 X 최소 경계 상자 속성입니다. *xmin* 은 **float**이며 기본값은 없습니다.  
  
`[ @ymin = ] 'ymin'` 는 Y 최소 경계 상자 속성입니다. *ymin* 은 **float**이며 기본값은 없습니다.  
  
`[ @xmax = ] 'xmax'` X 최대 경계 상자 속성입니다. *xmax* 는 **float**이며 기본값은 없습니다.  
  
`[ @ymax = ] 'ymax'` 는 Y 최대 경계 상자 속성입니다. *ymax* 는 **float**이며 기본값은 없습니다.  
  
`[ @sample = ] 'sample'` 사용 되는 테이블의 백분율입니다. 유효한 값은 0에서 100 까지입니다. *샘플이* **float**입니다. 기본값은 100입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 테이블 값이 반환됩니다. 다음 표에서는 테이블의 열 내용에 대해 설명합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**cellid**|**int**|각 셀의 고유한 ID를 나타내며 1부터 셉니다.|  
|**셀씩**|**geometry**|각 셀을 나타내는 사각의 다각형입니다. 셀 셰이프는 공간 인덱싱에 사용된 셀 셰이프와 동일합니다.|  
|**row_count**|**bigint**|셀에 접해 있거나 셀을 포함하는 공간 개체 수를 나타냅니다.|  
  
## <a name="permissions"></a>사용 권한  
 사용자는 **public** 역할의 멤버 여야 합니다. 서버 및 개체에 대한 READ ACCESS 권한이 필요합니다.  
  
## <a name="remarks"></a>설명  
 SSMS 공간 탭은 결과를 그래픽으로 나타냅니다. 공간 창에서 결과를 쿼리하여 결과 항목의 대략적인 개수를 가져올 수 있습니다. 테이블의 개체가 셀 한 개를 넘어갈 수 있으므로 셀 합계는 실제 개체의 개수보다 클 수 있습니다.  
  
 경계 상자를 벗어나거나 경계 상자 테두리에 접해 있는 개체의 수가 포함된 결과 집합에 행이 추가로 삽입될 수 있습니다. 이 행의 **cellid** 은 0이 고이 행의 **셀** 에는 경계 상자를 나타내는 **LineString** 이 포함 됩니다. 이 행은 경계 상자 밖의 전체 공간을 나타냅니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 예제 테이블을 만든 다음 테이블에 대해 **sp_help_spatial_geometry_histogram** 를 호출 합니다.  
  
 `USE AdventureWorksDW2012`  
  
 `GO`  
  
 `-- Set database compatibility for circular arc segments`  
  
 `ALTER DATABASE AdventureWorksDW2012`  
  
 `SET COMPATIBILITY_LEVEL = 110;`  
  
 `GO`  
  
 `-- Create table to execute sp_help_spatial_geometry_histogram on`  
  
 `CREATE TABLE TownSites`  
  
 `(`  
  
 `Location geometry NULL,`  
  
 `SiteName nvarchar(50) NULL`  
  
 `)`  
  
 `GO`  
  
 `-- Insert site data into table`  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('POINT(0 0)');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Booth Map';`  
  
 `SET @g = geometry::Parse('POLYGON((1 1, 1 2, 2 2, 2 1, 1 1))');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Town Hall';`  
  
 `SET @g = geometry::Parse('CURVEPOLYGON(COMPOUNDCURVE(CIRCULARSTRING(-1 0, 0 -1, 1 0),(1 0, 1 2, -1 0)))');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Main Park';`  
  
 `SET @g = geometry::Parse('CIRCULARSTRING(1 5, 2 2, 5 1)');`  
  
 `INSERT INTO TownSites(Location, SiteName)`  
  
 `SELECT @g, N'Main Road';`  
  
 `-- Call proc to see data within bounding box`  
  
 `EXEC sp_help_spatial_geometry_histogram @tabname = TownSites, @colname = Location, @resolution = 64, @xmin = -2, @ymin = -2, @xmax = 3, @ymax = 3, @sample = 100;`  
  
 `GO`  
  
 `DROP TABLE TownSites;`  
  
 `GO`  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;공간 인덱스 저장 프로시저 &#40;](https://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)  
  
  
