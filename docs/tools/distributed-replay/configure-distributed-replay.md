---
title: Configure Distributed Replay
titleSuffix: SQL Server Distributed Replay
description: 이 문서에서는 SQL Server의 Distributed Replay 기능을 사용하기 전에 고려해야 할 제품 요구 사항을 설명합니다.
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: aee11dde-daad-439b-b594-9f4aeac94335
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.openlocfilehash: bfbac9d60a1cdda4d4fe1ab1628088890e35be5a
ms.sourcegitcommit: a9f16d7819ed0e2b7ad8f4a7d4d2397437b2bbb2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88713791"
---
# <a name="configure-distributed-replay"></a>Configure Distributed Replay
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay 구성 세부 정보는 Distributed Replay 컨트롤러, 클라이언트 및 관리 도구가 설치되는 위치의 XML 파일에서 지정됩니다. 이러한 파일은 다음과 같습니다.  
  
-   [컨트롤러 구성 파일](#DReplayController)  
  
-   [클라이언트 구성 파일](#DReplayClient)  
  
-   [전처리 구성 파일](#PreprocessConfig)  
  
-   [재생 구성 파일](#ReplayConfig)  
  
##  <a name="controller-configuration-file-dreplaycontrollerconfig"></a><a name="DReplayController"></a> 컨트롤러 구성 파일: DReplayController.config  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay 컨트롤러 서비스가 시작되면 컨트롤러 구성 파일 `DReplayController.config`에서 로깅 수준을 로드합니다. 이 파일은 Distributed Replay 컨트롤러 서비스를 설치한 폴더에 있습니다.  
  
 **\<controller installation path>\DReplayController.config**  
  
 컨트롤러 구성 파일에 지정되는 로깅 수준은 다음과 같습니다.  
  
|설정|XML 요소|Description|허용되는 값|필수|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|로깅 수준|`<LoggingLevel>`|컨트롤러 서비스에 대한 로깅 수준을 지정합니다.|`INFORMATION` &#124; `WARNING` &#124; `CRITICAL`|아니요. 기본적으로 값은 `CRITICAL`입니다.|  
  
### <a name="example"></a>예제  
 이 예에서는 `INFORMATION` 및 `WARNING` 로그 항목을 표시하지 않도록 수정된 컨트롤러 구성 파일을 보여 줍니다.  
  
```  
<?xml version='1.0'?>  
<Options>  
<LoggingLevel>CRITICAL</LoggingLevel>  
</Options>  
```  
  
##  <a name="client-configuration-file-dreplayclientconfig"></a><a name="DReplayClient"></a> 클라이언트 구성 파일: DReplayClient.config  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay 클라이언트 서비스가 시작되면 클라이언트 구성 파일 `DReplayClient.config`에서 구성 설정을 로드합니다. 이 파일은 Distributed Replay 컨트롤러 서비스를 설치한 폴더에 있습니다.  
  
 **\<client installation path>\DReplayClient.config**  
  
 클라이언트 구성 파일에 지정되는 설정은 다음과 같습니다.  
  
|설정|XML 요소|Description|허용되는 값|필수|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|컨트롤러|`<Controller>`|컨트롤러의 컴퓨터 이름을 지정합니다. 클라이언트는 컨트롤러에 연결하여 Distributed Replay 환경에 등록합니다.|"`localhost`" 또는 "`.`"을 사용하여 로컬 컴퓨터를 참조할 수 있습니다.|아니요. 클라이언트는 기본적으로 로컬로 실행 중인("`.`") 컨트롤러 인스턴스(있는 경우)에 등록합니다.|  
|클라이언트 작업 디렉터리|`<WorkingDirectory>`|클라이언트에서 디스패치 파일이 저장된 로컬 경로입니다.<br /><br /> 이 디렉터리의 파일은 다음 재생 시 덮어씁니다.|드라이브 문자로 시작하는 전체 디렉터리 이름|아니요. 지정된 값이 없으면 디스패치 파일이 기본 클라이언트 구성 파일과 같은 위치에 저장됩니다. 지정된 값이 있지만 해당 폴더가 클라이언트에 없으면 클라이언트 서비스가 시작되지 않습니다.|  
|클라이언트 결과 디렉터리|`<ResultDirectory>`|클라이언트에서 클라이언트에 대한 재생 작업의 결과 추적 파일이 저장되는 로컬 경로입니다.<br /><br /> 이 디렉터리의 파일은 다음 재생 시 덮어씁니다.|드라이브 문자로 시작하는 전체 디렉터리 이름|아니요. 지정된 값이 없으면 결과 추적 파일이 기본 클라이언트 구성 파일과 같은 위치에 저장됩니다. 지정된 값이 있지만 해당 폴더가 클라이언트에 없으면 클라이언트 서비스가 시작되지 않습니다.|  
|로깅 수준|`<LoggingLevel>`|클라이언트 서비스에 대한 로깅 수준입니다.|`INFORMATION` &#124; `WARNING` &#124; `CRITICAL`|아니요. 기본적으로 값은 `CRITICAL`입니다.|  
  
### <a name="example"></a>예제  
 이 예에서는 컨트롤러 서비스가 `Controller1`이라는 다른 컴퓨터에서 실행되도록 수정된 클라이언트 구성 파일을 보여 줍니다. `WorkingDirectory` 및 `ResultDirectory` 요소는 각각 `c:\ClientWorkingDir` 및 `c:\ResultTraceDir`폴더를 사용하도록 구성되었습니다. `INFORMATION` 및 `WARNING` 로그 항목을 표시하지 않도록 기본값이 아닌 다른 값으로 로깅 수준이 변경되었습니다.  
  
```  
<?xml version='1.0'?>  
<Options>  
    <Controller>Controller1</Controller>  
    <WorkingDirectory>c:\ClientWorkingDir</WorkingDirectory>  
    <ResultDirectory>c:\ResultTraceDir</ResultDirectory>  
    <LoggingLevel>CRITICAL</LoggingLevel>  
</Options>  
```  
  
##  <a name="preprocess-configuration-file-dreplayexepreprocessconfig"></a><a name="PreprocessConfig"></a> 전처리 구성 파일: DReplay.exe.preprocess.config  
 관리 도구를 사용하여 전처리 단계를 시작하면 관리 도구가 전처리 구성 파일 `DReplay.exe.preprocess.config`에서 전처리 설정을 로드합니다.  
  
 기본 구성 파일을 사용하거나 관리 도구 **-c** 매개 변수를 사용하여 수정한 전처리 구성 파일의 위치를 지정할 수 있습니다. 관리 도구의 전처리 옵션 사용에 대한 자세한 내용은 [전처리 옵션&#40;Distributed Replay Utility Administration Tool&#41;](../../tools/distributed-replay/preprocess-option-distributed-replay-administration-tool.md)을 참조하세요.  
  
 기본 전처리 구성 파일은 관리 도구를 설치한 폴더에 있으면 위치는 다음과 같습니다.  
  
 **\<administration tool installation path>\DReplayAdmin\DReplay.exe.preprocess.config**  
  
 전처리 구성 설정은 전처리 구성 파일에서 `<PreprocessModifiers>` 요소의 자식 요소인 XML 요소에 지정됩니다. 이 설정은 다음을 포함합니다.  
  
|설정|XML 요소|Description|허용되는 값|필수|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|시스템 세션 작업 포함|`<IncSystemSession>`|캡처하는 동안의 시스템 세션 작업이 재생 중에 포함되는지 여부를 나타냅니다.|`Yes` &#124; `No`|아니요. 기본적으로 값은 `No`입니다.|  
|최대 유휴 시간|`<MaxIdleTime>`|유휴 시간을 절대 수(초)로 나타냅니다.|-1보다 크거나 같은 정수입니다.<br /><br /> `-1` 은 원래 추적 파일의 원래 값이 변경되지 않음을 의미합니다.<br /><br /> `0` 은 지정된 시점에 일부 작업이 진행 중임을 나타냅니다.|아니요. 기본적으로 값은 `-1`입니다.|  
  
### <a name="example"></a>예제  
 기본 전처리 구성 파일입니다.  
  
```  
<?xml version='1.0'?>  
<Options>  
    <PreprocessModifiers>  
        <IncSystemSession>No</IncSystemSession>  
        <MaxIdleTime>-1</MaxIdleTime>  
    </PreprocessModifiers>  
</Options>  
```  
  
##  <a name="replay-configuration-file-dreplayexereplayconfig"></a><a name="ReplayConfig"></a> 재생 구성 파일: DReplay.exe.replay.config  
 관리 도구를 사용하여 이벤트 재생 단계를 시작하면 관리 도구가 재생 구성 파일 `DReplay.exe.replay.config`에서 재생 설정을 로드합니다.  
  
 기본 구성 파일을 사용하거나 관리 도구 **-c** 매개 변수를 사용하여 수정한 재생 구성 파일의 위치를 지정할 수 있습니다. 관리 도구의 재생 옵션 사용에 대한 자세한 내용은 [재생 옵션&#40;Distributed Replay Administration Tool&#41;](../../tools/distributed-replay/replay-option-distributed-replay-administration-tool.md)을 참조하세요.  
  
 기본 재생 구성 파일은 관리 도구를 설치한 폴더에 있으며 위치는 다음과 같습니다.  
  
 **\<administration tool installation path>\DReplayAdmin\DReplay.exe.replay.config**  
  
 재생 구성 설정은 재생 구성 파일에서 `<ReplayOptions>` 및 `<OutputOptions>` 요소의 자식 요소인 XML 요소에 지정됩니다.  
  
### <a name="replayoptions-element"></a>\<ReplayOptions> 요소  
 재생 구성 파일의 `<ReplayOptions>` 요소에 지정되는 설정은 다음과 같습니다.  
  
|설정|XML 요소|Description|허용되는 값|필수|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|대상 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스(테스트 서버)|`<Server>`|연결할 서버 및 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스의 이름을 지정합니다.|*server_name*[\\*instance_name*]<br /><br /> "`localhost`" 또는 "`.`"을 사용하여 로컬 호스트를 나타낼 수 없습니다.|아니요(관리 도구의 **다시 재생**_옵션에_ -s **target server** 매개 변수를 사용하여 서버 이름이 이미 지정된 경우)|  
|시퀀스 모드|`<SequencingMode>`|이벤트 예약에 사용되는 모드를 지정합니다.|`synchronization` &#124; `stress`|아니요. 기본적으로 값은 `stress`입니다.|  
|스트레스 규모 세분성|`<StressScaleGranularity>`|스트레스 모드에서 SPID(Service Profile Identifier)에 대한 모든 연결의 배율을 함께 조정(SPID)해야 하는지 개별적으로 조정(연결)해야 하는지를 지정합니다.|SPID &#124; Connection|예. 기본적으로 값은 `SPID`입니다.|  
|연결 시간 조절|`<ConnectTimeScale>`|스트레스 모드에서 연결 시간을 조절하는 데 사용됩니다.|`1` 에서 `100`사이의 정수입니다.|아니요. 기본적으로 값은 `100`입니다.|  
|대기 시간 조절|`<ThinkTimeScale>`|스트레스 모드에서 대기 시간을 조절하는 데 사용됩니다.|`0` 에서 `100`사이의 정수입니다.|아니요. 기본적으로 값은 `100`입니다.|  
|연결 풀링 사용|`<UseConnectionPooling>`|각 Distributed Replay 클라이언트에서 연결 풀링을 사용할지 여부를 지정합니다.|Yes &#124; No|예. 기본적으로 값은 `Yes`입니다.|  
|상태 모니터 간격|`<HealthmonInterval>`|상태 모니터 실행 빈도(초)를 나타냅니다.<br /><br /> 이 값은 동기화 모드에서만 사용됩니다.|1보다 크거나 같은 정수입니다.<br /><br /> (비활성화하려면`-1` 로 설정)|아니요. 기본적으로 값은 `60`입니다.|  
|쿼리 제한 시간|`<QueryTimeout>`|쿼리 제한 시간 값(초)을 지정합니다. 이 값은 첫 번째 행이 반환될 때까지만 효력이 있습니다.|1보다 크거나 같은 정수입니다.<br /><br /> (비활성화하려면`-1` 로 설정)|아니요. 기본적으로 값은 `3600`입니다.|  
|클라이언트당 스레드 수|`<ThreadsPerClient>`|각 재생 클라이언트에 사용할 재생 스레드 수를 지정합니다.|`1` 에서 `512`사이의 정수입니다.|아니요. 지정하지 않으면 Distributed Replay가 값 `255`를 사용합니다.|  
  
### <a name="outputoptions-element"></a>\<OutputOptions> 요소  
 재생 구성 파일의 `<OutputOptions>` 요소에 지정되는 설정은 다음과 같습니다.  
  
|설정|XML 요소|Description|허용되는 값|필수|  
|-------------|-----------------|-----------------|--------------------|--------------|  
|행 개수 기록|`<RecordRowCount>`|각 결과 집합에 대해 행 개수를 기록할지 여부를 나타냅니다.|`Yes` &#124; `No`|아니요. 기본적으로 값은 `Yes`입니다.|  
|결과 집합 기록|`<RecordResultSet>`|모든 결과 집합의 내용을 기록할지 여부를 나타냅니다.|`Yes` &#124; `No`|아니요. 기본적으로 값은 `No`입니다.|  
  
### <a name="example"></a>예제  
 기본 재생 구성 파일:  
  
```  
<?xml version='1.0'?>  
<Options>  
    <ReplayOptions>  
        <Server></Server>  
        <SequencingMode>stress</SequencingMode>  
        <ConnectTimeScale></ConnectTimeScale>  
        <ThinkTimeScale></ThinkTimeScale>  
        <HealthmonInterval>60</HealthmonInterval>  
        <QueryTimeout>3600</QueryTimeout>  
        <ThreadsPerClient></ThreadsPerClient>  
    </ReplayOptions>  
    <OutputOptions>  
        <ResultTrace>  
            <RecordRowCount>Yes</RecordRowCount>  
            <RecordResultSet>No</RecordResultSet>  
        </ResultTrace>  
    </OutputOptions>  
</Options>  
```  

### <a name="possible-issue-when-running-with-synchronization-sequencing-mode"></a>동기화 시퀀싱 모드로 실행하는 경우 발생할 수 있는 문제
 재생 기능이 "정지"로 표시되거나 이벤트를 매우 느리게 재생하는 증상이 발생할 수 있습니다. 이러한 현상은 재생 중인 추적이 복원된 대상 데이터베이스에 존재하지 않는 데이터 및/또는 이벤트에 의존할 경우 발생할 수 있습니다. 
 
 한 가지 예는 Service Broker의 WAITFOR RECEIVE 문에서와 같이 WAITFOR를 사용하는 캡처된 워크로드입니다. 동기화 시퀀싱 모드를 사용하는 경우 일괄 처리는 순차적으로 재생됩니다. 데이터베이스 백업 이후지만 재생 캡처 추적이 시작되기 전에 원본 데이터베이스에 대해 삽입이 발생한 경우, 재생 중에 실행된 WAITFOR RECEIVE는 WAITFOR의 전체 지속 시간 동안 기다려야 할 수 있습니다. WAITFOR RECEIVE가 정지된 다음 재생되도록 설정되는 이벤트입니다. 그러면 WAITFOR가 완료될 때까지 재생 데이터베이스 대상에 대한 초당 일괄 처리 요청 성능 모니터 카운터가 0으로 떨어질 수 있습니다. 
 
 동기화 모드를 사용해야 하고 이 동작을 방지하려는 경우에는 다음을 수행해야 합니다.
 
1.  재생 대상으로 사용할 데이터베이스를 정지합니다.

2.  보류 중인 모든 작업이 완료될 수 있도록 허용합니다.

3.  데이터베이스를 백업하고 백업을 완료할 수 있도록 합니다.

4.  Distributed replay 추적 캡처를 시작하고 일반 작업을 다시 시작합니다. 
 
 
## <a name="see-also"></a>참고 항목  
 [관리 도구 명령줄 옵션&#40;Distributed Replay Utility&#41;](../../tools/distributed-replay/administration-tool-command-line-options-distributed-replay-utility.md)   
 [SQL Server Distributed Replay](../../tools/distributed-replay/sql-server-distributed-replay.md)   
 [SQL Server Distributed Replay 포럼](https://social.technet.microsoft.com/Forums/sl/sqldru/)   
 [Distributed Replay를 사용하여 SQL Server 테스트 로드 - 2단계](/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2)   
 [Distributed Replay를 사용하여 SQL Server 테스트 로드 - 1단계](/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)  
  
