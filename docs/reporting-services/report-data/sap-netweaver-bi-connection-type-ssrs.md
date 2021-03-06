---
title: SAP NetWeaver BI 연결 형식 | Microsoft Docs
description: SAP NetWeaver BI 연결 형식에 대한 이 문서의 정보를 사용하여 데이터 원본을 작성하는 방법을 알아봅니다.
ms.date: 03/17/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-data
ms.topic: conceptual
ms.assetid: f985856b-31d5-4e56-844b-8a8ee38da67e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 028ee19646716666314b0242e0ebe0e3c6551e95
ms.sourcegitcommit: 9470c4d1fc8d2d9d08525c4f811282999d765e6e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86457753"
---
# <a name="sap-netweaver-bi-connection-type-ssrs"></a>SAP NetWeaver BI 연결 형식(SSRS)
  보고서에 SAP NetWeaver® Business Intelligence 외부 데이터 원본의 데이터를 포함하려면 [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)]유형의 보고서 데이터 원본에 기초하는 데이터 세트가 있어야 합니다. 이 기본 제공 데이터 원본 유형은 [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Data Provider 1.0 for [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)]의 확장 프로그램을 기반으로 합니다.  
  
 이 데이터 확장 프로그램을 사용하면 [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] 외부 데이터 원본에 정의된 InfoCube, MultiProvider(가상 InfoCube) 및 웹 사용이 가능한 쿼리에서 다차원 데이터를 검색할 수 있습니다.  
  
 이 항목의 정보를 사용하여 데이터 원본을 작성할 수 있습니다. 단계별 지침은 [데이터 연결 추가 및 확인&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md)을 참조하세요.  
  
##  <a name="connection-string"></a><a name="Connection"></a> 연결 문자열  
 데이터 원본 연결에 사용할 자격 증명 및 연결 정보는 데이터베이스 관리자에게 문의하세요. 다음 연결 문자열 예에서는 SOAP를 사용하는 인터넷을 통해 포트 8000과 XMLA(XML for Analysis Services)를 사용하는 서버의 [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] 데이터 원본을 지정합니다.  
  
```  
DataSource=https://mySAPNetWeaverBIServer:8000/sap/bw/xml/soap/xmla  
```  
  
 연결 문자열 예제는 [데이터 연결 문자열 만들기 - 보고서 작성기 및 SSRS](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)를 참조하세요.  
  
  
##  <a name="credentials"></a><a name="Credentials"></a> 자격 증명  
 쿼리를 실행하거나 보고서를 로컬로 미리 보거나 보고서 서버의 보고서를 미리 보려면 자격 증명이 필요합니다.  
  
 보고서를 게시한 후 보고서를 보고서 서버에서 실행할 때 데이터를 검색할 수 있는 권한이 유효하도록 데이터 원본에 대한 자격 증명을 변경해야 할 수도 있습니다.  
  
 자세한 내용은 [보고서 데이터 원본에 대한 자격 증명 및 연결 정보 지정](specify-credential-and-connection-information-for-report-data-sources.md)을 참조하세요.  
  
  
##  <a name="queries"></a><a name="Query"></a> 쿼리  
 디자인 모드나 쿼리 모드의 그래픽 쿼리 디자이너에서 데이터 원본의 기본 데이터 구조를 찾아서 MDX(Multidimensional Expression) 쿼리를 작성할 수 있습니다. 또한 디자인 타임에 쿼리 디자이너에서 대화형으로 쿼리를 실행하여 결과를 볼 수 있습니다. 작성한 쿼리는 데이터 세트의 필드를 정의합니다. 실제 데이터는 런타임에 데이터 원본에서 반환됩니다. 그래픽 쿼리 디자이너를 사용하여 수행할 수 있는 동작은 다음과 같습니다.  
  
-   디자인 모드에서 데이터 원본의 차원, 멤버, 멤버 속성 및 주요 숫자 값을 데이터 창으로 끌어 MDX(Multidimensional Expression) 쿼리를 작성합니다. 추가 데이터 세트 필드를 정의하려면 계산 멤버 창의 계산 멤버를 데이터 창으로 끌어 옵니다.  
  
