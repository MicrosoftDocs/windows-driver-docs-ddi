---
UID: NF:dbgeng.IDebugControl4.EvaluateWide
title: IDebugControl4::EvaluateWide (dbgeng.h)
description: The EvaluateWide method evaluates an expression, returning the result.
old-location: debugger\evaluatewide.htm
tech.root: debugger
ms.assetid: 1a40e8a7-ba7b-4aaf-975f-4095f9ef7ba7
ms.date: 05/03/2018
keywords: ["IDebugControl4::EvaluateWide"]
ms.keywords: EvaluateWide, EvaluateWide method [Windows Debugging], EvaluateWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],EvaluateWide method, IDebugControl4.EvaluateWide, IDebugControl4::EvaluateWide, dbgeng/IDebugControl4::EvaluateWide, debugger.evaluatewide
f1_keywords:
 - "dbgeng/IDebugControl4.EvaluateWide"
 - "IDebugControl4.EvaluateWide"
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl4.EvaluateWide
targetos: Windows
req.typenames: 
---

# IDebugControl4::EvaluateWide


## -description


The <b>EvaluateWide</b>  method evaluates an expression, returning the result.


## -parameters




### -param Expression [in]

Specifies the expression to be evaluated.


### -param DesiredType [in]

Specifies the desired return type.  Possible values are described in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a>; with the addition of DEBUG_VALUE_INVALID, which indicates that the return type should be the expression's natural type.


### -param Value [out]

Receives the value of the expression.


### -param RemainderIndex [out, optional]

Receives the index of the first character of the expression not used in the evaluation.  If <i>RemainderIndex</i> is <b>NULL</b>, this information isn't returned.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
An error occurred while evaluating the expression.  For example, there was a syntax error, an undefined variable, or a division by zero exception.

</td>
</tr>
</table>
 




## -remarks



Expressions are evaluated by the current <i>expression evaluator</i>.  The engine contains multiple expression evaluators; each supports a different syntax.  The current expression evaluator can be chosen by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntax">SetExpressionSyntax</a>.

For details of the available expression evaluators and their syntaxes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/numerical-expression-syntax">Numerical Expression Syntax</a>.

If an error occurs while evaluating the expression, returning E_FAIL, the <i>RemainderIndex</i> variable can be used to determine approximately where in the expression the error occurred. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexpressionsyntax">GetExpressionSyntax</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntax">SetExpressionSyntax</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntaxbyname">SetExpressionSyntaxByName</a>
 

 

