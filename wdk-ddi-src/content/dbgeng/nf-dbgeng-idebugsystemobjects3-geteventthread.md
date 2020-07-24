---
UID: NF:dbgeng.IDebugSystemObjects3.GetEventThread
title: IDebugSystemObjects3::GetEventThread (dbgeng.h)
description: The GetEventThread method returns the engine thread ID for the thread on which the last event occurred.
old-location: debugger\geteventthread.htm
tech.root: debugger
ms.assetid: 7a28c9bd-480e-4864-b7ff-9ff0dc1d04ad
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetEventThread"]
ms.keywords: GetEventThread, GetEventThread method [Windows Debugging], GetEventThread method [Windows Debugging],IDebugSystemObjects interface, GetEventThread method [Windows Debugging],IDebugSystemObjects2 interface, GetEventThread method [Windows Debugging],IDebugSystemObjects3 interface, GetEventThread method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetEventThread method, IDebugSystemObjects2 interface [Windows Debugging],GetEventThread method, IDebugSystemObjects2::GetEventThread, IDebugSystemObjects3 interface [Windows Debugging],GetEventThread method, IDebugSystemObjects3.GetEventThread, IDebugSystemObjects3::GetEventThread, IDebugSystemObjects4 interface [Windows Debugging],GetEventThread method, IDebugSystemObjects4::GetEventThread, IDebugSystemObjects::GetEventThread, IDebugSystemObjects_2074b9ad-a761-42fd-93ed-4774c2ddf3a5.xml, dbgeng/IDebugSystemObjects2::GetEventThread, dbgeng/IDebugSystemObjects3::GetEventThread, dbgeng/IDebugSystemObjects4::GetEventThread, dbgeng/IDebugSystemObjects::GetEventThread, debugger.geteventthread
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetEventThread"
 - "IDebugSystemObjects.GetEventThread"
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
- IDebugSystemObjects.GetEventThread
- IDebugSystemObjects2.GetEventThread
- IDebugSystemObjects3.GetEventThread
- IDebugSystemObjects4.GetEventThread
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetEventThread


## -description


The <b>GetEventThread</b> method returns the engine thread ID for the thread on which the last event occurred.


## -parameters




### -param Id [out]

Receives the engine thread ID.


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



In kernel-mode debugging, the engine thread ID for the virtual thread representing the processor on which the event occurred is returned.

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details about debugger engine events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.



