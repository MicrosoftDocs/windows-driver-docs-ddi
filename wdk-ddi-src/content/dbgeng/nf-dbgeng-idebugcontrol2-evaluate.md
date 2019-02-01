---
UID: NF:dbgeng.IDebugControl2.Evaluate
title: IDebugControl2::Evaluate (dbgeng.h)
description: The Evaluate method evaluates an expression, returning the result.
old-location: debugger\evaluate.htm
tech.root: debugger
ms.assetid: 67b17847-6ab3-4712-9ffc-94f8016e3c34
ms.date: 05/03/2018
ms.keywords: Evaluate, Evaluate method [Windows Debugging], Evaluate method [Windows Debugging],IDebugControl interface, Evaluate method [Windows Debugging],IDebugControl2 interface, Evaluate method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],Evaluate method, IDebugControl2 interface [Windows Debugging],Evaluate method, IDebugControl2.Evaluate, IDebugControl2::Evaluate, IDebugControl3 interface [Windows Debugging],Evaluate method, IDebugControl3::Evaluate, IDebugControl::Evaluate, IDebugControl_c985be86-1f8b-4b54-ae35-a7dec5980cec.xml, dbgeng/IDebugControl2::Evaluate, dbgeng/IDebugControl3::Evaluate, dbgeng/IDebugControl::Evaluate, debugger.evaluate
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.Evaluate
-	IDebugControl2.Evaluate
-	IDebugControl3.Evaluate
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::Evaluate


## -description


The <b>Evaluate</b>  method evaluates an expression, returning the result.


## -parameters




### -param Expression [in]

Specifies the expression to be evaluated.


### -param DesiredType [in]

Specifies the desired return type.  Possible values are described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff541719">DEBUG_VALUE</a>; with the addition of DEBUG_VALUE_INVALID, which indicates that the return type should be the expression's natural type.


### -param Value [out]

Receives the value of the expression.


### -param RemainderIndex [out, optional]

Receives the index of the first character of the expression not used in the evaluation.  If <i>RemainderIndex</i> is <b>NULL</b>, this information isn't returned.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



Expressions are evaluated by the current <i>expression evaluator</i>.  The engine contains multiple expression evaluators; each supports a different syntax.  The current expression evaluator can be chosen by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>.

For details of the available expression evaluators and their syntaxes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552280">Numerical Expression Syntax</a>.

If an error occurs while evaluating the expression, returning E_FAIL, the <i>RemainderIndex</i> variable can be used to determine approximately where in the expression the error occurred. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>
 

 

