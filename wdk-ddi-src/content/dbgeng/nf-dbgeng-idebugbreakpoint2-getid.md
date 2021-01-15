---
UID: NF:dbgeng.IDebugBreakpoint2.GetId
title: IDebugBreakpoint2::GetId (dbgeng.h)
description: The GetId method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.
old-location: debugger\getid.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetId"]
ms.keywords: ComOther_408e8e80-f34e-4895-9bae-66dbb0f9aa97.xml, GetId, GetId method [Windows Debugging], GetId method [Windows Debugging],IDebugBreakpoint interface, GetId method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetId method, IDebugBreakpoint2 interface [Windows Debugging],GetId method, IDebugBreakpoint2.GetId, IDebugBreakpoint2::GetId, IDebugBreakpoint::GetId, dbgeng/IDebugBreakpoint2::GetId, dbgeng/IDebugBreakpoint::GetId, debugger.getid
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
 - IDebugBreakpoint2::GetId
 - dbgeng/IDebugBreakpoint2::GetId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint2::GetId
---

# IDebugBreakpoint2::GetId


## -description

The <b>GetId</b> method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.

## -parameters

### -param Id 

[out]
The breakpoint ID.

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
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The breakpoint ID remains fixed as long as the breakpoint exists.  However, after the breakpoint has been removed, you can use its ID for another breakpoint.

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the breakpoint ID.

For more information about how to use breakpoints, see <a href="/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.

