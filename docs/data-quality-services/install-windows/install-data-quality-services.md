---
description: Data Quality Services 설치
title: Data Quality Services 설치
ms.date: 09/11/2017
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 486e4216-a946-4c6e-828c-61bc905f7ec1
author: swinarko
ms.author: sawinark
ms.openlocfilehash: 35ca44da3c63d8de38a342cbf1f63bceb1916e15
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88462137"
---
# <a name="install-data-quality-services"></a>Data Quality Services 설치

[!INCLUDE [SQL Server - Windows only ](../../includes/applies-to-version/sql-windows-only.md)]

  [!INCLUDE[ssDQSnoversionLong](../../includes/ssdqsnoversionlong-md.md)](DQS)에는 및와 같은 두 가지 구성 요소가 있습니다. **[!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]** **[!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]**  
  
|DQS 구성 요소|설명|  
|-------------------|-----------------|  
|[!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]|[!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]는 [!INCLUDE[ssNoversion](../../includes/ssNoVersion-md.md)] 데이터베이스 엔진을 기반으로 설치되며 DQS_MAIN, DQS_PROJECTS 및 DQS_STAGING_DATA의 세 데이터베이스를 포함합니다. DQS_MAIN은 DQS 저장 프로시저, DQS 엔진 및 게시된 기술 자료를 포함합니다. DQS_PROJECTS는 데이터 품질 프로젝트 정보를 포함합니다. DQS_STAGING_DATA는 DQS 작업을 수행하기 위해 원본 데이터를 복사한 다음 처리된 데이터를 내보낼 수 있는 준비 영역입니다.|  
|[!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]|[!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)] 는 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]에 연결할 수 있게 해주는 독립 실행형 애플리케이션으로, 데이터 품질 작업 및 DQS와 관련된 기타 관리 태스크를 수행하기 위한 매우 직관적인 그래픽 사용자 인터페이스를 제공합니다.|  
  
> [!IMPORTANT]  
>  위의 두 가지 DQS 구성 요소 외에도 다음을 수행할 수 있습니다.  
>   
>  Integration Services 패키징 프로세스 내에서 데이터 정리를 수행하고 Integration Services를 설치할 때 자동으로 설치되는 Integration Services의 DQS 정리 변환을 사용할 수 있습니다. Integration Services 설치에 대한 자세한 내용은 [Integration Services 설치](../../integration-services/install-windows/install-integration-services.md)를 참조하세요.  
>   
>  MDS(Master Data Services)에서 DQS 통합을 사용하도록 설정하여 Excel용 MDS(Master Data Services) 추가 기능에서 DQS 일치 기능을 사용할 수 있습니다. 자세한 내용은 [MDS(Master Data Services)와 Data Quality Services의 통합 설정](../../master-data-services/install-windows/enable-data-quality-services-integration-with-master-data-services.md)을 참조하세요.  
  
 DQS 설치는 3단계로 수행되는 프로세스입니다.  
  
