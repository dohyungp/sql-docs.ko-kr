---
description: VBScript로 오류 처리
title: VBScript의 오류 처리 | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- VBScript error handling [ADO]
- errors [ADO], VBScript
ms.assetid: 31bc3743-32d3-4bc7-ac61-ee6ed0fdec70
author: rothja
ms.author: jroth
ms.openlocfilehash: 540319ac38bcf9f9c74eee74cff3b4f0f934f125
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88980644"
---
# <a name="handling-errors-in-vbscript"></a>VBScript로 오류 처리
Visual Basic에 사용 되는 메서드와 VBScript에서 사용 되는 방법 간에는 약간의 차이가 있습니다. 주요 차이점은 VBScript는 레이블에서 실행을 계속 하 여 오류 처리 개념을 지원 하지 않는다는 것입니다. 즉, VBScript에서는를 사용할 수 없습니다 `On Error GoTo` . 대신 다음 예제와 같이을 사용 하 `On Error Resume Next` 고 **Errors** 컬렉션의 Err 및 **Count** 속성을 모두 확인 **합니다** .  
  
```  
<!-- BeginErrorExampleVBS -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Visual Studio 6.0">  
<TITLE>Error Handling Example (VBScript)</TITLE>  
</HEAD>  
<BODY>  
  
<h1>Error Handling Example (VBScript)</h1>  
  
<%  
  
   Dim cnn1  
   Dim errLoop  
   Dim strError  
  
   On Error Resume Next  
  
   ' Intentionally trigger an error.  
   Set cnn1 = Server.CreateObject("ADODB.Connection")  
   cnn1.Open "nothing"  
  
   If cnn1.Errors.Count > 0 Then  
      ' Enumerate Errors collection and display  
      ' properties of each Error object.  
      For Each errLoop In cnn1.Errors  
         strError = "Error #" & errLoop.Number & "<br>" & _  
            "   " & errLoop.Description & "<br>" & _  
            "   (Source: " & errLoop.Source & ")" & "<br>" & _  
            "   (SQL State: " & errLoop.SQLState & ")" & "<br>" & _  
            "   (NativeError: " & errLoop.NativeError & ")" & "<br>"  
         If errLoop.HelpFile = "" Then  
            strError = strError & _  
               "   No Help file available" & _  
               "<br><br>"  
         Else  
            strError = strError & _  
               "   (HelpFile: " & errLoop.HelpFile & ")" & "<br>" & _  
               "   (HelpContext: " & errLoop.HelpContext & ")" & _  
               "<br><br>"  
         End If  
  
         Response.Write("<p>" & strError & "</p>")  
      Next  
   End If  
  
%>  
  
</BODY>  
</HTML>  
<!-- EndErrorExampleVBS -->  
```
