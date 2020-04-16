---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffsetExpressionWide
title: IDebugBreakpoint2::GetOffsetExpressionWide (dbgeng.h)
description: The GetOffsetExpressionWide method returns the expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\getoffsetexpressionwide.htm
tech.root: debugger
ms.assetid: bd4b32b1-e8ba-485f-bfb6-15c8c44926af
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetOffsetExpressionWide"]
ms.keywords: GetOffsetExpressionWide, GetOffsetExpressionWide method [Windows Debugging], GetOffsetExpressionWide method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint2 interface [Windows Debugging],GetOffsetExpressionWide method, IDebugBreakpoint2.GetOffsetExpressionWide, IDebugBreakpoint2::GetOffsetExpressionWide, dbgeng/IDebugBreakpoint2::GetOffsetExpressionWide, debugger.getoffsetexpressionwide
f1_keywords:
 - "dbgeng/IDebugBreakpoint2.GetOffsetExpressionWide"
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
- IDebugBreakpoint2.GetOffsetExpressionWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::GetOffsetExpressionWide


## -description


The <b>GetOffsetExpressionWide</b> method returns the expression string that evaluates to the location that triggers a breakpoint.


## -parameters




### -param Buffer [out, optional]

The expression string that evaluates to the location on the target that triggers the breakpoint.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size, in characters, of the buffer that <i>Buffer </i>points to.


### -param ExpressionSize [out, optional]

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
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



The expression is evaluated every time that a module is loaded or unloaded.  If the debugger cannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.)

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the size of the expression string that specifies the location that triggers the breakpoint, <i>ExpressionSize</i>.

For more information about how to use breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.



