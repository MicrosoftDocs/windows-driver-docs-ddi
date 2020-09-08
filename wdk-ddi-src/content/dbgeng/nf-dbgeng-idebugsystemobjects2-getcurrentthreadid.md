---
UID: NF:dbgeng.IDebugSystemObjects2.GetCurrentThreadId
title: IDebugSystemObjects2::GetCurrentThreadId (dbgeng.h)
description: The GetCurrentThreadId method returns the engine thread ID for the current thread.
old-location: debugger\getcurrentthreadid.htm
tech.root: debugger
ms.assetid: 7062c962-2e82-40e3-81ea-97ac0948e501
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects2::GetCurrentThreadId"]
ms.keywords: GetCurrentThreadId, GetCurrentThreadId method [Windows Debugging], GetCurrentThreadId method [Windows Debugging],IDebugSystemObjects interface, GetCurrentThreadId method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentThreadId method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentThreadId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentThreadId method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentThreadId method, IDebugSystemObjects2.GetCurrentThreadId, IDebugSystemObjects2::GetCurrentThreadId, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentThreadId method, IDebugSystemObjects3::GetCurrentThreadId, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentThreadId method, IDebugSystemObjects4::GetCurrentThreadId, IDebugSystemObjects::GetCurrentThreadId, IDebugSystemObjects_e40e3ab8-b03d-4b1e-805b-ad8ba51ea1c5.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadId, dbgeng/IDebugSystemObjects3::GetCurrentThreadId, dbgeng/IDebugSystemObjects4::GetCurrentThreadId, dbgeng/IDebugSystemObjects::GetCurrentThreadId, debugger.getcurrentthreadid
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
 - IDebugSystemObjects2::GetCurrentThreadId
 - dbgeng/IDebugSystemObjects2::GetCurrentThreadId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetCurrentThreadId
 - IDebugSystemObjects2.GetCurrentThreadId
 - IDebugSystemObjects3.GetCurrentThreadId
 - IDebugSystemObjects4.GetCurrentThreadId
---

# IDebugSystemObjects2::GetCurrentThreadId


## -description

The <b>GetCurrentThreadId</b> method returns the engine thread ID for the current thread.

## -parameters

### -param Id 

[out]
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

For more information about threads, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

