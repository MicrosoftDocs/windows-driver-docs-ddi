---
UID: NF:dbgeng.IDebugControl.Evaluate
title: IDebugControl::Evaluate method
author: windows-driver-content
description: The Evaluate method evaluates an expression, returning the result.
old-location: debugger\evaluate.htm
old-project: debugger
ms.assetid: 67b17847-6ab3-4712-9ffc-94f8016e3c34
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Evaluate, Evaluate method [Windows Debugging], IDebugControl2 interface, Evaluate method [Windows Debugging], IDebugControl interface, Evaluate method [Windows Debugging], IDebugControl2 interface [Windows Debugging], Evaluate method, debugger.evaluate, dbgeng/IDebugControl3::Evaluate, IDebugControl_c985be86-1f8b-4b54-ae35-a7dec5980cec.xml, IDebugControl interface [Windows Debugging], Evaluate method, IDebugControl2::Evaluate, IDebugControl3 interface [Windows Debugging], Evaluate method, Evaluate method [Windows Debugging], IDebugControl3 interface, IDebugControl::Evaluate, IDebugControl, dbgeng/IDebugControl::Evaluate, dbgeng/IDebugControl2::Evaluate, IDebugControl3::Evaluate
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl.Evaluate
-	IDebugControl2.Evaluate
-	IDebugControl3.Evaluate
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl::Evaluate method


## -description


The <b>Evaluate</b>  method evaluates an expression, returning the result.


## -syntax


````
HRESULT Evaluate(
  [in]            PCSTR        Expression,
  [in]            ULONG        DesiredType,
  [out]           PDEBUG_VALUE Value,
  [out, optional] PULONG       RemainderIndex
);
````


## -parameters




### -param Expression [in]

Specifies the expression to be evaluated.


### -param DesiredType [in]

Specifies the desired return type.  Possible values are described in <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a>; with the addition of DEBUG_VALUE_INVALID, which indicates that the return type should be the expression's natural type.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556697">SetExpressionSyntaxByName</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::Evaluate method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

