---
title: scan for startup procs 서버 구성 옵션 구성 | Microsoft Docs
description: "\"scan for startup procs\" 옵션에 대해 알아봅니다. 이 옵션을 사용하여 SQL Server가 시작 시 저장된 프로시저를 모두 검사하고 자동으로 실행할지를 지정하는 방법을 확인합니다."
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 0547d5a800533a2414a8dbf666c85a8e9f4bc4c1
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85785644"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a>scan for startup procs 서버 구성 옵션 구성
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  이 항목에서는 **또는** 을 사용하여 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 에서 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 시작 프로시저 검색 [!INCLUDE[tsql](../../includes/tsql-md.md)]서버 구성 옵션을 구성하는 방법에 대해 설명합니다. **시작 프로시저 검색** 옵션을 사용하여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시작 시 저장 프로시저의 자동 실행을 검색할 수 있습니다. 이 옵션을 1로 설정하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 는 서버에 정의된 자동 실행 저장 프로시저를 모두 검색하여 실행합니다. **시작 프로시저 검색** 의 기본값은 0(검색 안 함)입니다.  
  
 **항목 내용**  
  
-   **시작하기 전 주의 사항:**  
  
     [권장 사항](#Recommendations)  
  
     [보안](#Security)  
  
-   **시작 프로시저 검색 옵션을 구성하려면:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **후속 작업:**  [시작 프로시저 검색 옵션을 구성한 후](#FollowUp)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> 시작하기 전에  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> 권장 사항  
  
-   이 옵션은 고급 옵션으로, 숙련된 데이터베이스 관리자나 공인된 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 전문가만이 변경해야 합니다.  
  
-   이 옵션의 값은 **sp_configure**를 사용하여 설정할 수 있지만 자동 실행 저장 프로시저를 설정하거나 설정을 해제하는 데 사용되는 **sp_procoption**을 사용하면 자동으로 설정됩니다. **sp_procoption** 을 사용하여 첫 번째 저장 프로시저를 autoproc로 설정하면 이 옵션의 값이 자동으로 1로 설정됩니다. **sp_procoption** 을 사용하여 마지막 저장 프로시저의 autoproc 설정을 해제하면 이 옵션의 값이 자동으로 0으로 설정됩니다. **sp_procoption** 을 사용하여 autoprocs를 설정하거나 해제하고 autoprocs를 삭제하기 전에 항상 해제하면 이 옵션을 수동으로 설정할 필요가 없습니다.  
  
###  <a name="security"></a><a name="Security"></a> 보안  
  
####  <a name="permissions"></a><a name="Permissions"></a> 권한  
 매개 변수 없이 또는 첫 번째 매개 변수만 사용하여 **sp_configure** 를 실행할 수 있는 권한은 기본적으로 모든 사용자에게 부여됩니다. 구성 옵션을 변경하거나 RECONFIGURE 문을 실행하는 두 매개 변수를 사용하여 **sp_configure** 를 실행하려면 사용자에게 ALTER SETTINGS 서버 수준 권한이 있어야 합니다. **sysadmin** 및 **serveradmin** 고정 서버 역할은 ALTER SETTINGS 권한을 암시적으로 보유하고 있습니다.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> SQL Server Management Studio 사용  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a>scan for startup procs 옵션을 구성하려면  
  
1.  개체 탐색기에서 서버를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **고급** 노드를 클릭합니다.  
  
3.  **기타**아래의 드롭다운 목록 상자에서 원하는 값을 선택하여 **시작 프로시저 검색** 옵션을 True 또는 False로 변경합니다.  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Transact-SQL 사용  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a>scan for startup procs 옵션을 구성하려면  
  
1.  [!INCLUDE[ssDE](../../includes/ssde-md.md)]에 연결합니다.  
  
2.  표준 도구 모음에서 **새 쿼리**를 클릭합니다.  
  
3.  다음 예를 복사하여 쿼리 창에 붙여 넣고 **실행**을 클릭합니다. 다음 예에서는 [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) 를 사용하여 `scan for startup procs` 옵션의 값을 `1`(으)로 설정하는 방법을 보여 줍니다.  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> 후속 작업: 시작 프로시저 검색 옵션을 구성한 후  
 설정을 적용하려면 서버를 다시 시작해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [RECONFIGURE&#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [서버 구성 옵션&#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [sp_procoption&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-procoption-transact-sql.md)  
  
  