-   [설치 전 태스크](#PreInstallationTasks): DQS를 설치하기 전에 시스템 요구 사항을 확인합니다.  
  
-   [Data Quality Services 설치 태스크](#DQSInstallation): SQL Server 설치 프로그램을 사용하여 DQS를 설치합니다.  
  
-   [설치 후 태스크](#PostInstallationTasks): SQL Server 설치를 마친 후 다음 태스크를 수행하여 DQS 설치를 완료합니다.  
  
> [!NOTE]  
>  이 항목에서는 명령줄에서 설치 프로그램을 실행하는 데 대한 지침을 다루지 않습니다. [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 및 클라이언트 설치를 위한 명령줄 옵션에 대한 자세한 내용은 [명령 프롬프트에서 SQL Server 설치](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md#Feature) 에서 [기능 매개 변수](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)를 참조하세요.  
  
##  <a name="pre-installation-tasks"></a><a name="PreInstallationTasks"></a> 설치 전 태스크  
 DQS를 설치하기 전에 컴퓨터가 최소 시스템 요구 사항을 만족하는지 확인합니다. 다음 표에서는 DQS 구성 요소에 대한 최소 시스템 요구 사항 정보를 제공합니다.  
  
|DQS 구성 요소|최소 시스템 요구 사항|  
|-------------------|---------------------------------|  
|[!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]|메모리(RAM): 최소: 2GB / 권장: 4GB 이상<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] 데이터베이스 엔진 자세한 내용은 [SQL Server 데이터베이스 엔진 설치](../../database-engine/install-windows/install-sql-server-database-engine.md)를 참조하세요.|  
|[!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]|.NET Framework 4.0(이미 설치되어 있지 않은 경우 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)] 와 함께 설치됨)<br /><br /> Internet Explorer 6.0 SP1 이상|  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 및 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]는 동일한 컴퓨터나 별도의 컴퓨터에 설치할 수 있습니다. 두 가지 구성 요소는 모두 임의의 순서로 서로 독립적으로 설치할 수 있습니다. 하지만 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]를 사용하려면 연결할 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 가 설치되어 있어야 합니다.  
>   
>  최신 또는 이전 버전의 [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] 및 DQS 정리 변환을 사용하여 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 버전의 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)] 에 연결할 수 있습니다. 기존 버전의 DQS를 [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]로 업그레이드하는 방법은 [Data Quality Services 업그레이드](../../database-engine/install-windows/upgrade-data-quality-services.md)를 참조하세요.  
>   
>  Microsoft Excel은 Data Quality 클라이언트를 설치하기 위한 필수 구성 요소는 아니지만, Excel 파일에서 도메인 값을 가져오거나 기술 자료 검색, 정리 또는 일치 작업을 위해 Excel 파일의 원본 데이터에 매핑하는 등의 다양한 작업을 클라이언트 애플리케이션에서 수행하려면 Data Quality 클라이언트 컴퓨터에 Microsoft Excel 2003 이상이 설치되어 있어야 합니다.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)]설치에 대한 최소 시스템 요구 사항에 대한 자세한 내용은 [SQL Server 설치를 위한 하드웨어 및 소프트웨어 요구 사항](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)을 참조하세요.  
  
##  <a name="data-quality-services-installation-tasks"></a><a name="DQSInstallation"></a> Data Quality Services 설치 태스크  
 DQS 구성 요소를 설치하려면 [!INCLUDE[ssNoVersion](../../includes/ssNoVersion-md.md)] 설치 프로그램을 사용해야 합니다. SQL Server 설치 프로그램을 실행할 때는 일련의 설치 마법사 페이지를 진행하면서 요구 사항에 따라 적합한 옵션을 선택해야 합니다. 다음 표에서는 선택한 옵션이 DQS 설치에 영향을 미치는 설치 마법사 페이지만 보여 줍니다.  
  
|페이지|작업|  
|----------|------------|  
|기능 선택|선택:<br /><br /> **데이터베이스 엔진 서비스** 아래에서 **Data Quality Services** 를 선택하여 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]를 설치합니다. <br />**Data Quality Services** 확인란을 선택한 경우 SQL Server 설치 프로그램에서 설치 파일인 DQSInstaller.exe를 컴퓨터의 SQL Server 인스턴스 디렉터리에 복사합니다. SQL Server 설치 프로그램을 완료한 후 이 파일을 실행하여 *설치를* 완료 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 해야 합니다. 또한 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 를 사용하려면 먼저 몇 가지 추가 단계를 수행하여 DQS 서버를 구성해야 합니다. 자세한 내용은 [설치 후 태스크](#PostInstallationTasks)를 참조하세요.<br /><br /> **Data Quality 클라이언트** 를 선택하여 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]를 설치합니다.<br /><br /> 바람직하지 **관리 도구-** **관리 도구-기본** 에서 설치를 완료 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 합니다. 이렇게 하면 그래픽 사용자 인터페이스를 사용하여 SQL Server 인스턴스를 관리할 수 있으며, 다음 섹션에 나열된 추가 사후 설치 태스크를 수행하는 데에도 도움이 됩니다.|  
|데이터베이스 엔진 구성|**현재 사용자 추가** 를 클릭하여 사용자 Windows 계정을 sysadmin 고정 서버 역할에 추가합니다. 나중에 DQSInstaller.exe 파일을 실행하여 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 설치를 완료하기 위해서는 이 과정이 필요합니다.|  
  
##  <a name="post-installation-tasks"></a><a name="PostInstallationTasks"></a> 설치 후 작업  
 SQL Server 설치 마법사를 완료한 후 이 섹션에 언급된 추가 단계를 수행해야 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 설치 및 구성을 완료하여 사용할 수 있습니다.  
  
1.  [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 설치를 완료하려면 DQSInstaller.exe 파일을 실행합니다. DQSInstaller.exe 파일 실행 시:  
  
    -   DQS_MAIN, DQS_PROJECTS 및 DQS_STAGING_DATA 데이터베이스가 만들어집니다.  
  
    -   ##MS_dqs_db_owner_login## 및 ##MS_dqs_service_login## 로그인이 만들어집니다.  
  
    -   dqs_administrator, dqs_kb_editor 및 dqs_kb_operator 역할은 DQS_MAIN 데이터베이스에 만들어집니다.  
  
    -   DQInitDQS_MAIN 저장 프로시저는 master 데이터베이스에 만들어집니다.  
  
    -   DQS_install.log 파일은 일반적으로 C:\Program Files\Microsoft SQL Server\MSSQL13.*<instance_name>* \MSSQL\Log 폴더에 만들어집니다. 이 파일에는 DQSInstaller.exe 파일을 실행할 때 수행되는 동작에 대한 정보가 포함됩니다.  
  
    -   MDS(Master Data Services) 데이터베이스가 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)]와 같은 SQL Server 인스턴스에 있는 경우 MDS(Master Data Services) 로그인에 매핑된 사용자가 만들어지고 DQS_MAIN 데이터베이스의 dqs_administrator 역할이 부여됩니다.  
  
     이렇게 하면 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 설치가 완료됩니다.  
  
     자세한 내용은 [DQSInstaller.exe를 실행 하 여 Data Quality 서버 설치 완료를](../../data-quality-services/install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md)참조 하세요.  
  
