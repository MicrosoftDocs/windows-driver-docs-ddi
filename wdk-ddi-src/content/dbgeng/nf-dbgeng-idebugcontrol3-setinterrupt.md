---
UID: NF:dbgeng.IDebugControl3.SetInterrupt
title: IDebugControl3::SetInterrupt (dbgeng.h)
description: The SetInterrupt method registers a user interrupt or breaks into the debugger.
old-location: debugger\setinterrupt.htm
tech.root: debugger
ms.assetid: d67119c7-ecbe-446c-8a4f-38d33e92a277
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetInterrupt method, IDebugControl2 interface [Windows Debugging],SetInterrupt method, IDebugControl2::SetInterrupt, IDebugControl3 interface [Windows Debugging],SetInterrupt method, IDebugControl3.SetInterrupt, IDebugControl3::SetInterrupt, IDebugControl::SetInterrupt, IDebugControl_dd73562c-6f15-4101-8ab3-3f432de5a002.xml, SetInterrupt, SetInterrupt method [Windows Debugging], SetInterrupt method [Windows Debugging],IDebugControl interface, SetInterrupt method [Windows Debugging],IDebugControl2 interface, SetInterrupt method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetInterrupt, dbgeng/IDebugControl3::SetInterrupt, dbgeng/IDebugControl::SetInterrupt, debugger.setinterrupt
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
- dbgeng.h
api_name:
- IDebugControl.SetInterrupt
- IDebugControl2.SetInterrupt
- IDebugControl3.SetInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetInterrupt


## -description


The <b>SetInterrupt</b> method registers a user interrupt or breaks into the debugger.


## -parameters




### -param Flags [in]

Specifies the type of interrupt to register.  <i>Flags</i> can take one of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_ACTIVE

</td>
<td>
If the target is running, the engine will request a break into the debugger.  This request might time out. For more information, see the "Remarks" section.

Otherwise, when the target is suspended, the engine will register a user interrupt.

</td>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_PASSIVE

</td>
<td>
The engine will register a user interrupt.

</td>
</tr>
<tr>
<td>
DEBUG_INTERRUPT_EXIT

</td>
<td>
If there is currently a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> call running, the engine will force it to return.  If there are any debugger commands causing execution in the target -- for example, <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/g--go-">g (Go)</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/p--step-">p (Step)</a> -- the engine will force them to complete.  This does not force a break into the debugger, so the target might not be suspended. In which case, the <b>WaitForEvent</b> call will return E_PENDING.

Otherwise, when the target is suspended, register a user interrupt.

</td>
</tr>
</table>
 


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



This method can be called at any time and from any thread.  Once the interrupt has been registered, this method returns immediately.

If <i>Flags</i> is DEBUG_INTERRUPT_ACTIVE, and the interrupt times out, the engine will generate a synthetic exception event.  This event will be sent to event callback's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exception">IDebugEventCallbacks::Exception</a> method.  The amount of time before the interrupt times out can be set using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupttimeout">SetInterruptTimeout</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getinterrupt">GetInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getinterrupttimeout">GetInterruptTimeout</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupttimeout">SetInterruptTimeout</a>
 

 

