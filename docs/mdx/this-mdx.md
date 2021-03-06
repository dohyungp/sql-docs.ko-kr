---
description: This(MDX)
title: This (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: e00435741516fd1ed1942506084c26192b6d47da
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88413099"
---
# <a name="this-mdx"></a>This(MDX)


  MDX 계산 스크립트에서 할당에 사용할 수 있도록 현재 하위 큐브를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
This   
```  
  
## <a name="remarks"></a>설명  
 **이** 함수를 하위 큐브 식 대신 사용 하 여 MDX 계산 스크립트 내에서 현재 범위 내의 현재 하위 큐브를 제공할 수 있습니다. **이** 함수는 할당의 왼쪽에서 사용 해야 합니다.  
  
## <a name="examples"></a>예제  
 다음 MDX 스크립트 조각에서는 SCOPE 문에 This 키워드를 사용하여 하위 큐브에 할당하는 방법을 보여 줍니다.  
  
 `Scope`  
  
 `(`  
  
 `[Date].[Fiscal Year].&[2005],`  
  
 `[Date].[Fiscal].[Fiscal Quarter].Members,`  
  
 `[Measures].[Sales Amount Quota]`  
  
 `) ;`  
  
 `This = ParallelPeriod`  
  
 `(`  
  
 `[Date].[Fiscal].[Fiscal Year], 1,`  
  
 `[Date].[Fiscal].CurrentMember`  
  
 `) * 1.35 ;`  
  
 `/*-- Allocate equally to months in FY 2002 -----------------------------*/`  
  
 `Scope`  
  
 `(`  
  
 `[Date].[Fiscal Year].&[2002],`  
  
 `[Date].[Fiscal].[Month].Members`  
  
 `) ;`  
  
 `This = [Date].[Fiscal].CurrentMember.Parent / 3 ;`  
  
 `End Scope ;`  
  
 `End Scope;`  
  
## <a name="see-also"></a>참고 항목  
 [Mdx 함수 참조 &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)   
 [계산](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/calculations)  
  
  