2.  사용자에게 DQS 역할 부여:  
  
     [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 를 사용하여 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]에 로그온하려면 DQS_MAIN 데이터베이스에 대한 다음 세 가지 역할 중 최소한 하나 이상이 사용자에게 있어야 합니다.  
  
    -   **dqs_administrator**  
  
    -   **dqs_kb_editor**  
  
    -   **dqs_kb_operator**  
  
     기본적으로 사용자 계정이 sysadmin 고정 서버 역할의 멤버인 경우 사용자 계정에게 할당된 DQS 역할이 없더라도 [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] 를 사용하여 [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)] 에 로그온할 수 있습니다. 세 가지 DQS 역할에 대한 자세한 내용은 [DQS 보안](../../data-quality-services/dqs-security.md)을 참조하십시오.  
  
     자세한 내용은 [사용자에게 DQS 역할 부여](../../data-quality-services/install-windows/grant-dqs-roles-to-users.md)를 참조하세요.  
  
    > [!NOTE]  
    >  DQS_PROJECTS 및 DQS_STAGING_DATA 데이터베이스의 경우 이 세 가지 역할을 사용할 수 없습니다.  
  
3.  DQS 작업에 데이터를 사용할 수 있도록 설정합니다. DQS 작업을 위해 원본 데이터에 액세스할 수 있고 처리된 데이터를 데이터베이스 테이블로 내보낼 수 있는지 확인합니다.  
  
     자세한 내용은  
                    [DQS 작업의 데이터에 액세스](../../data-quality-services/install-windows/access-data-for-the-dqs-operations.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비디오: DQS 설치 및 구성](https://go.microsoft.com/fwlink/?LinkId=238241)   
 [.NET Framework 업데이트 후 SQLCLR 어셈블리 업그레이드](../../data-quality-services/install-windows/upgrade-sqlclr-assemblies-after-net-framework-update.md)   
 [DQSInstaller.exe를 사용 하 여 DQS 기술 자료 내보내기 및 가져오기 ](../../data-quality-services/install-windows/export-and-import-dqs-knowledge-bases-using-dqsinstaller-exe.md)   
 [Data Quality Services 업그레이드](../../database-engine/install-windows/upgrade-data-quality-services.md)   
 [Data Quality 서버 개체 제거](../../sql-server/install/remove-data-quality-server-objects.md)   
 [SQL Server 비즈니스 인텔리전스 기능 설치](../../sql-server/install/install-sql-server-business-intelligence-features.md)   
 [제거 SQL Server](../../sql-server/install/uninstall-sql-server.md)   
 [Data Quality Services](../../data-quality-services/data-quality-services.md)   
 [DQS에서 설치 및 구성 문제 해결](https://social.technet.microsoft.com/wiki/contents/articles/3776.aspx)  
  
  
