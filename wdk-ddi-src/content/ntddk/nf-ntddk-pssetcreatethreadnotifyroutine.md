---
UID: NF:ntddk.PsSetCreateThreadNotifyRoutine
title: PsSetCreateThreadNotifyRoutine function
author: windows-driver-content
description: The PsSetCreateThreadNotifyRoutine routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.
old-location: kernel\pssetcreatethreadnotifyroutine.htm
old-project: kernel
ms.assetid: 02c5d325-e0b2-4b0f-b964-7befd1b40cb6
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsSetCreateThreadNotifyRoutine function


## -description


The <b>PsSetCreateThreadNotifyRoutine</b> routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.


## -syntax


````
NTSTATUS PsSetCreateThreadNotifyRoutine(
  _In_ PCREATE_THREAD_NOTIFY_ROUTINE NotifyRoutine
);
````


## -parameters




### -param NotifyRoutine [in]

A pointer to the driver's implementation of <a href="..\ntddk\nc-ntddk-pcreate_thread_notify_routine.md">PCREATE_THREAD_NOTIFY_ROUTINE</a> routine. 


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

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the <a href="..\ntddk\nf-ntddk-psremovecreatethreadnotifyroutine.md">PsRemoveCreateThreadNotifyRoutine</a> routine.




## -see-also

<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>



<a href="..\ntifs\nf-ntifs-psissystemthread.md">PsIsSystemThread</a>



<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>



<a href="..\ntddk\nf-ntddk-psgetcurrentthreadid.md">PsGetCurrentThreadId</a>



<a href="..\ntddk\nf-ntddk-psremovecreatethreadnotifyroutine.md">PsRemoveCreateThreadNotifyRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsSetCreateThreadNotifyRoutine routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

