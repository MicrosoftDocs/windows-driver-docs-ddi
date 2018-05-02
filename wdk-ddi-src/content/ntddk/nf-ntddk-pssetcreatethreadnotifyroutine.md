---
UID: NF:ntddk.PsSetCreateThreadNotifyRoutine
title: PsSetCreateThreadNotifyRoutine function
author: windows-driver-content
description: The PsSetCreateThreadNotifyRoutine routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.
old-location: kernel\pssetcreatethreadnotifyroutine.htm
old-project: kernel
ms.assetid: 02c5d325-e0b2-4b0f-b964-7befd1b40cb6
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PsSetCreateThreadNotifyRoutine, PsSetCreateThreadNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_1fe3d941-1e48-4f07-bf57-ad7b2855947f.xml, kernel.pssetcreatethreadnotifyroutine, ntddk/PsSetCreateThreadNotifyRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsSetCreateThreadNotifyRoutine
product: Windows
targetos: Windows
req.typenames: 
---

# PsSetCreateThreadNotifyRoutine function


## -description


The <b>PsSetCreateThreadNotifyRoutine</b> routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.


## -parameters




### -param NotifyRoutine [in]

A pointer to the driver's implementation of <a href="https://msdn.microsoft.com/library/windows/hardware/mt764087">PCREATE_THREAD_NOTIFY_ROUTINE</a> routine. 


## -returns



<b>PsSetCreateThreadNotifyRoutine</b> either returns STATUS_SUCCESS or it returns STATUS_INSUFFICIENT_RESOURCES if it failed the callback registration.




## -remarks



Highest-level drivers can call <b>PsSetCreateThreadNotifyRoutine</b> to set up their thread-creation notify routines, declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PCREATE_THREAD_NOTIFY_ROUTINE) (
    IN HANDLE  ProcessId,
    IN HANDLE  ThreadId,
    IN BOOLEAN  Create
    );</pre>
</td>
</tr>
</table></span></div>
For example, an IFS or highest-level system-profiling driver might register such a thread-creation callback to track the system-wide creation and deletion of threads against the driver's internal state.

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559947">PsRemoveCreateThreadNotifyRoutine</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559935">PsGetCurrentProcessId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559937">PsGetCurrentThreadId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559945">PsIsSystemThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559947">PsRemoveCreateThreadNotifyRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559951">PsSetCreateProcessNotifyRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559957">PsSetLoadImageNotifyRoutine</a>
 

 

