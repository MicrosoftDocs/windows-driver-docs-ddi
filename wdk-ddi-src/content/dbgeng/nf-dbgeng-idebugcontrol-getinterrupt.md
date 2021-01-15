---
UID: NF:dbgeng.IDebugControl.GetInterrupt
title: IDebugControl::GetInterrupt (dbgeng.h)
description: The GetInterrupt method checks whether a user interrupt was issued.
old-location: debugger\getinterrupt.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl::GetInterrupt"]
ms.keywords: GetInterrupt, GetInterrupt method [Windows Debugging], GetInterrupt method [Windows Debugging],IDebugControl interface, GetInterrupt method [Windows Debugging],IDebugControl2 interface, GetInterrupt method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetInterrupt method, IDebugControl.GetInterrupt, IDebugControl2 interface [Windows Debugging],GetInterrupt method, IDebugControl2::GetInterrupt, IDebugControl3 interface [Windows Debugging],GetInterrupt method, IDebugControl3::GetInterrupt, IDebugControl::GetInterrupt, IDebugControl_059bd637-c75b-4b52-a382-c645cb4b25b9.xml, dbgeng/IDebugControl2::GetInterrupt, dbgeng/IDebugControl3::GetInterrupt, dbgeng/IDebugControl::GetInterrupt, debugger.getinterrupt
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
 - IDebugControl::GetInterrupt
 - dbgeng/IDebugControl::GetInterrupt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl::GetInterrupt
---

# IDebugControl::GetInterrupt


## -description

The <b>GetInterrupt</b> method checks whether a user interrupt was issued.

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
The method was successful and an interrupt has been requested.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful and an interrupt was not requested.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If a user interrupt was issued, it is cleared when this method is called.

Examples of user interrupts include pressing Ctrl+C or pressing the <b>Stop</b> button in a debugger.  Calling <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupt">SetInterrupt</a> also causes a user interrupt.

<div class="alert"><b>Note</b>    It is recommended that debugger extensions call <b>GetInterrupt</b> while undertaking long tasks.</div>
<div> </div>
This method can be called at any time and from any thread.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setinterrupt">SetInterrupt</a>

