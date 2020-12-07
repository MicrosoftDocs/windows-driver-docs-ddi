---
UID: NF:dbgeng.IDebugSystemObjects2.GetNumberThreads
title: IDebugSystemObjects2::GetNumberThreads (dbgeng.h)
description: The GetNumberThreads method returns the number of threads in the current process.
old-location: debugger\getnumberthreads.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects2::GetNumberThreads"]
ms.keywords: GetNumberThreads, GetNumberThreads method [Windows Debugging], GetNumberThreads method [Windows Debugging],IDebugSystemObjects interface, GetNumberThreads method [Windows Debugging],IDebugSystemObjects2 interface, GetNumberThreads method [Windows Debugging],IDebugSystemObjects3 interface, GetNumberThreads method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetNumberThreads method, IDebugSystemObjects2 interface [Windows Debugging],GetNumberThreads method, IDebugSystemObjects2.GetNumberThreads, IDebugSystemObjects2::GetNumberThreads, IDebugSystemObjects3 interface [Windows Debugging],GetNumberThreads method, IDebugSystemObjects3::GetNumberThreads, IDebugSystemObjects4 interface [Windows Debugging],GetNumberThreads method, IDebugSystemObjects4::GetNumberThreads, IDebugSystemObjects::GetNumberThreads, IDebugSystemObjects_47d86764-4881-4178-97fa-d6c8732dbb1a.xml, dbgeng/IDebugSystemObjects2::GetNumberThreads, dbgeng/IDebugSystemObjects3::GetNumberThreads, dbgeng/IDebugSystemObjects4::GetNumberThreads, dbgeng/IDebugSystemObjects::GetNumberThreads, debugger.getnumberthreads
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
 - IDebugSystemObjects2::GetNumberThreads
 - dbgeng/IDebugSystemObjects2::GetNumberThreads
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetNumberThreads
 - IDebugSystemObjects2.GetNumberThreads
 - IDebugSystemObjects3.GetNumberThreads
 - IDebugSystemObjects4.GetNumberThreads
---

# IDebugSystemObjects2::GetNumberThreads


## -description

The <b>GetNumberThreads</b> method returns the number of <a href="/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a> in the current process.

## -parameters

### -param Number 

[out]
Receives the number of threads in the current process.

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

In kernel-mode debugging, there is a virtual thread representing each processor.

In user-mode debugging, the number of threads changes with the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-createthread">IDebugEventCallbacks::CreateThread</a> and <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-exitthread">IDebugEventCallbacks::ExitThread</a> events.

For more information about threads, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.
