---
UID: NF:dbgeng.IDebugControl3.GetBreakpointParameters
title: IDebugControl3::GetBreakpointParameters (dbgeng.h)
description: The GetBreakpointParameters method returns the parameters of one or more breakpoints.
old-location: debugger\getbreakpointparameters.htm
tech.root: debugger
ms.assetid: c4426dfa-7c14-4ef0-8660-855ee24ed7fe
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetBreakpointParameters"]
ms.keywords: GetBreakpointParameters, GetBreakpointParameters method [Windows Debugging], GetBreakpointParameters method [Windows Debugging],IDebugControl interface, GetBreakpointParameters method [Windows Debugging],IDebugControl2 interface, GetBreakpointParameters method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetBreakpointParameters method, IDebugControl2 interface [Windows Debugging],GetBreakpointParameters method, IDebugControl2::GetBreakpointParameters, IDebugControl3 interface [Windows Debugging],GetBreakpointParameters method, IDebugControl3.GetBreakpointParameters, IDebugControl3::GetBreakpointParameters, IDebugControl::GetBreakpointParameters, IDebugControl_7b2d9423-82db-4274-a1f7-eebcda92e6c3.xml, dbgeng/IDebugControl2::GetBreakpointParameters, dbgeng/IDebugControl3::GetBreakpointParameters, dbgeng/IDebugControl::GetBreakpointParameters, debugger.getbreakpointparameters
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbgeng.h, Dbgeng.h
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
 - IDebugControl3::GetBreakpointParameters
 - dbgeng/IDebugControl3::GetBreakpointParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetBreakpointParameters
 - IDebugControl2.GetBreakpointParameters
 - IDebugControl3.GetBreakpointParameters
---

# IDebugControl3::GetBreakpointParameters


## -description

The <b>GetBreakpointParameters</b> method returns the parameters of one or more <a href="/windows-hardware/drivers/debugger/breakpoints3">breakpoints</a>.

## -parameters

### -param Count 

[in]
Specifies the number of breakpoints whose parameters are being requested.

### -param Ids 

[in, optional]
Specifies an array containing the IDs of the breakpoints whose parameters are being requested.  The number of items in this array must be equal to the value specified in <i>Count</i>.  If <i>Ids</i> is <b>NULL</b>, <i>Start</i> is used instead.

### -param Start 

[in]
Specifies the beginning index of the breakpoints whose parameters are being requested.  The parameters for breakpoints with indices <i>Start</i> through <i>Start</i> plus <i>Count</i> minus one will be returned.  <i>Start</i> is used only if <i>Ids</i> is <b>NULL</b>.

### -param Params 

[out]
Receives the parameters for the specified breakpoints. The size of this array is equal to the value of <i>Count</i>.  For details on the structure returned, see <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_breakpoint_parameters">DEBUG_BREAKPOINT_PARAMETERS</a>.

## -returns

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful. However, the parameters for some of the breakpoints were not returned.  The parameters that were not returned have their <b>Id</b> field set to DEBUG_ANY_ID.

</td>
</tr>
</table>

## -remarks

Some of the parameters might not be returned.  This happens if either a breakpoint could not be found or a breakpoint is private (see <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getflags">GetFlags</a>).

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getbreakpointbyid">GetBreakpointById</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getbreakpointbyindex">GetBreakpointByIndex</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>