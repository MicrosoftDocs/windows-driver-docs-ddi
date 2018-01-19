---
UID: NF:ntddk.PsSetCreateProcessNotifyRoutine
title: PsSetCreateProcessNotifyRoutine function
author: windows-driver-content
description: The PsSetCreateProcessNotifyRoutine routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted.
old-location: kernel\pssetcreateprocessnotifyroutine.htm
old-project: kernel
ms.assetid: eeeea140-e469-476f-adce-4505817bc35e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsSetCreateProcessNotifyRoutine
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
req.alt-api: PsSetCreateProcessNotifyRoutine
req.alt-loc: NtosKrnl.exe
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsSetCreateProcessNotifyRoutine function



## -description
The <b>PsSetCreateProcessNotifyRoutine</b> routine adds a driver-supplied callback routine to, or removes it from, a list of routines to be called whenever a process is created or deleted.



## -syntax

````
NTSTATUS PsSetCreateProcessNotifyRoutine(
  _In_ PCREATE_PROCESS_NOTIFY_ROUTINE NotifyRoutine,
  _In_ BOOLEAN                        Remove
);
````


## -parameters

### -param NotifyRoutine [in]

Specifies the entry point of a caller-supplied process-creation callback routine. See <a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine.md">PCREATE_PROCESS_NOTIFY_ROUTINE</a>.


### -param Remove [in]

Indicates whether the routine specified by <i>NotifyRoutine</i> should be added to or removed from the system's list of notification routines. If <b>FALSE</b>, the specified routine is added to the list. If <b>TRUE</b>, the specified routine is removed from the list.


## -returns
<b>PsSetCreateProcessNotifyRoutine</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The given <i>NotifyRoutine</i> is now registered with the system.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The given <i>NotifyRoutine</i> has already been registered, so this call is a redundant call, or the system has reached its limit for registering process-creation callbacks. 

 


## -remarks
Highest-level drivers can call <b>PsSetCreateProcessNotifyRoutine</b> to set up their process-creation notify routines implemented as <a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine.md">PCREATE_PROCESS_NOTIFY_ROUTINE</a>.

An IFS or highest-level system-profiling driver might register a process-creation callback to track the system-wide creation and deletion of processes against the driver's internal state. For Windows Vista and later versions of Windows, the system can register up to 64 process-creation callback routines.

A driver must remove any callbacks that it registers before it unloads. You can remove the callback by calling <b>PsSetCreateProcessNotify</b> with <i>Remove</i> = <b>TRUE</b>.

After a driver-supplied routine is registered, it is called with <i>Create</i> set to <b>TRUE</b> just after the initial thread is created within the newly created process designated by the input <i>ProcessId</i> handle. The input <i>ParentId</i> handle identifies the parent process of the newly-created process (this is the parent used for priority, affinity, quota, token, and handle inheritance, among others).


## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pcreate_process_notify_routine.md">PCREATE_PROCESS_NOTIFY_ROUTINE</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-psgetcurrentprocessid.md">PsGetCurrentProcessId</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutineex.md">PsSetCreateProcessNotifyRoutineEx</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsSetCreateProcessNotifyRoutine routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

