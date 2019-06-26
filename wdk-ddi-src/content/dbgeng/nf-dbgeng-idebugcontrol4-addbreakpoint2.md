---
UID: NF:dbgeng.IDebugControl4.AddBreakpoint2
title: IDebugControl4::AddBreakpoint2 (dbgeng.h)
description: The AddBreakpoint2 method creates a new breakpoint for the current target.
old-location: debugger\addbreakpoint2.htm
tech.root: debugger
ms.assetid: 001a64dd-1470-42e0-98ba-22ba33f3fa69
ms.date: 05/03/2018
ms.keywords: AddBreakpoint2, AddBreakpoint2 method [Windows Debugging], AddBreakpoint2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],AddBreakpoint2 method, IDebugControl4.AddBreakpoint2, IDebugControl4::AddBreakpoint2, dbgeng/IDebugControl4::AddBreakpoint2, debugger.addbreakpoint2
ms.topic: method
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
- Dbgeng.h
api_name:
- IDebugControl4.AddBreakpoint2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::AddBreakpoint2


## -description


The <b>AddBreakpoint2</b>  method creates a new breakpoint for the current target.


## -parameters




### -param Type [in]

Specifies the breakpoint type of the new breakpoint.  This can be either of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/s">software breakpoint</a>

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/p">processor breakpoint</a>

</td>
</tr>
</table>
 


### -param DesiredId [in]

Specifies the desired ID of the new breakpoint.  If it is DEBUG_ANY_ID, the engine will pick an unused ID.


### -param Bp [out]

Receives an interface pointer to the new breakpoint.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint couldn't be created with the desired ID or the value of <i>Type</i> was not recognized.

</td>
</tr>
</table>
 

This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



If <i>DesiredId</i> is not DEBUG_ANY_ID and another breakpoint already uses the ID <i>DesiredId</i>, these methods will fail.

Breakpoints are created empty and disabled.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a> for details on configuring and enabling the breakpoint.

The client is saved as the adder of the new breakpoint. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugbreakpoint2-getadder">GetAdder</a>. 

<div class="alert"><b>Note</b>    Even though <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a> is called.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/breakpoints3">Breakpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>
 

 

