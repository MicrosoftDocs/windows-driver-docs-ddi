---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffsetExpression
title: IDebugBreakpoint2::GetOffsetExpression (dbgeng.h)
description: The GetOffsetExpression methods return the expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\getoffsetexpression.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetOffsetExpression"]
ms.keywords: ComOther_08bb15b2-f37d-4bd2-b19a-899ab9293f4a.xml, GetOffsetExpression, GetOffsetExpression method [Windows Debugging], GetOffsetExpression method [Windows Debugging],IDebugBreakpoint interface, GetOffsetExpression method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetOffsetExpression method, IDebugBreakpoint2 interface [Windows Debugging],GetOffsetExpression method, IDebugBreakpoint2.GetOffsetExpression, IDebugBreakpoint2::GetOffsetExpression, IDebugBreakpoint::GetOffsetExpression, dbgeng/IDebugBreakpoint2::GetOffsetExpression, dbgeng/IDebugBreakpoint::GetOffsetExpression, debugger.getoffsetexpression
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugBreakpoint2::GetOffsetExpression
 - dbgeng/IDebugBreakpoint2::GetOffsetExpression
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint.GetOffsetExpression
 - IDebugBreakpoint2.GetOffsetExpression
---

# IDebugBreakpoint2::GetOffsetExpression


## -description

The <b>GetOffsetExpression</b>  methods return the expression string that evaluates to the location that triggers a breakpoint.

## -parameters

### -param Buffer 

[out, optional]
The expression string that evaluates to the location on the target that triggers the breakpoint.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
The size, in characters, of the buffer that <i>Buffer </i>points to.

### -param ExpressionSize 

[out, optional]
The size, in characters, of the expression string.  If <i>ExpressionSize</i> is <b>NULL</b>, this information is not returned.

## -returns

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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the expression string and so the string was truncated to fit.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The expression is evaluated every time that a module is loaded or unloaded.  If the debugger cannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.)

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the size of the expression string that specifies the location that triggers the breakpoint, <i>ExpressionSize</i>.

For more information about how to use breakpoints, see <a href="/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.
