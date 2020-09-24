---
UID: NF:dbgeng.IDebugControl2.AddBreakpoint
title: IDebugControl2::AddBreakpoint (dbgeng.h)
description: The AddBreakpoint method creates a new breakpoint for the current target.
old-location: debugger\addbreakpoint.htm
tech.root: debugger
ms.assetid: 08452b54-158f-4dca-86d8-34cc3f96bc62
ms.date: 05/03/2018
keywords: ["IDebugControl2::AddBreakpoint"]
ms.keywords: AddBreakpoint, AddBreakpoint method [Windows Debugging], AddBreakpoint method [Windows Debugging],IDebugControl interface, AddBreakpoint method [Windows Debugging],IDebugControl2 interface, AddBreakpoint method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],AddBreakpoint method, IDebugControl2 interface [Windows Debugging],AddBreakpoint method, IDebugControl2.AddBreakpoint, IDebugControl2::AddBreakpoint, IDebugControl3 interface [Windows Debugging],AddBreakpoint method, IDebugControl3::AddBreakpoint, IDebugControl::AddBreakpoint, IDebugControl_3d11665a-ec78-4742-8195-2798601814e9.xml, dbgeng/IDebugControl2::AddBreakpoint, dbgeng/IDebugControl3::AddBreakpoint, dbgeng/IDebugControl::AddBreakpoint, debugger.addbreakpoint
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
 - IDebugControl2::AddBreakpoint
 - dbgeng/IDebugControl2::AddBreakpoint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl.AddBreakpoint
 - IDebugControl2.AddBreakpoint
 - IDebugControl3.AddBreakpoint
---

# IDebugControl2::AddBreakpoint


## -description

The <b>AddBreakpoint</b>  method creates a new breakpoint for the current target.

## -parameters

### -param Type 

[in]
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
<a href="/windows-hardware/drivers/debugger/s">software breakpoint</a>

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
<a href="/windows-hardware/drivers/debugger/p">processor breakpoint</a>

</td>
</tr>
</table>

### -param DesiredId 

[in]
Specifies the desired ID of the new breakpoint.  If it is DEBUG_ANY_ID, the engine will pick an unused ID.

### -param Bp 

[out]
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
 

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If <i>DesiredId</i> is not DEBUG_ANY_ID and another breakpoint already uses the ID <i>DesiredId</i>, these methods will fail.

Breakpoints are created empty and disabled.  See <a href="/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a> for details on configuring and enabling the breakpoint.

The client is saved as the adder of the new breakpoint. See <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getadder">GetAdder</a>. 

<div class="alert"><b>Note</b>    Even though <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> extends the COM interface <b>IUnknown</b>, the lifetime of the breakpoint is not controlled using the <b>IUnknown</b> interface.  Instead, the breakpoint is deleted after <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a> is called.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/debugger/breakpoints3">Breakpoints</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a>



<a href="/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>