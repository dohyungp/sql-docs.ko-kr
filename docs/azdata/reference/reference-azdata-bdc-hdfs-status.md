---
title: azdata bdc hdfs status 참조
titleSuffix: SQL Server big data clusters
description: azdata bdc hdfs status 명령에 대한 참조 문서입니다.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: seanw
ms.date: 09/22/2020
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: f6cb7dccdd8c7f5894d9010a72ef4545a1019b7c
ms.sourcegitcommit: d56f1eca807c55cf606a6316f3872585f014fec1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90914824"
---
# <a name="azdata-bdc-hdfs-status"></a>azdata bdc hdfs status

`azdata`에 적용됩니다.

다음 문서에서는 **azdata** 도구의 **sql** 명령에 대한 참조를 제공합니다. 다른 **azdata** 명령에 대한 자세한 내용은 [azdata 참조](reference-azdata.md)를 참조하세요.

## <a name="commands"></a>명령

|명령|설명|
| --- | --- |
[azdata bdc hdfs status 표시](#azdata-bdc-hdfs-status-show) | Hdfs 서비스 상태입니다.
## <a name="azdata-bdc-hdfs-status-show"></a>azdata bdc hdfs status 표시
Hdfs 서비스 상태입니다.
```bash
azdata bdc hdfs status show [--resource -r] 
                            [--all -a]
```
### <a name="examples"></a>예제
hdfs 서비스의 상태를 가져옵니다.
```bash
azdata bdc hdfs status show
```
모든 인스턴스에서 hdfs 서비스 상태를 가져옵니다.
```bash
azdata bdc hdfs status show --all
```
hdfs 서비스 내에서 스토리지 리소스의 상태를 가져옵니다.
```bash
azdata bdc hdfs status show --resource storage-0
```
### <a name="optional-parameters"></a>선택적 매개 변수
#### `--resource -r`
이 서비스에서 이 리소스를 가져옵니다.
#### `--all -a`
서비스 내에서 각 리소스의 모든 인스턴스를 표시합니다.
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

