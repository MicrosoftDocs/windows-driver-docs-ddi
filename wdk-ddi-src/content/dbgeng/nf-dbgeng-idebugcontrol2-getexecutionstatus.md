---
UID: NF:dbgeng.IDebugControl2.GetExecutionStatus
title: IDebugControl2::GetExecutionStatus (dbgeng.h)
description: The GetExecutionStatus method returns information about the execution status of the debugger engine.
old-location: debugger\getexecutionstatus.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetExecutionStatus"]
ms.keywords: GetExecutionStatus, GetExecutionStatus method [Windows Debugging], GetExecutionStatus method [Windows Debugging],IDebugControl interface, GetExecutionStatus method [Windows Debugging],IDebugControl2 interface, GetExecutionStatus method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetExecutionStatus method, IDebugControl2 interface [Windows Debugging],GetExecutionStatus method, IDebugControl2.GetExecutionStatus, IDebugControl2::GetExecutionStatus, IDebugControl3 interface [Windows Debugging],GetExecutionStatus method, IDebugControl3::GetExecutionStatus, IDebugControl::GetExecutionStatus, IDebugControl_0e47a42b-f980-4c4b-b8b3-8d795498e5d5.xml, dbgeng/IDebugControl2::GetExecutionStatus, dbgeng/IDebugControl3::GetExecutionStatus, dbgeng/IDebugControl::GetExecutionStatus, debugger.getexecutionstatus
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
 - IDebugControl2::GetExecutionStatus
 - dbgeng/IDebugControl2::GetExecutionStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetExecutionStatus
---

# IDebugControl2::GetExecutionStatus


## -description

The <b>GetExecutionStatus</b> method returns information about the execution status of the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.

## -parameters

### -param Status 

[out]
Receives the execution status.  This will be set to one of the values in the following table. Note that the description of these values differs slightly from the description in <a href="/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_STATUS_NO_DEBUGGEE

</td>
<td>
The engine is not attached to a target.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_OVER

</td>
<td>
The target is currently executing a single instruction.  If that instruction is a subroutine call, the entire call will be executed.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_INTO

</td>
<td>
The target is currently executing a single instruction.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_STEP_BRANCH

</td>
<td>
The target is currently running until it encounters a branch instruction.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_GO

</td>
<td>
The target is currently running normally.  It will continue normal execution until an event occurs.

</td>
</tr>
<tr>
<td>
DEBUG_STATUS_BREAK

</td>
<td>
The target is not running.

</td>
</tr>
</table>

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setexecutionstatus">SetExecutionStatus</a>

