---
UID: NF:dbgeng.IDebugControl3.SetExecutionStatus
title: IDebugControl3::SetExecutionStatus (dbgeng.h)
description: The SetExecutionStatus method requests that the debugger engine enter an executable state. Actual execution will not occur until the next time WaitForEvent is called.
old-location: debugger\setexecutionstatus.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl3::SetExecutionStatus"]
ms.keywords: IDebugControl interface [Windows Debugging],SetExecutionStatus method, IDebugControl2 interface [Windows Debugging],SetExecutionStatus method, IDebugControl2::SetExecutionStatus, IDebugControl3 interface [Windows Debugging],SetExecutionStatus method, IDebugControl3.SetExecutionStatus, IDebugControl3::SetExecutionStatus, IDebugControl::SetExecutionStatus, IDebugControl_b89bf576-8a07-49a8-8373-0b915300d36a.xml, SetExecutionStatus, SetExecutionStatus method [Windows Debugging], SetExecutionStatus method [Windows Debugging],IDebugControl interface, SetExecutionStatus method [Windows Debugging],IDebugControl2 interface, SetExecutionStatus method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetExecutionStatus, dbgeng/IDebugControl3::SetExecutionStatus, dbgeng/IDebugControl::SetExecutionStatus, debugger.setexecutionstatus
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
 - IDebugControl3::SetExecutionStatus
 - dbgeng/IDebugControl3::SetExecutionStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.SetExecutionStatus
 - IDebugControl2.SetExecutionStatus
 - IDebugControl3.SetExecutionStatus
---

# IDebugControl3::SetExecutionStatus


## -description

The <b>SetExecutionStatus</b> method requests that the debugger engine enter an executable state.  Actual execution will not occur until the next time <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> is called.

## -parameters

### -param Status 

[in]
Specifies the mode for the engine to use when executing.  Possible values are those values in the table in <a href="/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> whose precedence lies between DEBUG_STATUS_GO and DEBUG_STATUS_STEP_INTO.

## -returns

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
Something prevented the execution of this method. Possible causes include: there is no current target, there is an outstanding request for input, or execution is not supported in the current target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_ACCESSDENIED</b></dt>
</dl>
</td>
<td width="60%">
The target is already executing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No target can generate any more events.

</td>
</tr>
</table>

## -remarks

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getexecutionstatus">GetExecutionStatus</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
