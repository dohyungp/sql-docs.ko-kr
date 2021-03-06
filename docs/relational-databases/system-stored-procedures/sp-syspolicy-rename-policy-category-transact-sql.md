---
description: sp_syspolicy_rename_policy_category(Transact-SQL)
title: sp_syspolicy_rename_policy_category (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_syspolicy_rename_policy_category_TSQL
- sp_syspolicy_rename_policy_category
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syspolicy_rename_policy_category
ms.assetid: 8a9c4a3a-91e8-435e-b721-e0293c92be3e
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: b350a19bb19defbd1510f7ce13a82729c2cbe779
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88446749"
---
# <a name="sp_syspolicy_rename_policy_category-transact-sql"></a>sp_syspolicy_rename_policy_category(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  정책 기반 관리에 있는 기존 정책 범주의 이름을 바꿉니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
sp_syspolicy_rename_policy_category { [ @name = ] 'name' | [ @policy_category_id = ] policy_category_id }  
    , [ @new_name = ] 'new_name'  
```  
  
## <a name="arguments"></a>인수  
`[ @name = ] 'name'` 이름을 바꿀 정책 범주의 이름입니다. *name* 은 **SYSNAME**이며 *policy_category_id* NULL 인 경우에는 반드시 지정 해야 합니다.  
  
`[ @policy_category_id = ] policy_category_id` 이름을 바꿀 정책 범주의 식별자입니다. *policy_category_id* 은 **INT**이며 *이름이* NULL 인 경우에는 반드시 지정 해야 합니다.  
  
`[ @new_name = ] 'new_name'` 정책 범주의 새 이름입니다. *new_name* 는 **sysname**이며 필수입니다. NULL 또는 빈 문자열일 수 없습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="remarks"></a>설명  
 sp_syspolicy_rename_policy_category는 msdb 시스템 데이터베이스의 컨텍스트에서 실행해야 합니다.  
  
 *이름* 또는 *policy_category_id*에 대 한 값을 지정 해야 합니다. 둘 다 NULL일 수는 없습니다. 이러한 값을 가져오려면 msdb.dbo.syspolicy_policy_categories 시스템 뷰를 쿼리합니다.  
  
## <a name="permissions"></a>사용 권한  
 PolicyAdministratorRole 고정 데이터베이스 역할의 멤버 자격이 필요합니다.  
  
> [!IMPORTANT]  
>  자격 증명의 승격 가능: Policy관리자 역할 역할의 사용자는 서버 트리거를 만들고 인스턴스 작업에 영향을 줄 수 있는 정책 실행을 예약할 수 있습니다 [!INCLUDE[ssDE](../../includes/ssde-md.md)] . 예를 들어 PolicyAdministratorRole 역할의 사용자는 대부분의 개체가 [!INCLUDE[ssDE](../../includes/ssde-md.md)]에서 생성되지 않도록 할 수 있는 정책을 만들 수 있습니다. 이렇게 자격 증명을 승격할 수 있기 때문에 PolicyAdministratorRole 역할은 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 구성을 제어할 수 있도록 신뢰할 수 있는 사용자에게만 부여되어야 합니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 'Test Category 1'이라는 정책 범주의 이름을 'Test Category 2'로 바꿉니다.  
  
```  
EXEC msdb.dbo.sp_syspolicy_rename_policy_category @name = N'Test Category 1'  
, @new_name = N'Test Category 2';  
  
GO  
```  
  
## <a name="see-also"></a>관련 항목  
 [Transact-sql&#41;&#40;정책 기반 관리 저장 프로시저 ](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;sp_syspolicy_add_policy_category &#40;](../../relational-databases/system-stored-procedures/sp-syspolicy-add-policy-category-transact-sql.md)   
 [Transact-sql&#41;sp_syspolicy_delete_policy_category &#40;](../../relational-databases/system-stored-procedures/sp-syspolicy-delete-policy-category-transact-sql.md)   
 [Transact-sql&#41;sp_syspolicy_update_policy_category &#40;](../../relational-databases/system-stored-procedures/sp-syspolicy-update-policy-category-transact-sql.md)  
  
  
