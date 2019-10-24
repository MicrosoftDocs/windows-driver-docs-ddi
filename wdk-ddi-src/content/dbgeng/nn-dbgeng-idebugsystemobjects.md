---
UID: NN:dbgeng.IDebugSystemObjects
title: IDebugSystemObjects (dbgeng.h)
description: IDebugSystemObjects interface
old-location: debugger\idebugsystemobjects.htm
tech.root: debugger
ms.assetid: ed830f09-10c0-4614-b002-8ede0e5e30bb
ms.date: 05/03/2018
ms.keywords: IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], IDebugSystemObjects interface [Windows Debugging],described, IDebugSystemObjects_82c2f1f3-4eb4-4071-ba0b-d2e4d2929ce2.xml, dbgeng/IDebugSystemObjects, debugger.idebugsystemobjects
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugSystemObjects"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- IDebugSystemObjects
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSystemObjects</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugSystemObjects</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSystemObjects</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocessdataoffset">GetCurrentProcessDataOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the system data structure describing the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocessexecutablename">GetCurrentProcessExecutableName</a>
</td>
<td align="left" width="63%">
Returns the name of executable file loaded in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects-getcurrentprocesshandle">GetCurrentProcessHandle</a>
</td>
<td align="left" width="63%">
Returns the system handle for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocessid">GetCurrentProcessId</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocesspeb">GetCurrentProcessPeb</a>
</td>
<td align="left" width="63%">
Returns the process environment block (PEB) of the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocesssystemid">GetCurrentProcessSystemId</a>
</td>
<td align="left" width="63%">
Returns the system process ID of the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentthreaddataoffset">GetCurrentThreadDataOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the system data structure for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentthreadhandle">GetCurrentThreadHandle</a>
</td>
<td align="left" width="63%">
Returns the system handle for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentthreadid">GetCurrentThreadId</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentthreadsystemid">GetCurrentThreadSystemId</a>
</td>
<td align="left" width="63%">
Returns the system thread ID of the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentthreadteb">GetCurrentThreadTeb</a>
</td>
<td align="left" width="63%">
Returns the location of the thread environment block (TEB) for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-geteventprocess">GetEventProcess</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the process on which the last event occurred.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-geteventthread">GetEventThread</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the thread on which the last event occurred.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getnumberprocesses">GetNumberProcesses</a>
</td>
<td align="left" width="63%">
Returns the number of processes for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getnumberthreads">GetNumberThreads</a>
</td>
<td align="left" width="63%">
Returns the number of threads in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getprocessidbydataoffset">GetProcessIdByDataOffset</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getprocessidbyhandle">GetProcessIdByHandle</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getprocessidbypeb">GetProcessIdByPeb</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getprocessidbysystemid">GetProcessIdBySystemId</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for a process specified by its system process ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getprocessidsbyindex">GetProcessIdsByIndex</a>
</td>
<td align="left" width="63%">
Returns the engine process ID and system process ID for the specified processes in the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidbydataoffset">GetThreadIdByDataOffset</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidbyhandle">GetThreadIdByHandle</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidbyprocessor">GetThreadIdByProcessor</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidbysystemid">GetThreadIdBySystemId</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidbyteb">GetThreadIdByTeb</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID of the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getthreadidsbyindex">GetThreadIdsByIndex</a>
</td>
<td align="left" width="63%">
Returns the engine and system thread IDs for the specified threads in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-gettotalnumberthreads">GetTotalNumberThreads</a>
</td>
<td align="left" width="63%">
Returns the total number of threads for all the processes in the current target, in addition to the largest number of threads in any process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-setcurrentprocessid">SetCurrentProcessId</a>
</td>
<td align="left" width="63%">
Makes the specified process the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-setcurrentthreadid">SetCurrentThreadId</a>
</td>
<td align="left" width="63%">
Makes the specified thread the current thread.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects2">IDebugSystemObjects2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>
 

 

