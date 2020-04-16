---
UID: NF:dbgeng.IDebugControl3.GetExpressionSyntax
title: IDebugControl3::GetExpressionSyntax (dbgeng.h)
description: The GetExpressionSyntax method returns the current syntax that the engine is using for evaluating expressions.
old-location: debugger\getexpressionsyntax.htm
tech.root: debugger
ms.assetid: e04e4567-5ae6-4349-9876-0c2b55c340e0
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetExpressionSyntax"]
ms.keywords: GetExpressionSyntax, GetExpressionSyntax method [Windows Debugging], GetExpressionSyntax method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetExpressionSyntax method, IDebugControl3.GetExpressionSyntax, IDebugControl3::GetExpressionSyntax, IDebugControl_9eae3270-fd1f-4d50-875b-3bd9908ba76d.xml, dbgeng/IDebugControl3::GetExpressionSyntax, debugger.getexpressionsyntax
f1_keywords:
 - "dbgeng/IDebugControl3.GetExpressionSyntax"
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
- IDebugControl3.GetExpressionSyntax
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetExpressionSyntax


## -description


The <b>GetExpressionSyntax</b> method returns the current syntax that the engine is using for evaluating expressions.


## -parameters




### -param Flags [out]

Receives the expression syntax.  It is set to one of the following values:





#### DEBUG_EXPR_MASM

Expressions will be evaluated according to MASM syntax. For details of this syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/masm-numbers-and-operators">MASM Numbers and Operators</a>.



#### DEBUG_EXPR_CPLUSPLUS

Expressions will be evaluated according to C++ syntax. For details of this syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/c---numbers-and-operators">C++ Numbers and Operators</a>.


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
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-evaluate">Evaluate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntax">SetExpressionSyntax</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexpressionsyntaxbyname">SetExpressionSyntaxByName</a>
 

 

