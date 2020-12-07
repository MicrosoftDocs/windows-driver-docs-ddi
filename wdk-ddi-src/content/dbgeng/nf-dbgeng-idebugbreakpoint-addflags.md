---
UID: NF:dbgeng.IDebugBreakpoint.AddFlags
title: IDebugBreakpoint::AddFlags (dbgeng.h)
description: The AddFlags method adds flags to a breakpoint.
old-location: debugger\addflags.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint::AddFlags"]
ms.keywords: AddFlags, AddFlags method [Windows Debugging], AddFlags method [Windows Debugging],IDebugBreakpoint interface, AddFlags method [Windows Debugging],IDebugBreakpoint2 interface, ComOther_2becec27-600b-4d57-93b0-8a794ff2f068.xml, IDebugBreakpoint interface [Windows Debugging],AddFlags method, IDebugBreakpoint.AddFlags, IDebugBreakpoint2 interface [Windows Debugging],AddFlags method, IDebugBreakpoint2::AddFlags, IDebugBreakpoint::AddFlags, dbgeng/IDebugBreakpoint2::AddFlags, dbgeng/IDebugBreakpoint::AddFlags, debugger.addflags
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
 - IDebugBreakpoint::AddFlags
 - dbgeng/IDebugBreakpoint::AddFlags
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugBreakpoint.AddFlags
 - IDebugBreakpoint2.AddFlags
---

# IDebugBreakpoint::AddFlags


## -description

The <b>AddFlags</b> method adds flags to a <a href="/windows-hardware/drivers/debugger/b">breakpoint</a>.

## -parameters

### -param Flags 

[in]
Additional flags to add to the breakpoint.  <i>Flags</i> is a bit field that is combined together with the existing flags by using a bitwise OR.  For more information about the flag bit field and an explanation of each flag, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.  You cannot modify the DEBUG_BREAKPOINT_DEFERRED flag in the <a href="/windows-hardware/drivers/debugger/e">engine</a>. This bit in <i>Flags</i> must always be zero.

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

For more information about breakpoint properties, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.
