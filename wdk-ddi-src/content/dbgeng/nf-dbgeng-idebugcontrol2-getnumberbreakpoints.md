---
UID: NF:dbgeng.IDebugControl2.GetNumberBreakpoints
title: IDebugControl2::GetNumberBreakpoints (dbgeng.h)
description: The GetNumberBreakpoints method returns the number of breakpoints for the current process.
old-location: debugger\getnumberbreakpoints.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetNumberBreakpoints"]
ms.keywords: GetNumberBreakpoints, GetNumberBreakpoints method [Windows Debugging], GetNumberBreakpoints method [Windows Debugging],IDebugControl interface, GetNumberBreakpoints method [Windows Debugging],IDebugControl2 interface, GetNumberBreakpoints method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNumberBreakpoints method, IDebugControl2 interface [Windows Debugging],GetNumberBreakpoints method, IDebugControl2.GetNumberBreakpoints, IDebugControl2::GetNumberBreakpoints, IDebugControl3 interface [Windows Debugging],GetNumberBreakpoints method, IDebugControl3::GetNumberBreakpoints, IDebugControl::GetNumberBreakpoints, IDebugControl_c5b9bf83-0a0e-4570-8a05-04ca39a4d335.xml, dbgeng/IDebugControl2::GetNumberBreakpoints, dbgeng/IDebugControl3::GetNumberBreakpoints, dbgeng/IDebugControl::GetNumberBreakpoints, debugger.getnumberbreakpoints
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
 - IDebugControl2::GetNumberBreakpoints
 - dbgeng/IDebugControl2::GetNumberBreakpoints
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetNumberBreakpoints
---

# IDebugControl2::GetNumberBreakpoints


## -description

The <b>GetNumberBreakpoints</b> method returns the number of <a href="/windows-hardware/drivers/debugger/breakpoints3">breakpoints</a> for the current process.

## -parameters

### -param Number 

[out]
Receives the number of breakpoints.

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
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addbreakpoint">AddBreakpoint</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a>

