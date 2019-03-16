---
UID: NF:dbgeng.IDebugControl3.GetNotifyEventHandle
title: IDebugControl3::GetNotifyEventHandle (dbgeng.h)
description: The GetNotifyEventHandle method receives the handle of the event that will be signaled after the next exception in a target.
old-location: debugger\getnotifyeventhandle.htm
tech.root: debugger
ms.assetid: a949a583-1ee1-4538-9117-4ad1482e8bc8
ms.date: 05/03/2018
ms.keywords: GetNotifyEventHandle, GetNotifyEventHandle method [Windows Debugging], GetNotifyEventHandle method [Windows Debugging],IDebugControl interface, GetNotifyEventHandle method [Windows Debugging],IDebugControl2 interface, GetNotifyEventHandle method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl2 interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl2::GetNotifyEventHandle, IDebugControl3 interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl3.GetNotifyEventHandle, IDebugControl3::GetNotifyEventHandle, IDebugControl::GetNotifyEventHandle, IDebugControl_73931ad2-ace6-4d38-ad22-c322f2e3c13c.xml, dbgeng/IDebugControl2::GetNotifyEventHandle, dbgeng/IDebugControl3::GetNotifyEventHandle, dbgeng/IDebugControl::GetNotifyEventHandle, debugger.getnotifyeventhandle
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
- IDebugControl.GetNotifyEventHandle
- IDebugControl2.GetNotifyEventHandle
- IDebugControl3.GetNotifyEventHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetNotifyEventHandle


## -description


The <b>GetNotifyEventHandle</b> method receives the handle of the event that will be signaled after the next <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a> in a target.


## -parameters




### -param Handle [out]

Receives the handle of the event that will be signaled.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



If an event to be signaled was set and an exception occurs in a target, when the engine resumes execution in the target again, the event will be signaled.

The event will only be signaled once.  After it has been signaled, this method will return <b>NULL</b> to <i>Handle</i>, unless <a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a> is called to set another event to signal. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556739">SetNotifyEventHandle</a>
 

 

