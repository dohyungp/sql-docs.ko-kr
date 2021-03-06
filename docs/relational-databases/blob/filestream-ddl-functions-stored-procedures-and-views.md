---
title: FILESTREAM, 함수, 저장 프로시저, 뷰 | Microsoft Docs
description: FILESTREAM은 특정 Transact-SQL 문, API, 함수, 저장 프로시저 및 뷰와 함께 작동합니다. FILESTREAM을 지원하는 문과 개체에 대해 알아봅니다.
ms.custom: seo-lt-2019
ms.date: 12/13/2019
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 9ecb49ee-f64e-4d30-a803-e4064a21950a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe2ed55cd68ee6852ab071a7ff8ca428150737d9
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85642684"
---
# <a name="filestream-functions-stored-procedures-and-views"></a>FILESTREAM, 함수, 저장 프로시저, 뷰
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  FILESTREAM을 지원하는 Transact-SQL 문 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스 개체를 나열합니다.  
  
 FileTable 기능을 지원하는 데이터베이스 개체 목록은 [FileTable DDL, Functions, Stored Procedures, and Views](../../relational-databases/blob/filetable-ddl-functions-stored-procedures-and-views.md)를 참조하세요.  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> Transact-SQL DDL(데이터 정의 언어) 문  
  
-   [CREATE DATABASE&#40;SQL Server Transact-SQL&#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md)  
  
-   [ALTER DATABASE&#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)  
  
-   [CREATE TABLE&#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)  
  
-   [ALTER TABLE&#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)  
  
-   [CREATE INDEX&#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md)  
  
-   [DROP INDEX&#40;Transact-SQL&#41;](../../t-sql/statements/drop-index-transact-sql.md)
  
##  <a name="system-functions"></a><a name="func"></a> 시스템 함수  
  
-   [GET_FILESTREAM_TRANSACTION_CONTEXT&#40;Transact-SQL&#41;](../../t-sql/functions/get-filestream-transaction-context-transact-sql.md)  
  
-   [PathName&#40;Transact-SQL&#41;](../../relational-databases/system-functions/pathname-transact-sql.md)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> 시스템 저장 프로시저  
  
-   [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
-   [sp_filestream_force_garbage_collection&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/filestream-and-filetable-sp-filestream-force-garbage-collection.md)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> 시스템 뷰 - 카탈로그 뷰  
  
-   [sys.database_filestream_options&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql.md)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> 시스템 뷰 - 동적 관리 뷰  
  
-   [sys.dm_filestream_file_io_handles&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql.md)  
  
-   [sys.dm_filestream_file_io_requests&#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql.md)  
  
##  <a name="programming-apis"></a><a name="api"></a> 프로그래밍 API  
  
-   [OpenSqlFilestream을 사용하여 FILESTREAM 데이터 액세스](../../relational-databases/blob/access-filestream-data-with-opensqlfilestream.md)  
  
-   [관리되는 API - SqlFileStream 클래스](https://go.microsoft.com/fwlink/?LinkId=220875)  
  
  
