---
UID: NF:dbgeng.IDebugControl2.OutputCurrentState
title: IDebugControl2::OutputCurrentState (dbgeng.h)
description: The OutputCurrentState method prints the current state of the current target to the debugger console.
old-location: debugger\outputcurrentstate.htm
tech.root: debugger
ms.assetid: 3d176438-5551-48a4-b757-81c14d84c075
ms.date: 05/03/2018
keywords: ["IDebugControl2::OutputCurrentState"]
ms.keywords: IDebugControl interface [Windows Debugging],OutputCurrentState method, IDebugControl2 interface [Windows Debugging],OutputCurrentState method, IDebugControl2.OutputCurrentState, IDebugControl2::OutputCurrentState, IDebugControl3 interface [Windows Debugging],OutputCurrentState method, IDebugControl3::OutputCurrentState, IDebugControl::OutputCurrentState, IDebugControl_1a038e3b-1bf3-47d0-8e40-b2ebc3506308.xml, OutputCurrentState, OutputCurrentState method [Windows Debugging], OutputCurrentState method [Windows Debugging],IDebugControl interface, OutputCurrentState method [Windows Debugging],IDebugControl2 interface, OutputCurrentState method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::OutputCurrentState, dbgeng/IDebugControl3::OutputCurrentState, dbgeng/IDebugControl::OutputCurrentState, debugger.outputcurrentstate
f1_keywords:
 - "dbgeng/IDebugControl.OutputCurrentState"
 - "IDebugControl.OutputCurrentState"
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
- IDebugControl.OutputCurrentState
- IDebugControl2.OutputCurrentState
- IDebugControl3.OutputCurrentState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::OutputCurrentState


## -description


The <b>OutputCurrentState</b> method prints the current state of the current target to the debugger console.


## -parameters




### -param OutputControl [in]

Specifies which clients to send the output to.  For possible values see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-outctl-xxx">DEBUG_OUTCTL_XXX</a>.


### -param Flags [in]

Specifies the bit set that determines the information to print to the debugger console.  <i>Flags</i> can be any combination of values from the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CURRENT_SYMBOL

</td>
<td>
Symbol string for the address of the current instruction.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_DISASM

</td>
<td>
Disassembly of the current instruction.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_REGISTERS

</td>
<td>
Current register values.

</td>
</tr>
<tr>
<td>
DEBUG_CURRENT_SOURCE_LINE

</td>
<td>
File name and line number of the source corresponding to the current instruction.

</td>
</tr>
</table>
 

Alternatively, <i>Flags</i> can be set to DEBUG_CURRENT_DEFAULT.  This value includes all of the above flags.


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
 




## -remarks



Setting the flags contained in <i>Flags</i> merely allows the information to be printed.  The information will not always be printed (for example, it will not be printed if it is not available).

This is the same status information that is printed when breaking into the debugger.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/target-information">Target Information</a>.



