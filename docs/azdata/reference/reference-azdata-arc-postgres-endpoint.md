---
title: azdata arc postgres endpoint 참조
titleSuffix: SQL Server big data clusters
description: azdata arc postgres endpoint 명령에 대한 참조 문서입니다.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 42e5144ca4cfd3544e9a93a5464bea531af21187
ms.sourcegitcommit: d56f1eca807c55cf606a6316f3872585f014fec1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90942912"
---
# <a name="azdata-arc-postgres-endpoint"></a>azdata arc postgres endpoint

`azdata`에 적용됩니다.

다음 문서에서는 **azdata** 도구의 **sql** 명령에 대한 참조를 제공합니다. 다른 **azdata** 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요.

## <a name="commands"></a>명령

|명령|설명|
| --- | --- |
[azdata arc postgres endpoint list](#azdata-arc-postgres-endpoint-list) | PostgreSQL 서버 그룹 엔드포인트를 나열합니다.
## <a name="azdata-arc-postgres-endpoint-list"></a>azdata arc postgres endpoint list
PostgreSQL 서버 그룹 엔드포인트를 나열합니다.
```bash
azdata arc postgres endpoint list --name -n 
                                  [--engine-version -ev]
```
### <a name="examples"></a>예
PostgreSQL 서버 그룹 엔드포인트를 나열합니다.
```bash
azdata arc postgres endpoint list -n postgres01
```
### <a name="required-parameters"></a>필수 매개 변수
#### `--name -n`
PostgreSQL 서버 그룹의 이름입니다.
### <a name="optional-parameters"></a>선택적 매개 변수
#### `--engine-version -ev`
엔진 버전이 다른 두 서버 그룹의 이름이 같은 경우 --name과 함께 --engine-version을 사용하여 PostgreSQL 하이퍼스케일 서버 그룹을 식별할 수 있습니다. --engine-version은 선택 사항으로, 서버 그룹을 식별하는 데 사용할 경우 11 또는 12여야 합니다.
### <a name="global-arguments"></a>전역 인수
#### `--debug`
로깅의 자세한 정도를 늘려 모든 디버그 로그를 표시합니다.
#### `--help -h`
이 도움말 메시지를 표시하고 종료합니다.
#### `--output -o`
출력 형식입니다.  허용되는 값: json, jsonc, table, tsv  기본값: json
#### `--query -q`
JMESPath 쿼리 문자열입니다. 자세한 내용 및 예제는 [http://jmespath.org/](http://jmespath.org)를 참조하세요.
#### `--verbose`
로깅의 자세한 정도를 늘립니다. 전체 디버그 로그를 표시하려면 --debug를 사용합니다.

## <a name="next-steps"></a>다음 단계

다른 **azdata** 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요. 

**azdata** 도구를 설치하는 방법에 대한 자세한 내용은 [azdata 설치](..\install\deploy-install-azdata.md)를 참조하세요.

