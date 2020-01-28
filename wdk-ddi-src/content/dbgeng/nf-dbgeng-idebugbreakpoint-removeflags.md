---
UID: NF:dbgeng.IDebugBreakpoint.RemoveFlags
title: IDebugBreakpoint::RemoveFlags (dbgeng.h)
description: The RemoveFlags method removes flags from a breakpoint.
old-location: debugger\removeflags.htm
tech.root: debugger
ms.assetid: 60538544-6baf-4d23-a65f-5c5e82bd6f11
ms.date: 05/03/2018
ms.keywords: ComOther_15793582-5533-4f63-8278-9556b160e6d2.xml, IDebugBreakpoint interface [Windows Debugging],RemoveFlags method, IDebugBreakpoint.RemoveFlags, IDebugBreakpoint2 interface [Windows Debugging],RemoveFlags method, IDebugBreakpoint2::RemoveFlags, IDebugBreakpoint::RemoveFlags, RemoveFlags, RemoveFlags method [Windows Debugging], RemoveFlags method [Windows Debugging],IDebugBreakpoint interface, RemoveFlags method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::RemoveFlags, dbgeng/IDebugBreakpoint::RemoveFlags, debugger.removeflags
f1_keywords:
 - "dbgeng/IDebugBreakpoint.RemoveFlags"
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
- IDebugBreakpoint.RemoveFlags
- IDebugBreakpoint2.RemoveFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::RemoveFlags


## -description


The <b>RemoveFlags</b> method removes flags from a breakpoint.


## -parameters




### -param Flags [in]

Flags to remove from the breakpoint.  <i>Flags</i> is a bit field. The new value of the flags in the engine is the old value and not the value of <i>Flags</i>.  For more information about the flag bit field and an explanation of each flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.  You cannot modify the DEBUG_BREAKPOINT_DEFERRED flag in the engine. This bit in <i>Flags</i> must always be zero.


## -returns



<b>RemoveFlags</b> might return one of the following values:

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



For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



