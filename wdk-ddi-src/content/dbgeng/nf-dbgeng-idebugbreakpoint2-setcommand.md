---
UID: NF:dbgeng.IDebugBreakpoint2.SetCommand
title: IDebugBreakpoint2::SetCommand (dbgeng.h)
description: The SetCommand method sets the command that is executed when a breakpoint is triggered.
old-location: debugger\setcommand.htm
tech.root: debugger
ms.assetid: 0c9db77e-6e5d-45cd-a52c-dcc3acf5cba0
ms.date: 05/03/2018
ms.keywords: ComOther_166ee15d-c9e1-466f-9337-a6d20e9355ee.xml, IDebugBreakpoint interface [Windows Debugging],SetCommand method, IDebugBreakpoint2 interface [Windows Debugging],SetCommand method, IDebugBreakpoint2.SetCommand, IDebugBreakpoint2::SetCommand, IDebugBreakpoint::SetCommand, SetCommand, SetCommand method [Windows Debugging], SetCommand method [Windows Debugging],IDebugBreakpoint interface, SetCommand method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetCommand, dbgeng/IDebugBreakpoint::SetCommand, debugger.setcommand
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugBreakpoint.SetCommand"
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
- IDebugBreakpoint.SetCommand
- IDebugBreakpoint2.SetCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::SetCommand


## -description


The <b>SetCommand</b>  method sets the command that is executed when a breakpoint is triggered.


## -parameters




### -param Command [in]

The command string that is executed when the breakpoint is triggered.


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



The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

If the command string includes an execution command such as <b>G (Go)</b>, this command should be the last command in the <i>Command</i> string.  If a command causes the target to resume execution, the rest of the command string is ignored.

For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



