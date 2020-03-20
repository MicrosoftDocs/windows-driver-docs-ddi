---
UID: NF:dbgeng.IDebugControl.SetInterruptTimeout
title: IDebugControl::SetInterruptTimeout (dbgeng.h)
description: The SetInterruptTimeout method sets the number of seconds that the debugger engine should wait when requesting a break into the debugger.
old-location: debugger\setinterrupttimeout.htm
tech.root: debugger
ms.assetid: 93bc2a07-a6f7-45df-945d-81c6c53adb47
ms.date: 05/03/2018
keywords: ["IDebugControl::SetInterruptTimeout"]
ms.keywords: IDebugControl interface [Windows Debugging],SetInterruptTimeout method, IDebugControl.SetInterruptTimeout, IDebugControl2 interface [Windows Debugging],SetInterruptTimeout method, IDebugControl2::SetInterruptTimeout, IDebugControl3 interface [Windows Debugging],SetInterruptTimeout method, IDebugControl3::SetInterruptTimeout, IDebugControl::SetInterruptTimeout, IDebugControl_c16219f4-97b7-451d-8f04-30aa262667f6.xml, SetInterruptTimeout, SetInterruptTimeout method [Windows Debugging], SetInterruptTimeout method [Windows Debugging],IDebugControl interface, SetInterruptTimeout method [Windows Debugging],IDebugControl2 interface, SetInterruptTimeout method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetInterruptTimeout, dbgeng/IDebugControl3::SetInterruptTimeout, dbgeng/IDebugControl::SetInterruptTimeout, debugger.setinterrupttimeout
f1_keywords:
 - "dbgeng/IDebugControl.SetInterruptTimeout"
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
- IDebugControl.SetInterruptTimeout
- IDebugControl2.SetInterruptTimeout
- IDebugControl3.SetInterruptTimeout
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::SetInterruptTimeout


## -description


The <b>SetInterruptTimeout</b> method sets the number of seconds that the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> should wait when requesting a break into the debugger.


## -parameters




### -param Seconds [in]

Specifies the number of seconds that the engine should wait for the target when requesting a break into the debugger.


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



The engine requests a break into the debugger when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupt">SetInterrupt</a> is called with the DEBUG_INTERRUPT_ACTIVE flag.  

If an interrupt times out, the engine will generate a synthetic exception event.  This event will be sent to <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">event callback objects</a>'s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-exception">IDebugEventCallbacks::Exception</a> method.

Most targets do not support interrupt time-outs.  Live user-mode debugging is one of the targets that does support them.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getinterrupttimeout">GetInterruptTimeout</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-exception">IDebugEventCallbacks::Exception</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupt">SetInterrupt</a>
 

 

