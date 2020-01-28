---
UID: NF:dbgeng.IDebugControl3.SetNotifyEventHandle
title: IDebugControl3::SetNotifyEventHandle (dbgeng.h)
description: The SetNotifyEventHandle method sets the event that will be signaled after the next exception in a target.
old-location: debugger\setnotifyeventhandle.htm
tech.root: debugger
ms.assetid: 0c0059a7-4b0f-4b74-b543-ad5904d40033
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetNotifyEventHandle method, IDebugControl2 interface [Windows Debugging],SetNotifyEventHandle method, IDebugControl2::SetNotifyEventHandle, IDebugControl3 interface [Windows Debugging],SetNotifyEventHandle method, IDebugControl3.SetNotifyEventHandle, IDebugControl3::SetNotifyEventHandle, IDebugControl::SetNotifyEventHandle, IDebugControl_9934efa7-aed4-4706-8885-71d78f6950a8.xml, SetNotifyEventHandle, SetNotifyEventHandle method [Windows Debugging], SetNotifyEventHandle method [Windows Debugging],IDebugControl interface, SetNotifyEventHandle method [Windows Debugging],IDebugControl2 interface, SetNotifyEventHandle method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetNotifyEventHandle, dbgeng/IDebugControl3::SetNotifyEventHandle, dbgeng/IDebugControl::SetNotifyEventHandle, debugger.setnotifyeventhandle
f1_keywords:
 - "dbgeng/IDebugControl.SetNotifyEventHandle"
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
- IDebugControl.SetNotifyEventHandle
- IDebugControl2.SetNotifyEventHandle
- IDebugControl3.SetNotifyEventHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetNotifyEventHandle


## -description


The <b>SetNotifyEventHandle</b> method sets the event that will be signaled after the next <a href="https://docs.microsoft.com/windows-hardware/drivers/">exception</a> in a target.


## -parameters




### -param Handle [in]

Specifies the handle of the event to signal.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.


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



After setting the event to signal, and after the next exception occurs in a target, when the engine resumes execution in the target, the event will be signaled.

The event will only be signaled once.  After it has been signaled, <b>GetNotifyEventHandle</b> will return <b>NULL</b>, unless this method is called to set another event to signal.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setnotifyeventhandle">SetNotifyEventHandle</a>
 

 

