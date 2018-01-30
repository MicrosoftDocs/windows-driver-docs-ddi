---
UID: NF:dbgeng.IDebugControl3.SetExpressionSyntaxByName
title: IDebugControl3::SetExpressionSyntaxByName method
author: windows-driver-content
description: The SetExpressionSyntaxByName method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntaxbyname.htm
old-project: debugger
ms.assetid: b9f1618a-e4f7-4eb1-952f-0f565a068dab
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.setexpressionsyntaxbyname, IDebugControl3 interface [Windows Debugging], SetExpressionSyntaxByName method, SetExpressionSyntaxByName method [Windows Debugging], IDebugControl3 interface, IDebugControl3, SetExpressionSyntaxByName method [Windows Debugging], IDebugControl3::SetExpressionSyntaxByName, IDebugControl_88ebbf3c-a6f7-41d1-84e8-291a8db101c2.xml, dbgeng/IDebugControl3::SetExpressionSyntaxByName, SetExpressionSyntaxByName
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
-	IDebugControl3.SetExpressionSyntaxByName
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugControl3::SetExpressionSyntaxByName method


## -description


The <b>SetExpressionSyntaxByName</b>  method sets the syntax that the engine will use to evaluate expressions.


## -syntax


````
HRESULT SetExpressionSyntaxByName(
  [in] PCSTR AbbrevName
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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546701">GetExpressionSyntax</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543046">Evaluate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556696">SetExpressionSyntax</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::SetExpressionSyntaxByName method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

