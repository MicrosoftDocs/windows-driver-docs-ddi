---
UID: NF:dbgeng.IDebugControl3.SetExpressionSyntaxByName
title: IDebugControl3::SetExpressionSyntaxByName (dbgeng.h)
description: The SetExpressionSyntaxByName method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntaxbyname.htm
tech.root: debugger
ms.assetid: b9f1618a-e4f7-4eb1-952f-0f565a068dab
ms.date: 05/03/2018
keywords: ["IDebugControl3::SetExpressionSyntaxByName"]
ms.keywords: IDebugControl3 interface [Windows Debugging],SetExpressionSyntaxByName method, IDebugControl3.SetExpressionSyntaxByName, IDebugControl3::SetExpressionSyntaxByName, IDebugControl_88ebbf3c-a6f7-41d1-84e8-291a8db101c2.xml, SetExpressionSyntaxByName, SetExpressionSyntaxByName method [Windows Debugging], SetExpressionSyntaxByName method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl3::SetExpressionSyntaxByName, debugger.setexpressionsyntaxbyname
f1_keywords:
 - "dbgeng/IDebugControl3.SetExpressionSyntaxByName"
 - "IDebugControl3.SetExpressionSyntaxByName"
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
- IDebugControl3.SetExpressionSyntaxByName
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetExpressionSyntaxByName


## -description


The <b>SetExpressionSyntaxByName</b>  method sets the syntax that the engine will use to evaluate expressions.


## -parameters




### -param AbbrevName [in]

Specifies the abbreviated name of the syntax.  It can be one of the following strings:





#### C++

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/c---numbers-and-operators">C++ Numbers and Operators</a>.



#### MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/masm-numbers-and-operators">MASM Numbers and Operators</a>.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The expression syntax of the engine determines how the engine will interpret expressions passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-execute">Execute</a>, and any other method that evaluates an expression.

After the expression syntax has been changed, the engine sends out notification to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> callback object registered with each client.  It also passes the DEBUG_CES_EXPRESSION_SYNTAX flag to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexpressionsyntax">GetExpressionSyntax</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntax">SetExpressionSyntax</a>
 

 

