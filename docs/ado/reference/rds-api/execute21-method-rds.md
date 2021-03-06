---
description: Execute21 메서드(RDS)
title: Execute21 메서드 (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Execute21 method [RDS]
ms.assetid: 9f131c8d-1497-416d-8209-abb481c38f7b
author: rothja
ms.author: jroth
ms.openlocfilehash: 84c8c977615fdc99da45a255e5306d4066b13406
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88982314"
---
# <a name="execute21-method-rds"></a>Execute21 메서드(RDS)
요청을 실행 하 고 ADO 2.1에 사용할 ADO 레코드 집합을 만듭니다.  
  
> [!IMPORTANT]
>  Windows 8 및 Windows Server 2012부터 RDS 서버 구성 요소는 더 이상 Windows 운영 체제에 포함 되지 않습니다 (자세한 내용은 Windows 8 및 [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) 참조). 이후 버전의 Windows에서는 RDS 클라이언트 구성 요소가 제거 됩니다. 새 개발 작업에서는 이 기능을 사용하지 않도록 하고, 현재 이 기능을 사용하는 애플리케이션은 수정하세요. RDS를 사용 하는 응용 프로그램은 [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565)로 마이그레이션해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object.Execute21(ConnectionString As String, HandlerString As String, QueryString As String, lMarshalOptions As Long, Properties, TableId, lExecuteOptions As Long, pParameters)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *ConnectionString*  
 요청을 실행 하기 위해 전송 되는 OLE DB 공급자에 연결 하는 데 사용 되는 문자열입니다. *Handlerstring*을 사용 하 여 처리기를 지정 하는 경우 연결 문자열을 편집 하거나 바꿀 수 있습니다.  
  
 *HandlerString*  
 문자열은이 실행에 사용할 처리기를 식별 합니다. 문자열에는 두 부분이 포함 됩니다. 첫 번째 부분에는 사용할 처리기의 이름 (ProgID)이 포함 되어 있습니다. 문자열의 두 번째 부분에는 처리기에 전달 될 인수가 들어 있습니다. 인수 문자열을 해석 하는 방법은 handler와 관련이 있습니다. 인수 문자열에 추가 쉼표를 포함할 수는 있지만 두 부분은 문자열에 있는 첫 번째 인스턴스의 쉼표로 구분 됩니다. 인수는 선택 사항입니다.  
  
 *문자열*  
 연결 문자열에서 식별 된 OLE DB 공급자가 지 원하는 명령 언어의 명령입니다. SQL 기반 공급자의 경우 명령 문이 포함 될 수 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 있지만 sql 이외의 공급자 (예: MSDataShape)의 경우 쿼리 문이 아닐 수 있습니다 [!INCLUDE[tsql](../../../includes/tsql-md.md)] .  
  
 또한 처리기를 사용 하는 경우 처리기를 사용 하는 것이 좋습니다. 처리기는 여기에 지정 된 값을 변경 하거나 바꿀 수 있습니다. 예를 들어 처리기는 일반적으로 *QueryString* 파일의 쿼리 문자열로 QueryString을 대체 합니다. 기본적으로 Msdfmap.ini 파일이 사용 됩니다.  
  
 *lMarshalOptions*  
 반환 되는 행 집합/레코드 집합에 대 한 마샬링 옵션을 설정 하는 데 사용 됩니다.  
  
 *TableID*  
 VT_EMPTY 또는 VT_BSTR 형식의 변형입니다. 이 값이 VT_EMPTY 형식이 면 무시 됩니다. VT_BSTR 형식이 면 여기에 지정 된 값을 사용 하 여 **adCmdTableDirect** 를 사용 하 여 레코드 집합을 만들고 *QueryString* 매개 변수는 무시 됩니다.  
  
 *lExecuteOptions*  
 실행 옵션의 비트 마스크입니다.  
  
 1 =*Readonly* **adlockreadonly**를 사용 하 여 레코드 집합을 엽니다.  
  
 2 =*Nobatch* 레코드 집합은 **adlockoptimistic**을 사용 하 여 열립니다.  
  
 4 =*Allparaminfosupplied* 호출자는 모든 매개 변수에 대 한 매개 변수 정보가 *pparameters*에 제공 되도록 보장 합니다.  
  
 8 =*GetInfo* 공급자 OLE DB에서 쿼리에 대 한 매개 변수 정보를 가져오고 *pparameters* 매개 변수에 반환 합니다. 쿼리가 실행 되지 않으며 레코드 집합이 반환 되지 않습니다.  
  
 16 = GetHiddenColumns는 **Adlockbatchoptimistic** 을 사용 하 여 레코드 집합을 열고 숨겨진 열은 레코드 집합에 포함 됩니다.  
  
 *ReadOnly*, *Nobatch* 및 *GetHiddenColumns* 는 함께 사용할 수 없는 옵션 이지만 둘 이상의 옵션을 설정 하는 것은 오류가 아닙니다. 여러 옵션을 설정 하는 경우 *GetHiddenColumns* 는 다른 모든 옵션에 우선 하 고 그 뒤에 *ReadOnly*가 적용 됩니다. 옵션이 지정 되지 않은 경우 기본적으로 **Adlockbatchoptimistic** 을 사용 하 여 레코드 집합을 열 수는 있지만 숨겨진 열은 레코드 집합에 포함 되지 않습니다.  
  
 *pParameters*  
 매개 변수 정의의 안전 배열을 포함 하는 variant입니다. *Lexecuteoptions*에 *GetInfo* 옵션이 지정 된 경우이 매개 변수는 OLE DB 공급자에서 가져온 매개 변수 정의를 반환 하는 데 사용 됩니다. 그렇지 않으면이 매개 변수는 비어 있을 수 있습니다.  
  
## <a name="remarks"></a>설명  
 *Handlerstring* 매개 변수는 null 일 수 있습니다. 이 경우에 발생 하는 작업은 RDS 서버를 구성 하는 방법에 따라 달라 집니다. "MSDFMAP. handler"의 처리기 문자열은 Microsoft에서 제공 하는 처리기 (Msdfmap.dll)를 사용 해야 함을 나타냅니다. "MASDFMAP sample.ini" 처리기 문자열은 Msdfmap.dll 처리기를 사용 해야 하며 "sample.ini" 인수를 처리기에 전달 해야 함을 나타냅니다. MSDFMAP.dll은 sample.ini를 사용 하 여 연결 및 쿼리 문자열을 확인 하는 방향으로 인수를 해석 합니다.  
  
> [!NOTE]
>  **Execute21** 메서드는 [EXECUTE 메서드 (RDS)](./execute-method-rds.md)의 버전입니다. **Execute** 메서드를 사용 하 여 ADO 2.1와 통신 해야 하는 경우 대신 **Execute21** 메서드를 호출할 수 있습니다. ADO 2.5 이상에서 **Execute** 메서드의 기능은 ado 2.1에서 동일한 메서드에 제공 되는 기능의 상위 집합입니다.  
  
## <a name="applies-to"></a>적용 대상  
 [DataFactory 개체(RDSServer)](./datafactory-object-rdsserver.md)