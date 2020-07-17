---
UID: NF:dbgeng.IDebugControl2.RemoveBreakpoint
title: IDebugControl2::RemoveBreakpoint (dbgeng.h)
description: The RemoveBreakpoint method removes a breakpoint.
old-location: debugger\removebreakpoint.htm
tech.root: debugger
ms.assetid: ce0f5e42-3f4e-48e1-9e73-96bca96e8e23
ms.date: 05/03/2018
keywords: ["IDebugControl2::RemoveBreakpoint"]
ms.keywords: IDebugControl interface [Windows Debugging],RemoveBreakpoint method, IDebugControl2 interface [Windows Debugging],RemoveBreakpoint method, IDebugControl2.RemoveBreakpoint, IDebugControl2::RemoveBreakpoint, IDebugControl3 interface [Windows Debugging],RemoveBreakpoint method, IDebugControl3::RemoveBreakpoint, IDebugControl::RemoveBreakpoint, IDebugControl_431f31ce-38fb-4350-851b-49b103047943.xml, RemoveBreakpoint, RemoveBreakpoint method [Windows Debugging], RemoveBreakpoint method [Windows Debugging],IDebugControl interface, RemoveBreakpoint method [Windows Debugging],IDebugControl2 interface, RemoveBreakpoint method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::RemoveBreakpoint, dbgeng/IDebugControl3::RemoveBreakpoint, dbgeng/IDebugControl::RemoveBreakpoint, debugger.removebreakpoint
f1_keywords:
 - "dbgeng/IDebugControl.RemoveBreakpoint"
 - "IDebugControl.RemoveBreakpoint"
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
- IDebugControl.RemoveBreakpoint
- IDebugControl2.RemoveBreakpoint
- IDebugControl3.RemoveBreakpoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::RemoveBreakpoint


## -description


The <b>RemoveBreakpoint</b>  method removes a breakpoint.


## -parameters




### -param Bp [in]

Specifies an interface pointer to breakpoint to remove.


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
 

This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



After <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called, the breakpoint object specified in the <i>Bp</i> parameter must not be used again.

<div class="alert"><b>Note</b>    Even though <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <b>RemoveBreakpoint</b> and <b>RemoveBreakpoint2</b> are called.</div>
<div> </div>
For more details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-addbreakpoint">AddBreakpoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

