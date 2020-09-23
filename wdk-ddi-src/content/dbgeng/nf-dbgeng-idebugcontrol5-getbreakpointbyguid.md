---
UID: NF:dbgeng.IDebugControl5.GetBreakpointByGuid
title: IDebugControl5::GetBreakpointByGuid (dbgeng.h)
description: The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.
old-location: debugger\idebugcontrol5_getbreakpointbyguid.htm
tech.root: debugger
ms.assetid: AC316591-CCF9-4040-B1A3-29AB2033B673
ms.date: 05/03/2018
keywords: ["IDebugControl5::GetBreakpointByGuid"]
ms.keywords: GetBreakpointByGuid, GetBreakpointByGuid method [Windows Debugging], GetBreakpointByGuid method [Windows Debugging],IDebugControl5 interface, IDebugControl5 interface [Windows Debugging],GetBreakpointByGuid method, IDebugControl5.GetBreakpointByGuid, IDebugControl5::GetBreakpointByGuid, dbgeng/IDebugControl5::GetBreakpointByGuid, debugger.idebugcontrol5_getbreakpointbyguid
req.header: dbgeng.h
req.include-header: 
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
 - IDebugControl5::GetBreakpointByGuid
 - dbgeng/IDebugControl5::GetBreakpointByGuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl5.GetBreakpointByGuid
---

# IDebugControl5::GetBreakpointByGuid


## -description

The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.

## -parameters

### -param Guid 

[in]
Specifies the breakpoint GUID of the breakpoint to return.

### -param Bp 

[out]
Receives the breakpoint.

## -returns

This method can also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No breakpoint was found with the given GUID, or the breakpoint with the specified GUID does not belong to the current process, or the breakpoint with the given GUID is private (see <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getflags">GetFlags</a>). 

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol5">IDebugControl5</a>