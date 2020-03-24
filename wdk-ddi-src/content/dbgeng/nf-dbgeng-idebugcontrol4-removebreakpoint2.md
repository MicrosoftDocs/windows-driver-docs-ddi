---
UID: NF:dbgeng.IDebugControl4.RemoveBreakpoint2
title: IDebugControl4::RemoveBreakpoint2 (dbgeng.h)
description: The RemoveBreakpoint2 method removes a breakpoint.
old-location: debugger\removebreakpoint2.htm
tech.root: debugger
ms.assetid: e1c77758-0249-4ec6-9244-329c0b823e44
ms.date: 05/03/2018
keywords: ["IDebugControl4::RemoveBreakpoint2"]
ms.keywords: IDebugControl4 interface [Windows Debugging],RemoveBreakpoint2 method, IDebugControl4.RemoveBreakpoint2, IDebugControl4::RemoveBreakpoint2, RemoveBreakpoint2, RemoveBreakpoint2 method [Windows Debugging], RemoveBreakpoint2 method [Windows Debugging],IDebugControl4 interface, dbgeng/IDebugControl4::RemoveBreakpoint2, debugger.removebreakpoint2
f1_keywords:
 - "dbgeng/IDebugControl4.RemoveBreakpoint2"
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
- IDebugControl4.RemoveBreakpoint2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::RemoveBreakpoint2


## -description


The <b>RemoveBreakpoint2</b>  method removes a breakpoint.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

