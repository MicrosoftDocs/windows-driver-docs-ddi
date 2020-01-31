---
UID: NF:wdbgexts.GetExpressionEx
title: GetExpressionEx function (wdbgexts.h)
description: The GetExpressionEx function evaluates an expression. The expression is evaluated using the MASM evaluator, and can contain aliases.
old-location: debugger\getexpressionex.htm
tech.root: debugger
ms.assetid: 07525217-afa5-4fbf-8c84-847ded9556d8
ms.date: 05/03/2018
ms.keywords: GetExpressionEx, GetExpressionEx function [Windows Debugging], WdbgExts_Ref_74af8a17-694a-46ec-827c-fdd2aecbf15c.xml, debugger.getexpressionex, wdbgexts/GetExpressionEx
f1_keywords:
 - "wdbgexts/GetExpressionEx"
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- GetExpressionEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetExpressionEx function


## -description


The <b>GetExpressionEx</b> function evaluates an expression. The expression is evaluated using the MASM evaluator, and can contain aliases.


## -parameters




### -param Expression

Specifies the expression to evaluate.  The expression uses the MASM syntax.  For details of this syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/masm-numbers-and-operators">MASM Numbers and Operators</a>.


### -param Value

Receives the value of the expression.


### -param Remainder

Receives a pointer to the first character in the expression <i>Expression</i> that was not used in the evaluation of the expression.


## -returns



<b>GetExpressionEx</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The expression was evaluated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FALSE</b></dt>
</dl>
</td>
<td width="60%">
An error occurred while attempting to evaluate the expression.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_get_expression">GetExpression</a>
 

 

