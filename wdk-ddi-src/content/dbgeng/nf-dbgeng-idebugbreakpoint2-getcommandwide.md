---
UID: NF:dbgeng.IDebugBreakpoint2.GetCommandWide
title: IDebugBreakpoint2::GetCommandWide (dbgeng.h)
description: The GetCommand method returns the command string that is executed when a breakpoint is triggered.
old-location: debugger\getcommandwide.htm
tech.root: debugger
ms.assetid: 050a4243-6ad8-4aa4-8ffb-40fe9fc07b51
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetCommandWide"]
ms.keywords: GetCommandWide, GetCommandWide method [Windows Debugging], GetCommandWide method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint2 interface [Windows Debugging],GetCommandWide method, IDebugBreakpoint2.GetCommandWide, IDebugBreakpoint2::GetCommandWide, dbgeng/IDebugBreakpoint2::GetCommandWide, debugger.getcommandwide
f1_keywords:
 - "dbgeng/IDebugBreakpoint2.GetCommandWide"
 - "IDebugBreakpoint2.GetCommandWide"
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
- IDebugBreakpoint2.GetCommandWide
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::GetCommandWide


## -description


The <b>GetCommand</b>  method returns the command string that is executed when a breakpoint is triggered.


## -parameters




### -param Buffer 
[out, optional]
The command string that is executed when the breakpoint is triggered.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize 
[in]
The size, in characters, of the buffer that <i>Buffer</i> points to.


### -param CommandSize 
[out, optional]
The size of the command string.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful, but the buffer was not large enough to hold the command string and so the command string was truncated to fit.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the size of the breakpoint's command, <i>CommandSize</i>.

For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



