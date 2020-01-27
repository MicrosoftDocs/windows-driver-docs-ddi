---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadHandle
title: IDebugSystemObjects4::GetCurrentThreadHandle (dbgeng.h)
description: The GetCurrentThreadHandle method returns the system handle for the current thread.
old-location: debugger\getcurrentthreadhandle.htm
tech.root: debugger
ms.assetid: edbda821-8016-48db-a2f5-7f615428da0c
ms.date: 05/03/2018
ms.keywords: GetCurrentThreadHandle, GetCurrentThreadHandle method [Windows Debugging], GetCurrentThreadHandle method [Windows Debugging],IDebugSystemObjects interface, GetCurrentThreadHandle method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentThreadHandle method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentThreadHandle method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentThreadHandle method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentThreadHandle method, IDebugSystemObjects2::GetCurrentThreadHandle, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentThreadHandle method, IDebugSystemObjects3::GetCurrentThreadHandle, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentThreadHandle method, IDebugSystemObjects4.GetCurrentThreadHandle, IDebugSystemObjects4::GetCurrentThreadHandle, IDebugSystemObjects::GetCurrentThreadHandle, IDebugSystemObjects_6c615962-bf20-4cdb-8bab-8afc142e8c65.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects3::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects4::GetCurrentThreadHandle, dbgeng/IDebugSystemObjects::GetCurrentThreadHandle, debugger.getcurrentthreadhandle
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetCurrentThreadHandle"
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
- IDebugSystemObjects.GetCurrentThreadHandle
- IDebugSystemObjects2.GetCurrentThreadHandle
- IDebugSystemObjects3.GetCurrentThreadHandle
- IDebugSystemObjects4.GetCurrentThreadHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects4::GetCurrentThreadHandle


## -description


The <b>GetCurrentThreadHandle</b> method returns the system handle for the current thread.


## -parameters




### -param Handle [out]

Receives the current thread's system handle.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



In kernel-mode debugging, an artificial handle is created because the threads are virtual threads.

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on system handles, see <a href="https://docs.microsoft.com/windows-hardware/drivers/">Handles</a>.



