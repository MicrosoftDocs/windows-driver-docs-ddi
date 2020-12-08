---
UID: NF:dbgeng.IDebugSystemObjects4.GetThreadIdByHandle
title: IDebugSystemObjects4::GetThreadIdByHandle (dbgeng.h)
description: The GetThreadIdByHandle method returns the engine thread ID for the specified thread. The thread is specified by its system handle.
old-location: debugger\getthreadidbyhandle.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetThreadIdByHandle"]
ms.keywords: GetThreadIdByHandle, GetThreadIdByHandle method [Windows Debugging], GetThreadIdByHandle method [Windows Debugging],IDebugSystemObjects interface, GetThreadIdByHandle method [Windows Debugging],IDebugSystemObjects2 interface, GetThreadIdByHandle method [Windows Debugging],IDebugSystemObjects3 interface, GetThreadIdByHandle method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetThreadIdByHandle method, IDebugSystemObjects2 interface [Windows Debugging],GetThreadIdByHandle method, IDebugSystemObjects2::GetThreadIdByHandle, IDebugSystemObjects3 interface [Windows Debugging],GetThreadIdByHandle method, IDebugSystemObjects3::GetThreadIdByHandle, IDebugSystemObjects4 interface [Windows Debugging],GetThreadIdByHandle method, IDebugSystemObjects4.GetThreadIdByHandle, IDebugSystemObjects4::GetThreadIdByHandle, IDebugSystemObjects::GetThreadIdByHandle, IDebugSystemObjects_d1cb023a-dd00-42bf-9827-e2ee98878964.xml, dbgeng/IDebugSystemObjects2::GetThreadIdByHandle, dbgeng/IDebugSystemObjects3::GetThreadIdByHandle, dbgeng/IDebugSystemObjects4::GetThreadIdByHandle, dbgeng/IDebugSystemObjects::GetThreadIdByHandle, debugger.getthreadidbyhandle
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
 - IDebugSystemObjects4::GetThreadIdByHandle
 - dbgeng/IDebugSystemObjects4::GetThreadIdByHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetThreadIdByHandle
 - IDebugSystemObjects2.GetThreadIdByHandle
 - IDebugSystemObjects3.GetThreadIdByHandle
 - IDebugSystemObjects4.GetThreadIdByHandle
---

# IDebugSystemObjects4::GetThreadIdByHandle


## -description

The <b>GetThreadIdByHandle</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system handle.

## -parameters

### -param Handle 

[in]
Specifies the system handle of the thread whose thread ID is requested.

### -param Id 

[out]
Receives the engine thread ID.

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

In kernel-mode debugging, because the handle is an artificial handle for a processor,  this method returns the engine thread ID for the virtual thread representing that processor.

For more information about threads, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on system handles, see <a href="/windows-hardware/drivers/">Handles</a>.
