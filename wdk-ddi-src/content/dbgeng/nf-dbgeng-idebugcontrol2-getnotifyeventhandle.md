---
UID: NF:dbgeng.IDebugControl2.GetNotifyEventHandle
title: IDebugControl2::GetNotifyEventHandle (dbgeng.h)
description: The GetNotifyEventHandle method receives the handle of the event that will be signaled after the next exception in a target.
old-location: debugger\getnotifyeventhandle.htm
tech.root: debugger
ms.assetid: a949a583-1ee1-4538-9117-4ad1482e8bc8
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetNotifyEventHandle"]
ms.keywords: GetNotifyEventHandle, GetNotifyEventHandle method [Windows Debugging], GetNotifyEventHandle method [Windows Debugging],IDebugControl interface, GetNotifyEventHandle method [Windows Debugging],IDebugControl2 interface, GetNotifyEventHandle method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl2 interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl2.GetNotifyEventHandle, IDebugControl2::GetNotifyEventHandle, IDebugControl3 interface [Windows Debugging],GetNotifyEventHandle method, IDebugControl3::GetNotifyEventHandle, IDebugControl::GetNotifyEventHandle, IDebugControl_73931ad2-ace6-4d38-ad22-c322f2e3c13c.xml, dbgeng/IDebugControl2::GetNotifyEventHandle, dbgeng/IDebugControl3::GetNotifyEventHandle, dbgeng/IDebugControl::GetNotifyEventHandle, debugger.getnotifyeventhandle
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
 - IDebugControl2::GetNotifyEventHandle
 - dbgeng/IDebugControl2::GetNotifyEventHandle
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
---

# IDebugControl2::GetNotifyEventHandle


## -description

The <b>GetNotifyEventHandle</b> method receives the handle of the event that will be signaled after the next <a href="/windows-hardware/drivers/">exception</a> in a target.

## -parameters

### -param Handle 

[out]
Receives the handle of the event that will be signaled.  If <i>Handle</i> is <b>NULL</b>, no event will be signaled.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The event will only be signaled once.  After it has been signaled, this method will return <b>NULL</b> to <i>Handle</i>, unless <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setnotifyeventhandle">SetNotifyEventHandle</a> is called to set another event to signal.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setnotifyeventhandle">SetNotifyEventHandle</a>