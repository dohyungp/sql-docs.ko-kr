---
description: SQLBulkOperations로 행 페치
title: SQLBulkOperations를 사용 하 여 행 페치 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data updates [ODBC], bookmarks
- SQLBulkOperations function [ODBC], fetching rows
- data updates [ODBC], SQLBulkOperations
- bookmarks [ODBC]
- updating data [ODBC], bookmarks
- updating data [ODBC], SQLBulkOperations
ms.assetid: 0efee2d6-ce94-411e-9976-97ba28b8da37
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e4c3cb6a38e3ef9c42f4e853b8c406579b5c0236
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88499873"
---
# <a name="fetching-rows-with-sqlbulkoperations"></a>SQLBulkOperations로 행 페치
SQLBulkOperations에 대 한 호출로 책갈피를 사용 하 여 행 집합으로 데이터를 **Refetched** 수 있습니다. 인출할 행은 바인딩된 책갈피 열의 책갈피를 통해 식별 됩니다. SQL_COLUMN_IGNORE 값이 있는 열은 인출 되지 않습니다.  
  
 **SQLBulkOperations**를 사용 하 여 대량 페치를 수행 하기 위해 응용 프로그램은 다음을 수행 합니다.  
  
1.  업데이트할 모든 행의 책갈피를 검색 하 고 캐시 합니다. 책갈피와 열 단위 바인딩이 모두 사용 되는 경우 책갈피는 배열에 저장 됩니다. 책갈피와 행 단위 바인딩이 모두 사용 되는 경우 책갈피는 행 구조의 배열에 저장 됩니다.  
  
2.  SQL_ATTR_ROW_ARRAY_SIZE statement 특성을 인출 하 여 책갈피 값을 포함 하는 버퍼 또는 책갈피의 배열을 열 0에 바인딩하는 행 수로 설정 합니다.  
  
3.  필요에 따라 각 열의 길이/표시기 버퍼에 값을 설정 합니다. 이는 문자열 버퍼에 바인딩된 열에 대 한 데이터 또는 SQL_NTS 바이트 길이, 이진 버퍼에 바인딩된 열의 데이터 바이트 길이, NULL로 설정 될 열에 대 한 SQL_NULL_DATA입니다. 응용 프로그램은 기본값 (있는 경우) 또는 NULL (있는 경우 SQL_COLUMN_IGNORE)로 설정 될 열에 대 한 길이/표시기 버퍼의 값을 설정 합니다 (있는 경우).  
  
4.  SQL_FETCH_BY_BOOKMARK로 설정 된 *Operation* 인수를 사용 하 여 **SQLBulkOperations** 를 호출 합니다.  
  
 특정 열에 대해 작업을 수행 하는 것을 방지 하기 위해 응용 프로그램에서 row 작업 배열을 사용할 필요는 없습니다. 응용 프로그램은 해당 행의 책갈피를 바인딩된 책갈피 배열에 복사 하 여 페치할 행을 선택 합니다.
