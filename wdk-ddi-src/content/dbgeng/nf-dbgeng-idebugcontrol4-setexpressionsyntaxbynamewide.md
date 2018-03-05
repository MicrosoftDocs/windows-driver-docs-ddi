---
UID: NF:dbgeng.IDebugControl4.SetExpressionSyntaxByNameWide
title: IDebugControl4::SetExpressionSyntaxByNameWide method
author: windows-driver-content
description: The SetExpressionSyntaxByNameWide method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntaxbynamewide.htm
old-project: debugger
ms.assetid: cad4ee84-333a-49ff-a087-da0e36b87989
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDebugControl4, IDebugControl4 interface [Windows Debugging], SetExpressionSyntaxByNameWide method, IDebugControl4::SetExpressionSyntaxByNameWide, SetExpressionSyntaxByNameWide method [Windows Debugging], SetExpressionSyntaxByNameWide method [Windows Debugging], IDebugControl4 interface, SetExpressionSyntaxByNameWide,IDebugControl4.SetExpressionSyntaxByNameWide, dbgeng/IDebugControl4::SetExpressionSyntaxByNameWide, debugger.setexpressionsyntaxbynamewide
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl4.SetExpressionSyntaxByNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::SetExpressionSyntaxByNameWide method


## -description


The  <b>SetExpressionSyntaxByNameWide</b> method sets the syntax that the engine will use to evaluate expressions.


## -syntax


````
HRESULT SetExpressionSyntaxByNameWide(
  [in] PCWSTR AbbrevName
);
````


## -parameters




### -param AbbrevName [in]

Specifies the abbreviated name of the syntax.  It can be one of the following strings:





#### C++

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540372">C++ Numbers and Operators</a>.



#### MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552157">MASM Numbers and Operators</a>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
</table>
 




## -remarks



The expression syntax is a global setting within the engine, so setting the expression syntax will affect all clients.

The expression syntax of the engine determines how the engine will interpret expressions passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543208">Execute</a>, and any other method that evaluates an expression.

After the expression syntax has been changed, the engine sends out notification to the <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> callback object registered with each client.  It also passes the DEBUG_CES_EXPRESSION_SYNTAX flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::SetExpressionSyntaxByNameWide method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

