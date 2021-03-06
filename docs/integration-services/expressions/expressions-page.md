---
description: 식 페이지
title: 식 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23afd7d406cc201615b696961f7c3fe1072f9ba9
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88425515"
---
# <a name="expressions-page"></a>식 페이지

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  **식** 페이지를 사용하여 속성 식을 편집하고 **속성 식 편집기** 및 **식 작성기** 대화 상자에 액세스할 수 있습니다.  
  
 속성 식은 패키지 실행 시 속성 값을 업데이트합니다. 패키지, 태스크, 컨테이너, 연결 관리자 및 일부 데이터 흐름 구성 요소의 속성에 속성 식을 사용할 수 있습니다. 식이 평가되고 그 결과가 패키지 및 패키지 개체를 구성할 때 설정한 속성 값 대신 사용됩니다. 식에는 식 언어가 제공하는 함수 및 연산자와 변수가 포함될 수 있습니다. 예를 들어 "Weather forecast for " 문자열이 포함된 변수 값과 GETDATE() 함수의 반환 결과를 연결하여 "Weather forecast for 4/5/2006" 문자열을 만들면 메일 보내기 태스크의 제목 줄을 생성할 수 있습니다.  
  
 식을 작성하고 속성 식을 사용하는 방법은 [Integration Services&#40;SSIS&#41; 식](../../integration-services/expressions/integration-services-ssis-expressions.md) 및 [패키지에서 속성 식 사용](../../integration-services/expressions/use-property-expressions-in-packages.md)을 참조하세요.  
  
## <a name="options"></a>옵션  
 **식(...)**  
 **속성 식 편집기** 대화 상자를 열려면 줄임표를 클릭합니다. 자세한 내용은 [Property Expressions Editor](../../integration-services/expressions/property-expressions-editor.md)를 참조하세요.  
  
 **\<property name>**  
 **식 작성기** 대화 상자를 열려면 줄임표를 클릭합니다. 자세한 내용은 [Expression Builder](../../integration-services/expressions/expression-builder.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Integration Services&#40;SSIS&#41; 변수](../../integration-services/integration-services-ssis-variables.md)   
 [시스템 변수](../../integration-services/system-variables.md)   
 [Integration Services&#40;SSIS&#41; 식](../../integration-services/expressions/integration-services-ssis-expressions.md)  
  
  
