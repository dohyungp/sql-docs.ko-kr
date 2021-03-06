---
title: ISSCommandWithParameters::SetParameterProperties(OLE DB) | Microsoft Docs
description: OLE DB Driver for SQL Server에서 ISSCommandWithParameters::SetParameterProperties 메서드가 매개 변수 속성을 설정하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
apiname:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
apitype: COM
helpviewer_keywords:
- SetParameterProperties method
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 6340c4f52106b15adb2fec651a3cca213dad5d19
ms.sourcegitcommit: c95f3ef5734dec753de09e07752a5d15884125e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88862167"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a>ISSCommandWithParameters::SetParameterProperties(OLE DB)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  매개 변수별 서수로 매개 변수 속성을 설정하거나, SSPARAMPROPS 구조의 배열을 지정하여 대량 매개 변수 속성을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
HRESULT SetParameterProperties(  
      DB_UPARAMS cParams,   
      SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a>인수  
 *cParams*[in]  
 *rgParamProperties* 배열의 SSPARAMPROPS 구조 수입니다. 이 개수가 0이면 **ISSCommandWithParameters::SetParameterProperties**가 명령의 매개 변수에 대해 지정되었을 수 있는 모든 속성을 삭제합니다.  
  
 *rgParamProperties*[in]  
 설정할 SSPARAMPROPS 구조의 배열입니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **ISSCommandWithParameters::SetParameterProperties** 메서드에서 핵심 OLE DB **ICommandProperties::SetProperties** 메서드와 동일한 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용한 매개 변수 속성 설정은 매개 변수별 서수로 허용되거나, 속성 배열에서 SSPARAMPROPS가 작성된 후 단일 **ISSCommandWithParameters::SetParameterProperties** 호출을 사용하여 허용됩니다.  
  
 **ISSCommandWithParameters::SetParameterProperties** 메서드를 호출하기 전에 **SetParameterInfo** 메서드를 호출해야 합니다. `SetParameterProperties(0, NULL)`를 호출하면 지정한 모든 매개 변수 속성이 지워지지만 `SetParameterInfo(0,NULL,NULL)`를 호출하면 매개 변수와 관련이 있을 수 있는 모든 속성을 비롯하여 모든 매개 변수 정보가 지워집니다.  
  
 DBTYPE_XML 또는 DBTYPE_UDT 유형이 아닌 매개 변수의 속성을 지정하기 위해 **ISSCommandWithParameters::SetParameterProperties**를 호출하면 DB_E_ERRORSOCCURRED 또는 DB_S_ERRORSOCCURRED가 반환되고, 해당 매개 변수의 SSPARAMPROPS에 포함된 모든 DBPROP의 *dwStatus* 필드에 DBPROPSTATUS_NOTSET가 표시됩니다. DB_E_ERRORSOCCURRED 또는 DB_S_ERRORSOCCURRED가 참조하는 매개 변수를 검색하기 위해 SSPARAMPROPS에 포함된 각 DBPROPSET의 DBPROP 배열을 이동해야 합니다.  
  
 **SetParameterInfo**를 사용하여 매개 변수 정보가 아직 설정되지 않은 매개 변수의 속성을 지정하기 위해 **ISSCommandWithParameters::SetParameterProperties**를 호출하면 공급자가 다음 오류 메시지와 함께 E_UNEXPECTED를 반환합니다.  
  
 먼저 SetParameterInfo 메서드를 호출해야만 지정한 매개 변수에 대해 SetParameterProperties 메서드를 호출할 수 있습니다. 매개 변수 속성을 설정하기 전에 매개 변수 정보를 설정해야 합니다.  
  
 **ISSCommandWithParameters::SetParameterProperties**에 대한 호출에 포함된 일부 매개 변수는 매개 변수 정보가 설정되어 있고 다른 일부 매개 변수는 매개 변수 정보가 설정되어 있지 않은 경우 SSPARAMPROPS 속성 집합의 DBPROPSET에 있는 dwStatus 속성이 DBSTATUS_NOTSET로 반환됩니다.  
  
 SSPARAMPROPS 구조는 다음과 같이 정의됩니다.  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]부터 데이터베이스 엔진의 기능이 향상되어 ISSCommandWithParameters::SetParameterProperties를 통해 예상 결과에 대한 보다 정확한 설명을 얻을 수 있습니다. 보다 정확한 결과는 이전 버전의 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에서 ISSCommandWithParameters::SetParameterProperties가 반환한 값과 다를 수 있습니다. 자세한 내용은 [메타데이터 검색](../../oledb/features/metadata-discovery.md)을 참조하세요.  
  
|멤버|Description|  
|------------|-----------------|  
|*iOrdinal*|전달된 매개 변수의 서수입니다.|  
|*cPropertySets*|*rgPropertySets*에 있는 DBPROPSET 구조의 개수입니다.|  
|*rgPropertySets*|DBPROPSET 구조의 배열을 반환할 메모리에 대한 포인터입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ISSCommandWithParameters&#40;OLE DB&#41;](../../oledb/ole-db-interfaces/isscommandwithparameters-ole-db.md)  
  
  
