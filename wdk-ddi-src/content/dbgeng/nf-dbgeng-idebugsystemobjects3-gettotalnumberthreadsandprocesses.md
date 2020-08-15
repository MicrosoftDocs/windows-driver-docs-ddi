---
UID: NF:dbgeng.IDebugSystemObjects3.GetTotalNumberThreadsAndProcesses
title: IDebugSystemObjects3::GetTotalNumberThreadsAndProcesses (dbgeng.h)
description: The GetTotalNumberThreadsAndProcesses method returns the total number of threads and processes in all the targets the engine is attached to, in addition to the largest number of threads and processes in a target.
old-location: debugger\gettotalnumberthreadsandprocesses.htm
tech.root: debugger
ms.assetid: 452dc67b-1938-4757-99bd-507a32d9a71a
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetTotalNumberThreadsAndProcesses"]
ms.keywords: GetTotalNumberThreadsAndProcesses, GetTotalNumberThreadsAndProcesses method [Windows Debugging], GetTotalNumberThreadsAndProcesses method [Windows Debugging],IDebugSystemObjects3 interface, GetTotalNumberThreadsAndProcesses method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetTotalNumberThreadsAndProcesses method, IDebugSystemObjects3.GetTotalNumberThreadsAndProcesses, IDebugSystemObjects3::GetTotalNumberThreadsAndProcesses, IDebugSystemObjects4 interface [Windows Debugging],GetTotalNumberThreadsAndProcesses method, IDebugSystemObjects4::GetTotalNumberThreadsAndProcesses, IDebugSystemObjects_503ce0cc-8781-4a45-aa59-727b41aaf23b.xml, dbgeng/IDebugSystemObjects3::GetTotalNumberThreadsAndProcesses, dbgeng/IDebugSystemObjects4::GetTotalNumberThreadsAndProcesses, debugger.gettotalnumberthreadsandprocesses
f1_keywords:
 - "dbgeng/IDebugSystemObjects3.GetTotalNumberThreadsAndProcesses"
 - "IDebugSystemObjects3.GetTotalNumberThreadsAndProcesses"
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
- IDebugSystemObjects3.GetTotalNumberThreadsAndProcesses
- IDebugSystemObjects4.GetTotalNumberThreadsAndProcesses
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::GetTotalNumberThreadsAndProcesses


## -description


The <b>GetTotalNumberThreadsAndProcesses</b> method returns the total number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">processes</a> in all the targets the engine is attached to, in addition to the largest number of threads and processes in a target.


## -parameters




### -param TotalThreads 
[out]
Receives the total number of threads in all processes in all targets.


### -param TotalProcesses 
[out]
Receives the total number of processes in all targets.


### -param LargestProcessThreads 
[out]
Receives the largest number of threads in any process on any target.


### -param LargestSystemThreads 
[out]
Receives the largest number of threads in any target.


### -param LargestSystemProcesses 
[out]
Receives the largest number of processes in any target.


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



If no target is found, all the values are set to zero.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>
 

 

