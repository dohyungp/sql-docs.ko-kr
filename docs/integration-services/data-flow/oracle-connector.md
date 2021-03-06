---
description: Microsoft Connector for Oracle
title: Microsoft Connector for Oracle | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5bb5631a398e398b45b84a0ee70b51f49c90988
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88430755"
---
# <a name="microsoft-connector-for-oracle"></a>Microsoft Connector for Oracle

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

Microsoft Connector for Oracle을 사용하면 SSIS 패키지의 Oracle 데이터 원본에서 데이터를 내보내거나 이 원본으로 데이터를 로드할 수 있습니다.

## <a name="version-support"></a>버전 지원

다음 Microsoft SQL Server 제품은 Microsoft Connector for Oracle에서 지원됩니다.

- SQL Server 2019 CU1 이상
- Visual Studio 2017용 SQL Server Data Tools(SSDT) 15.9.3 이상
- Visual Studio 2019용 Microsoft SQL Server Data Tools(SSDT)

데이터 원본의 다음 Oracle 데이터베이스 버전이 지원됩니다.

- Oracle 10.x
- Oracle 11.x
- Oracle 12c
- Oracle 18c(Windows 인증 지원 없음)
- Oracle 19c(Windows 인증 지원 없음)

Oracle 데이터베이스는 모든 운영 체제 및 플랫폼에서 지원됩니다.
> [!NOTE]
>
> SQL Server 2019의 Microsoft Connector for Oracle 데이터베이스에는 Oracle 클라이언트가 필요하지 않습니다.

## <a name="installation"></a>설치

Oracle 데이터베이스용 커넥터를 설치하려면 [최신 버전의 Microsoft Connector for Oracle](https://www.microsoft.com/download/details.aspx?id=58228)에서 설치 관리자를 다운로드하여 실행합니다. 그런 다음 설치 마법사의 지시를 따릅니다.

커넥터를 설치한 후에는 SQL Server Integration Services를 다시 시작해야 Oracle 원본 및 대상이 제대로 작동합니다.

**Microsoft Connector for Oracle** 이외에 SQL Server 2017 및 이전 버전을 대상으로 하는 SSIS 패키지를 실행하려면 아래 링크에서 해당 버전과 함께 **Oracle 클라이언트** 및 **Microsoft Connector for Oracle by Attunity**를 설치해야 합니다.

- [SQL Server 2017: Attunity의 Oracle용 Microsoft Connector 버전 5.0](https://www.microsoft.com/download/details.aspx?id=55179)
- [SQL Server 2016: Attunity의 Oracle용 Microsoft Connector 버전 4.0](https://www.microsoft.com/download/details.aspx?id=52950)
- [SQL Server 2014: Attunity의 Oracle용 Microsoft Connector 버전 3.0](https://www.microsoft.com/download/details.aspx?id=44582)
- [SQL Server 2012: Attunity의 Oracle용 Microsoft Connector 버전 2.0](https://www.microsoft.com/download/details.aspx?id=29283)

## <a name="limitations-and-known-issues"></a>제한 사항 및 알려진 문제

- Oracle 원본의 ‘테이블 또는 뷰 이름’에 뷰가 나열되지 않습니다. 해결 방법으로, SQL 명령을 사용하고 뷰에서 *를 선택하거나 고급 편집기에서 뷰 이름을 [Oracle Source].[TableName] 속성으로 설정하세요.

## <a name="uninstallation"></a>제거

제거 마법사를 실행하여 SQL Server에서 Microsoft Connector for Oracle 데이터베이스를 제거할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [Oracle 연결 관리자](oracle-connection-manager.md)를 구성합니다.
- [Oracle 원본](oracle-source.md)을 구성합니다.
- [Oracle 대상](oracle-destination.md)을 구성합니다.
- 질문이 있는 경우 [TechCommunity](https://aka.ms/AA5u35j)을 방문하세요.
