---
UID: NF:dbgeng.IDebugBreakpoint2.SetOffsetExpression
title: IDebugBreakpoint2::SetOffsetExpression (dbgeng.h)
description: The SetOffsetExpression methods set an expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\setoffsetexpression.htm
tech.root: debugger
ms.assetid: 63cfb3f2-5240-4cb6-9c23-8cdb363f62a8
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::SetOffsetExpression"]
ms.keywords: ComOther_d34036ae-b160-4b24-86d0-ebd2bd8408ea.xml, IDebugBreakpoint interface [Windows Debugging],SetOffsetExpression method, IDebugBreakpoint2 interface [Windows Debugging],SetOffsetExpression method, IDebugBreakpoint2.SetOffsetExpression, IDebugBreakpoint2::SetOffsetExpression, IDebugBreakpoint::SetOffsetExpression, SetOffsetExpression, SetOffsetExpression method [Windows Debugging], SetOffsetExpression method [Windows Debugging],IDebugBreakpoint interface, SetOffsetExpression method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetOffsetExpression, dbgeng/IDebugBreakpoint::SetOffsetExpression, debugger.setoffsetexpression
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
 - IDebugBreakpoint2::SetOffsetExpression
 - dbgeng/IDebugBreakpoint2::SetOffsetExpression
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint.SetOffsetExpression
 - IDebugBreakpoint2.SetOffsetExpression
---

# IDebugBreakpoint2::SetOffsetExpression


## -description

The <b>SetOffsetExpression</b>  methods set an expression string that evaluates to the location that triggers a breakpoint.

## -parameters

### -param Expression 

[in]
The expression string that evaluates to the location on the target that triggers the breakpoint.  If the engine icannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.)  For more information about the expression syntax, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.

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
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

For more information about how to use breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.

