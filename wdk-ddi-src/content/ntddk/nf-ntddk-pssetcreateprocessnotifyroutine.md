---
UID: NF:ntddk.PsSetCreateProcessNotifyRoutine
title: PsSetCreateProcessNotifyRoutine function (ntddk.h)
description: The PsSetCreateProcessNotifyRoutine routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted.
old-location: kernel\pssetcreateprocessnotifyroutine.htm
tech.root: kernel
ms.assetid: eeeea140-e469-476f-adce-4505817bc35e
ms.date: 04/30/2018
ms.keywords: PsSetCreateProcessNotifyRoutine, PsSetCreateProcessNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_6ae7797a-ecbe-4665-85d5-e199f13613cd.xml, kernel.pssetcreateprocessnotifyroutine, ntddk/PsSetCreateProcessNotifyRoutine
ms.topic: function
f1_keywords:
 - "ntddk/PsSetCreateProcessNotifyRoutine"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsSetCreateProcessNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsSetCreateProcessNotifyRoutine function


## -description


The <b>PsSetCreateProcessNotifyRoutine</b> routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted.


## -parameters




### -param NotifyRoutine [in]

Specifies the entry point of a caller-supplied process-creation callback routine. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine">PCREATE_PROCESS_NOTIFY_ROUTINE</a>.


### -param Remove [in]

Indicates whether the routine specified by <i>NotifyRoutine</i> should be added to or removed from the system's list of notification routines. If <b>FALSE</b>, the specified routine is added to the list. If <b>TRUE</b>, the specified routine is removed from the list.


## -returns



<b>PsSetCreateProcessNotifyRoutine</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given <i>NotifyRoutine</i> is now registered with the system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given <i>NotifyRoutine</i> has already been registered, so this call is a redundant call, or the system has reached its limit for registering process-creation callbacks. 

</td>
</tr>
</table>
 




## -remarks



Highest-level drivers can call <b>PsSetCreateProcessNotifyRoutine</b> to set up their process-creation notify routines implemented as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine">PCREATE_PROCESS_NOTIFY_ROUTINE</a>.

An IFS or highest-level system-profiling driver might register a process-creation callback to track the system-wide creation and deletion of processes against the driver's internal state. For Windows Vista and later versions of Windows, the system can register up to 64 process-creation callback routines.

A driver must remove any callbacks that it registers before it unloads. You can remove the callback by calling <b>PsSetCreateProcessNotify</b> with <i>Remove</i> = <b>TRUE</b>.

After a driver-supplied routine is registered, it is called with <i>Create</i> set to <b>TRUE</b> just after the initial thread is created within the newly created process designated by the input <i>ProcessId</i> handle. The input <i>ParentId</i> handle identifies the parent process of the newly-created process (this is the parent used for priority, affinity, quota, token, and handle inheritance, among others).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine">PCREATE_PROCESS_NOTIFY_ROUTINE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex">PsSetCreateProcessNotifyRoutineEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a>
 

 