-   쿼리 모드에서 차원, 멤버, 멤버 속성 및 주요 숫자 값을 쿼리 창으로 끌거나 MDX 텍스트를 쿼리 창에 직접 입력합니다. 추가 데이터 세트 필드를 정의하려면 계산 멤버 창의 계산 멤버를 데이터 창으로 끌어 옵니다.  
  
 쿼리를 작성하면 쿼리 디자이너가 기본 속성을 MDX 쿼리에 자동으로 추가합니다. 기본 속성 이외의 속성을 포함하려면 MDX 쿼리를 직접 수정해야 합니다.  
  
 이 쿼리 디자이너 사용에 대한 자세한 내용은 [SAP NetWeaver BI 쿼리 디자이너 사용자 인터페이스&#40;보고서 작성기&#41;](https://msdn.microsoft.com/library/8edda06d-1608-498b-bd50-10905e54f6ce)를 참조하세요.  
  
  
##  <a name="extended-field-properties"></a><a name="Extended"></a> 확장 필드 속성  
 [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] 데이터 원본은 확장 필드 속성을 지원합니다. 확장 필드 속성은 **Value** 및 **IsMissing** 외에 데이터 처리 확장 프로그램에서 데이터 세트 필드에 대해 정의한 속성입니다. 확장 속성에는 미리 정의된 속성과 사용자 지정 속성이 포함됩니다. 미리 정의된 속성은 여러 데이터 원본에 공통된 속성이고 사용자 지정 속성은 각 데이터 원본에 고유한 속성입니다.  
  
### <a name="working-with-field-properties"></a>필드 속성 사용  
 확장 필드 속성은 보고서 데이터 창에 보고서 레이아웃으로 끌 수 있는 항목으로 나타나지 않습니다. 대신 속성의 부모 필드를 보고서로 끈 다음 기본 속성 **Value** 를 사용하려는 속성으로 변경합니다. 예를 들어 MDX 쿼리 디자이너에서 메타데이터 창의 수준을 쿼리 창으로 끌어 **Calendar Year/Month Level 01** 이라는 필드를 만든 경우에는 식에서 다음 구문을 사용하여 사용자 지정 확장 속성 **Long Name** 을 참조합니다.  
  
 `=Fields!Calendar_Year_Month_Level_01("Long Name")`  
  
 메타데이터 창에서 필드를 가리키면 확장 필드 속성 이름이 도구 설명에 표시됩니다. 기본 데이터를 탐색할 때 사용할 수 있는 쿼리 디자이너에 대한 자세한 내용은 [SAP NetWeaver BI Query Designer User Interface](../../reporting-services/report-data/sap-netweaver-bi-query-designer-user-interface.md)를 참조하세요.  
  
> [!NOTE]  
>  보고서가 실행되어 해당 데이터 세트에 대한 데이터를 검색할 때 데이터 원본에서 확장 필드 속성에 대한 값을 제공하는 경우에만 이러한 속성에 대한 값이 있습니다. 그러면 아래 설명하는 구문을 사용하여 식에서 해당 **Field** 속성 값을 참조할 수 있습니다. 그러나 이러한 필드는 해당 데이터 공급자와만 관련이 있고 보고서 정의 언어에는 포함되지 않으므로 이러한 값을 변경해도 보고서 정의에는 변경된 값이 저장되지 않습니다.  
  
 식에서 미리 정의된 확장 속성을 참조하려면 다음 구문 중 하나를 사용합니다.  
  
-   *Fields!FieldName.PropertyName*  
  
-   *Fields!FieldName("PropertyName")*  
  
 식에서 사용자 지정 확장 속성을 참조하려면 다음 구문을 사용합니다.  
  
-   *Fields!FieldName("PropertyName")*  
  
  
### <a name="predefined-field-properties"></a>미리 정의된 필드 속성  
 다음 표에서는 [!INCLUDE[SAP_DPE_BW_1](../../includes/sap-dpe-bw-1-md.md)] 데이터 원본에 사용할 수 있는 미리 정의된 필드 속성 목록을 보여 줍니다.  
  
|**Property**|**Type**|**설명 또는 필요한 값**|  
|------------------|--------------|---------------------------------------|  
|**값**|**Object**|필드의 데이터 값을 지정합니다.|  
|**IsMissing**|**Boolean**|필드가 결과 데이터 집합에 있는지 여부를 나타냅니다.|  
|**FormattedValue**|**String**|주요 숫자 값의 형식화된 값을 반환합니다.|  
|**BackgroundColor**|**String**|필드에 대해 데이터베이스에 정의된 배경색을 반환합니다.|  
|**Color**|**String**|항목에 대해 데이터베이스에 정의된 전경색을 반환합니다.|  
|**Key**|**Object**|수준의 키를 반환합니다.|  
|**LevelNumber**|**정수**|부모-자식 계층에 대해 수준 또는 차원 번호를 반환합니다.|  
|**ParentUniqueName**|**String**|부모-자식 계층에 대해 부모 수준의 정규화된 이름을 반환합니다.|  
|**UniqueName**|**String**|수준의 정규화된 이름을 반환합니다. 예를 들어 직원의 **UniqueName** 값은 *[0D_Company].[10D_Department].[11]* 일 수 있습니다.|  
  
 식에서 필드 및 필드 속성을 사용하는 방법은 [식의 기본 제공 컬렉션&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/built-in-collections-in-expressions-report-builder.md)을 참조하세요.  
  
  
##  <a name="remarks"></a><a name="Remarks"></a> 주의  
 이 데이터 공급자는 일부 보고서 배달 모드만 지원합니다. 이 데이터 처리 확장 프로그램에서는 데이터 기반 구독을 통한 보고서 배달이 지원되지 않습니다. 자세한 내용은 [구독자 데이터에 외부 데이터 원본 사용&#40;데이터 기반 구독&#41;](../../reporting-services/subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)을 참조하세요.  
  
 자세한 내용은 [SAP NetWeaver Business Intelligence와 함께 SQL Server 2008 Reporting Services 사용](https://go.microsoft.com/fwlink/?LinkId=167352)을 참조하세요.  
  
  
##  <a name="how-to-topics"></a><a name="HowTo"></a> 방법 도움말 항목  
 이 섹션에서는 데이터 연결, 데이터 원본 및 데이터 세트를 사용하는 방법을 단계별로 설명합니다.  
  
 [데이터 연결 추가 및 확인&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [공유 데이터 세트 또는 포함된 데이터 세트 만들기&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [데이터 세트에 필터 추가&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
  
##  <a name="related-sections"></a><a name="Related"></a> 관련 단원  
 설명서의 다음 섹션에서는 보고서 데이터에 대한 깊이 있는 개념 정보를 제공하며, 데이터와 관련된 보고서 부분을 정의, 사용자 지정 및 사용하는 방법을 절차적인 측면에서 소개합니다.  
  
 [보고서 데이터 세트&#40;SSRS&#41;](../../reporting-services/report-data/report-datasets-ssrs.md)  
 보고서의 데이터 액세스에 대한 개요를 제공합니다.  
  
 [데이터 연결 문자열 만들기 - 보고서 작성기 및 SSRS](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)  
 데이터 연결 및 데이터 원본에 대한 정보를 제공합니다.  
  
 [보고서 포함된 데이터 세트 및 공유 데이터 세트&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 포함된 데이터 세트 및 공유 데이터 세트에 대한 정보를 제공합니다.  
  
 [데이터 세트 필드 컬렉션&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
 쿼리에 의해 생성되는 데이터 세트 필드 컬렉션에 대한 정보를 제공합니다.  
  
 [Reporting Services&#40;SSRS&#41;에서 지원하는 데이터 원본](../../reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs.md)  
 각 데이터 확장 프로그램의 플랫폼 및 버전 지원에 대한 자세한 정보를 제공합니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [보고서 매개 변수&#40;보고서 작성기 및 보고서 디자이너&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [데이터 필터링, 그룹화 및 정렬&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)   
 [식&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md)  
  
  
