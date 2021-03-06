---
title: 파일에서 바꾸기
description: 찾기 및 바꾸기 창의 파일에서 바꾸기 기능을 사용하여 파일 집합의 텍스트에서 특정 문자열 또는 식을 검색하고 찾은 텍스트의 일부 또는 모두를 변경하는 방법을 알아봅니다.
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.prod: sql
ms.technology: ssms
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Replace in Files dialog box
ms.assetid: 51191c0a-e022-41d6-8473-5cb3c6596862
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: dbf692581a7ad2cb6d1e2bb5ad600b65fc63d7c3
ms.sourcegitcommit: 6d53ecfdc463914f045c20eda96da39dec22acca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88901967"
---
# <a name="replace-in-files"></a>파일에서 바꾸기
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
  찾기 및 바꾸기 창의 **파일에서 바꾸기** 탭을 사용하여 지정한 파일 집합의 코드에서 문자열이나 식을 검색하고 일치하는 항목을 일부 또는 모두 변경할 수 있습니다. **결과 옵션**에서 선택한 찾기 결과 창에 일치하는 항목과 수행한 동작이 나열됩니다.  
  
 도구 모음 단추 및 바로 가기 키를 사용하여 **찾기 및 바꾸기** 대화 상자를 열 수도 있습니다.  
  
## <a name="find-what"></a>찾을 내용  
 **파일에서 바꾸기** 탭의 컨트롤을 사용하여 검색할 문자열이나 식을 지정할 수 있습니다.  
  
 **찾을 내용**  
 검색할 텍스트를 입력합니다. 대화 상자에서는 대화 상자를 열기 전에 커서로 선택한 텍스트, 가까이 위치한 텍스트 또는 이전에 검색한 텍스트를 사용하여 가능한 검색 텍스트를 입력합니다. 드롭다운 목록에서 검색 문자열을 선택하여 가장 최근에 사용한 20개의 문자열을 다시 사용할 수 있습니다.  
  
 **[와일드카드가 포함된 문자열]**  
 검색 문자열에 별표(`*`) 및 물음표(`?`)와 같은 와일드카드를 사용하려면 **찾기 옵션** 아래의 **사용** 확인란을 선택한 다음 **와일드카드**를 클릭합니다.  
  
 **[정규식]**  
 검색 엔진에서 검색 문자열을 정규식으로 해석하려면 **찾기 옵션** 아래의 **사용** 확인란을 선택한 다음 **정규식**을 클릭합니다.  
  
 **식 작성기**  
 **찾기 옵션** 에서 **사용** 확인란을 선택하면 **찾을 내용**입력란 옆에 있는 삼각형 단추가 활성화됩니다. 이 단추를 클릭하면 선택한 **사용** 옵션에 따라 와일드카드 또는 정규식 목록이 표시됩니다. 이 목록에서 항목을 선택하면 해당 항목이 **찾을 내용** 입력란에 지정된 문자열에 추가됩니다.  
  
## <a name="replace-with"></a>바꿀 항목  
 이러한 컨트롤을 사용하면 일치하는 문자열 또는 식의 자리에 삽입할 내용을 지정할 수 있습니다.  
  
 **Replace with**  
 **찾을 내용** 에 지정된 문자열의 인스턴스를 다른 문자열로 바꾸려면 이 필드에 바꿀 문자열을 입력합니다. **찾을 내용**에 지정된 문자열의 인스턴스를 삭제하려면 이 입력란을 비워 둡니다. 가장 최근에 입력한 20개의 항목을 표시하려면 드롭다운 목록을 선택합니다. **바꿀 내용** 입력란에 지정된 문자열에 정규식을 포함하려면 **사용** 확인란을 클릭한 다음 **정규식** 옵션을 클릭합니다.  
  
 **식 작성기**  
 **찾기 옵션** 에서 **사용** 확인란을 선택하면 **바꿀 내용**입력란 옆에 있는 삼각형 단추가 활성화됩니다. 이 단추를 클릭하면 선택한 **사용** 옵션에 따라 와일드카드 또는 정규식 목록이 표시됩니다. 이 목록에서 항목을 클릭하면 해당 항목이 **바꿀 내용** 입력란에 지정된 문자열에 추가됩니다.  
  
 **바꾸기**  
 **찾을 내용** 에 지정된 문자열의 현재 인스턴스를 **바꿀 내용** 입력란에 지정된 문자열로 바꾸고 **찾는 위치**에 지정된 범위 내에서 다음 인스턴스를 찾으려면 이 단추를 클릭합니다.  
  
 **모두 바꾸기**  
 **찾는 위치** 에 지정된 범위 내의 모든 파일에서 **찾을 내용** 에 지정된 문자열을 **바꿀 내용**확인란에 지정된 문자열로 바꾸려면 이 단추를 클릭합니다.  
  
