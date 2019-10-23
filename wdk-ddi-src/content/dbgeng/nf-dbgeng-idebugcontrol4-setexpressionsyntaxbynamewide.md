---
UID: NF:dbgeng.IDebugControl4.SetExpressionSyntaxByNameWide
title: IDebugControl4::SetExpressionSyntaxByNameWide (dbgeng.h)
description: The SetExpressionSyntaxByNameWide method sets the syntax that the engine will use to evaluate expressions.
old-location: debugger\setexpressionsyntaxbynamewide.htm
tech.root: debugger
ms.assetid: cad4ee84-333a-49ff-a087-da0e36b87989
ms.date: 05/03/2018
ms.keywords: IDebugControl4 interface [Windows Debugging],SetExpressionSyntaxByNameWide method, IDebugControl4.SetExpressionSyntaxByNameWide, IDebugControl4::SetExpressionSyntaxByNameWide, SetExpressionSyntaxByNameWide, SetExpressionSyntaxByNameWide method [Windows Debugging], SetExpressionSyntaxByNameWide method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::SetExpressionSyntaxByNameWide, debugger.setexpressionsyntaxbynamewide
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl4.SetExpressionSyntaxByNameWide"
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
- IDebugControl4.SetExpressionSyntaxByNameWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::SetExpressionSyntaxByNameWide


## -description


The  <b>SetExpressionSyntaxByNameWide</b> method sets the syntax that the engine will use to evaluate expressions.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntax">SetExpressionSyntax</a>
 

 

