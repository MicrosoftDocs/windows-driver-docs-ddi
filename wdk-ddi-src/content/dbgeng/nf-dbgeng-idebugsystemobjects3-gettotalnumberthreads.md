---
UID: NF:dbgeng.IDebugSystemObjects3.GetTotalNumberThreads
title: IDebugSystemObjects3::GetTotalNumberThreads (dbgeng.h)
description: The GetTotalNumberThreads method returns the total number of threads for all the processes in the current target, in addition to the largest number of threads in any process for the current target.
old-location: debugger\gettotalnumberthreads.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetTotalNumberThreads"]
ms.keywords: GetTotalNumberThreads, GetTotalNumberThreads method [Windows Debugging], GetTotalNumberThreads method [Windows Debugging],IDebugSystemObjects interface, GetTotalNumberThreads method [Windows Debugging],IDebugSystemObjects2 interface, GetTotalNumberThreads method [Windows Debugging],IDebugSystemObjects3 interface, GetTotalNumberThreads method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetTotalNumberThreads method, IDebugSystemObjects2 interface [Windows Debugging],GetTotalNumberThreads method, IDebugSystemObjects2::GetTotalNumberThreads, IDebugSystemObjects3 interface [Windows Debugging],GetTotalNumberThreads method, IDebugSystemObjects3.GetTotalNumberThreads, IDebugSystemObjects3::GetTotalNumberThreads, IDebugSystemObjects4 interface [Windows Debugging],GetTotalNumberThreads method, IDebugSystemObjects4::GetTotalNumberThreads, IDebugSystemObjects::GetTotalNumberThreads, IDebugSystemObjects_fece8f3e-8d85-492a-b1f8-beadc398613e.xml, dbgeng/IDebugSystemObjects2::GetTotalNumberThreads, dbgeng/IDebugSystemObjects3::GetTotalNumberThreads, dbgeng/IDebugSystemObjects4::GetTotalNumberThreads, dbgeng/IDebugSystemObjects::GetTotalNumberThreads, debugger.gettotalnumberthreads
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
 - IDebugSystemObjects3::GetTotalNumberThreads
 - dbgeng/IDebugSystemObjects3::GetTotalNumberThreads
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects3::GetTotalNumberThreads
---

# IDebugSystemObjects3::GetTotalNumberThreads


## -description

The <b>GetTotalNumberThreads</b> method returns the total number of <a href="/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a> for all the <a href="/windows-hardware/drivers/debugger/controlling-threads-and-processes">processes</a> in the current target, in addition to the largest number of threads in any process for the current target.

## -parameters

### -param Total 

[out]
Receives the total number of threads for all the processes in the current target.

### -param LargestProcess 

[out]
Receives the largest number of threads in any process for the current target.

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

For more information about threads, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.