> [!CAUTION]  
>  **찾는 위치** 에 수정하려는 파일만 포함되도록 설정되어 있는지 확인합니다.  
  
 **모두 바꾸기를 실행한 후 수정한 파일 열어 두기** 옵션이 포함된 미리 알림이 표시됩니다. **실행 취소** 옵션을 유지하려면 이 옵션을 선택해야 합니다. **실행 취소** 는 수정 후에 편집을 위해 계속 열려 있는 파일에서만 사용할 수 있습니다.  
  
 **파일 건너뛰기**  
 **찾는 위치** 에 여러 파일이 포함될 때 사용할 수 있게 됩니다. 현재 파일을 검색 또는 수정하지 않으려면 이 단추를 클릭합니다. 검색은 **찾는 위치**의 목록에 있는 다음 파일에서 계속됩니다.  
  
## <a name="look-in"></a>찾는 위치  
 **찾는 위치** 드롭다운 목록에서 선택한 옵션에 따라 **파일에서 바꾸기** 를 사용할 때 현재 활성 파일에서만 검색할지 특정 폴더 내에 저장된 파일을 모두 검색할지 결정됩니다. 목록에서 검색 범위를 선택하거나 폴더 경로를 입력하거나 **찾아보기** 단추를 클릭하여 **사용자 지정 디렉터리 집합** 대화 상자를 표시하고 검색할 폴더 집합을 선택합니다.  
  
> [!NOTE]  
>  **찾는 위치** 옵션을 선택하면 원본 코드 제어에서 체크 아웃한 파일을 검색합니다. 즉, 로컬 컴퓨터로 다운로드한 버전만 검색합니다.  
  
 **Look in**  
 이 목록에서 미리 정의된 검색 범위를 선택하거나 **사용자 지정 디렉터리 집합** 대화 상자를 사용하여 원하는 디렉터리 집합을 입력합니다.  
  
 **현재 문서**  
 이 옵션은 편집기에 문서가 열려 있을 때 사용할 수 있습니다. **찾을 내용**에 지정된 문자열을 활성 문서에서만 검색합니다.  
  
 **모든 열린 문서**  
 편집하기 위해 현재 열려 있는 모든 파일을 검색합니다.  
  
 **현재 프로젝트**  
 활성 프로젝트에 있는 모든 파일을 검색합니다.  
  
 **전체 솔루션**  
 활성 솔루션에 있는 모든 파일을 검색합니다.  
  
 **하위 폴더 포함**  
 **찾는 위치** 에서 지정한 폴더의 하위 폴더도 검색하도록 지정합니다. 이 옵션을 사용하려면 사용자 지정 디렉터리 집합이 있어야 합니다.  
  
 **찾아보기(...)**  
 **찾는 위치** 상자에 입력할 명명된 디렉터리 집합을 조합, 편집, 저장 및 선택할 수 있는 **검색 폴더 선택** 대화 상자를 표시하려면 이 단추를 클릭합니다.  
  
## <a name="find-options"></a>사용  
 **찾기 옵션** 섹션을 확장하거나 축소할 수 있습니다. 다음과 같은 옵션을 선택하거나 선택 취소할 수 있습니다.  
  
 **대/소문자 구분**  
 이 확인란을 선택하면 찾기 결과 창에 **찾을 내용** 에 지정된 문자열의 인스턴스 중 내용과 대/소문자가 모두 일치하는 인스턴스만 표시됩니다. 예를 들어 **대/소문자 구분** 확인란을 선택하고 " **MyObject** "를 검색하면 "MyObject"는 반환되지만 "myobject"나 "MYOBJECT"는 반환되지 않습니다.  
  
 **단어 단위로**  
 이 확인란을 선택하면 **찾을 내용** 에 지정한 문자열과 단어 단위로 일치하는 인스턴스만 찾기 결과 창에 표시됩니다. 예를 들어 **MyObject** 를 검색하면 "MyObject"는 반환되지만 "CMyObject"나 "MyObjectC"는 반환되지 않습니다.  
  
 **사용**  
 **찾을 내용** 또는 **바꿀 내용** 입력란에 입력한 특수 문자의 해석 방법을 나타냅니다. 옵션에는 **와일드카드** 및 **정규식**이 있습니다.  
  
 **Regular Expressions**  
 특수 표기를 사용하여 일치하는 텍스트의 패턴을 정의합니다. 목록을 보려면 [정규식으로 텍스트 검색](../../relational-databases/scripting/search-text-with-regular-expressions.md)을 참조하세요.  
  
 **와일드카드**  
 별표(`*`) 및 물음표(`?`)와 같은 특수 문자는 하나 이상의 문자를 나타냅니다. 목록을 보려면 [와일드카드로 텍스트 검색](../../relational-databases/scripting/search-text-with-wildcards.md)을 참조하세요.  
  
 **이 파일 형식 보기**  
 이 목록은 **찾는 위치**에 지정한 디렉터리에서 검색할 파일 유형을 나타냅니다. 이 상자를 비워 두면 **찾는 위치** 에 지정된 디렉터리의 모든 파일이 검색됩니다.  
  
