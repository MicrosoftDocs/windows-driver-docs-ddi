---
UID: NN:dbgeng.IDebugSystemObjects
title: IDebugSystemObjects
author: windows-driver-content
description: IDebugSystemObjects interface
old-location: debugger\idebugsystemobjects.htm
old-project: Debugger
ms.assetid: ed830f09-10c0-4614-b002-8ede0e5e30bb
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.idebugsystemobjects, IDebugSystemObjects interface [Windows Debugging], IDebugSystemObjects interface [Windows Debugging], described, IDebugSystemObjects, dbgeng/IDebugSystemObjects, IDebugSystemObjects_82c2f1f3-4eb4-4071-ba0b-d2e4d2929ce2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects interface


## -description




## -members

The <b>IDebugSystemObjects</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545787">GetCurrentProcessDataOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the system data structure describing the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545794">GetCurrentProcessExecutableName</a>
</td>
<td align="left" width="63%">
Returns the name of executable file loaded in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="..\dbgeng\nf-dbgeng-idebugsystemobjects-getcurrentprocesshandle.md">GetCurrentProcessHandle</a>
</td>
<td align="left" width="63%">
Returns the system handle for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545836">GetCurrentProcessId</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545839">GetCurrentProcessPeb</a>
</td>
<td align="left" width="63%">
Returns the process environment block (PEB) of the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545850">GetCurrentProcessSystemId</a>
</td>
<td align="left" width="63%">
Returns the system process ID of the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545894">GetCurrentThreadDataOffset</a>
</td>
<td align="left" width="63%">
Returns the location of the system data structure for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545904">GetCurrentThreadHandle</a>
</td>
<td align="left" width="63%">
Returns the system handle for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546542">GetCurrentThreadId</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546544">GetCurrentThreadSystemId</a>
</td>
<td align="left" width="63%">
Returns the system thread ID of the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546549">GetCurrentThreadTeb</a>
</td>
<td align="left" width="63%">
Returns the location of the thread environment block (TEB) for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546640">GetEventProcess</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the process on which the last event occurred.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546646">GetEventThread</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the thread on which the last event occurred.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547946">GetNumberProcesses</a>
</td>
<td align="left" width="63%">
Returns the number of processes for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547992">GetNumberThreads</a>
</td>
<td align="left" width="63%">
Returns the number of threads in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548140">GetProcessIdByDataOffset</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548147">GetProcessIdByHandle</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548150">GetProcessIdByPeb</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for the specified process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548155">GetProcessIdBySystemId</a>
</td>
<td align="left" width="63%">
Returns the engine process ID for a process specified by its system process ID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548160">GetProcessIdsByIndex</a>
</td>
<td align="left" width="63%">
Returns the engine process ID and system process ID for the specified processes in the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549302">GetThreadIdByDataOffset</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549312">GetThreadIdByHandle</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549319">GetThreadIdByProcessor</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549329">GetThreadIdBySystemId</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID for the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549336">GetThreadIdByTeb</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID of the specified thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549339">GetThreadIdsByIndex</a>
</td>
<td align="left" width="63%">
Returns the engine and system thread IDs for the specified threads in the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549356">GetTotalNumberThreads</a>
</td>
<td align="left" width="63%">
Returns the total number of threads for all the processes in the current target, in addition to the largest number of threads in any process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556645">SetCurrentProcessId</a>
</td>
<td align="left" width="63%">
Makes the specified process the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556650">SetCurrentThreadId</a>
</td>
<td align="left" width="63%">
Makes the specified thread the current thread.

</td>
</tr>
</table>Returns the location of the system data structure describing the current process.

Returns the name of executable file loaded in the current process.

Returns the system handle for the current process.

Returns the engine process ID for the current process.

Returns the process environment block (PEB) of the current process.

Returns the system process ID of the current process.

Returns the location of the system data structure for the current thread.

Returns the system handle for the current thread.

Returns the engine thread ID for the current thread.

Returns the system thread ID of the current thread.

Returns the location of the thread environment block (TEB) for the current thread.

Returns the engine process ID for the process on which the last event occurred.

Returns the engine thread ID for the thread on which the last event occurred.

Returns the number of processes for the current target.

Returns the number of threads in the current process.

Returns the engine process ID for the specified process.

Returns the engine process ID for the specified process.

Returns the engine process ID for the specified process.

Returns the engine process ID for a process specified by its system process ID.

Returns the engine process ID and system process ID for the specified processes in the current target.

Returns the engine thread ID for the specified thread.

Returns the engine thread ID for the specified thread.

Returns the engine thread ID for the kernel-modevirtual thread corresponding to the specified processor.

Returns the engine thread ID for the specified thread.

Returns the engine thread ID of the specified thread.

Returns the engine and system thread IDs for the specified threads in the current process.

Returns the total number of threads for all the processes in the current target, in addition to the largest number of threads in any process for the current target.

Makes the specified process the current process.

Makes the specified thread the current thread.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects2.md">IDebugSystemObjects2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSystemObjects interface%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

