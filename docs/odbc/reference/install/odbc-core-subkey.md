---
description: ODBC 핵심 하위 키
title: ODBC Core 하위 키 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- subkeys [ODBC], core subkey
- registry entries for components [ODBC], core subkey
- core subkey [ODBC]
ms.assetid: 055b31fc-f96c-450b-a596-d4570079fbf2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 37948c46d6a717975902bc2109ece2aea02b0129
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88499738"
---
# <a name="odbc-core-subkey"></a>ODBC 핵심 하위 키
ODBC Core 하위 키 아래에 있는 값은 핵심 구성 요소 (드라이버 관리자, 커서 라이브러리, 설치 관리자 DLL 등)의 사용 횟수를 제공 합니다. 이 값의 형식은 다음 표에 나와 있습니다.  
  
|Name|데이터 형식|데이터|  
|----------|---------------|----------|  
|UsageCount|REG_DWORD|*count*|  
  
 예를 들어 세 가지 응용 프로그램에 대 한 설치 프로그램 및 두 개의 다른 드라이버에 대해 ODBC 핵심 구성 요소가 설치 되어 있다고 가정 합니다. ODBC Core 하위 키 아래에 있는 값은 다음과 같습니다.  
  
```  
UsageCount : REG_DWORD : 0x5  
```