```  
*.[ext]; *.[ext] (manual)  
```  
  
 특정 유형의 파일을 찾으려면 파일 이름에 별표 와일드카드(`*`)를 입력하고 뒤에 마침표(`.`)와 파일 확장명을 추가합니다. 둘 이상의 파일 유형을 찾으려면 여러 개의 검색 문자열을 세미콜론(`;`)으로 구분하여 입력합니다.  
  
```  
*.[ext]; *.[ext] (from list)  
```  
  
 특정 유형의 파일을 찾는 미리 구성된 검색 문자열을 입력하려면 목록에서 임의 항목을 선택합니다.  
  
## <a name="result-options"></a>결과 옵션  
 **결과 옵션** 섹션은 확장하거나 축소할 수 있습니다. 다음과 같은 옵션을 선택하거나 선택 취소할 수 있습니다.  
  
 **찾기 결과 1 창**  
 이 확인란을 선택하면 현재 검색 결과가 찾기 결과 1 창의 내용에 추가됩니다. 이 창은 자동으로 열려 검색 결과를 표시합니다. 이 창을 수동으로 열려면 **보기** 메뉴의 **다른 창** 을 클릭한 다음 **찾기 결과 1**을 클릭합니다.  
  
 **찾기 결과 2 창**  
 이 확인란을 선택하면 현재 검색 결과가 찾기 결과 2 창의 내용에 추가됩니다. 이 창은 자동으로 열려 검색 결과를 표시합니다. 이 창을 수동으로 열려면 **보기** 메뉴의 **다른 창** 을 클릭한 다음 **찾기 결과 2**를 클릭합니다.  
  
 **파일 이름만 표시**  
 검색 조건과 일치하는 각 항목 대신 검색 조건과 일치하는 항목이 포함된 파일 단위로 찾기 결과 1 또는 찾기 결과 2 창에 표시합니다. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에서는 이 옵션을 사용할 수 없습니다.  
  
 **모두 바꾸기를 실행한 후 수정한 파일 열어 두기**  
 이 확인란을 선택하면 변경 내용을 실행 취소하거나 저장할 수 있도록 바꾸기를 수행한 모든 파일을 열어 둡니다. 메모리 제약 때문에 바꾸기 작업 후에 열어 둘 수 있는 파일 수는 제한됩니다.  
  
> [!CAUTION]  
>  편집하기 위해 열어 둔 파일에 대해서만 **실행 취소** 를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 편집하기 위해 열어 두지 않은 파일은 계속 닫혀 있으며 해당 파일에 대해 **실행 취소** 옵션을 사용할 수 없습니다.  
  
## <a name="find-and-replace-views"></a>찾기 및 바꾸기 뷰  
 찾기 및 바꾸기 창의 위쪽에 있는 탭에는 **보기** 메뉴가 있습니다. 이러한 메뉴를 사용하면 활성 창에서 표시할 필드 집합을 선택할 수 있습니다. 찾기 및 바꾸기 창은 사용하기 편한 위치에 도킹한 다음 탭 및 보기 사이를 오가며 찾기 또는 바꾸기 작업을 수행할 수 있습니다.  
  
 **빠른 찾기로 전환**  
 이 도구 모음 탭은 대화 상자를 **빠른 찾기** 대화 상자로 변경합니다.  
  
 **파일에서 찾기로 전환**  
 이 도구 모음 탭은 대화 상자를 **파일에서 찾기** 대화 상자로 변경합니다.  
  
 **기호 찾기로 전환**  
 이 도구 모음 탭은 대화 상자를 **기호 찾기** 대화 상자로 변경합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server Management Studio 바로 가기 키](../../ssms/sql-server-management-studio-keyboard-shortcuts.md)  
