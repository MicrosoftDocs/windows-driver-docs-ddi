---
UID: NF:ntddk.PsSetCreateProcessNotifyRoutineEx2
title: PsSetCreateProcessNotifyRoutineEx2 function (ntddk.h)
description: The PsSetCreateProcessNotifyRoutineEx2 routine registers or removes a callback routine that notifies the caller when a process is created or deleted.
old-location: kernel\pssetcreateprocessnotifyroutineex2.htm
tech.root: kernel
ms.assetid: 25B053C1-E3A3-4002-9355-F3EEA8FECB44
ms.date: 04/30/2018
ms.keywords: PsSetCreateProcessNotifyRoutineEx2, PsSetCreateProcessNotifyRoutineEx2 routine [Kernel-Mode Driver Architecture], kernel.pssetcreateprocessnotifyroutineex2, ntddk/PsSetCreateProcessNotifyRoutineEx2
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
- PsSetCreateProcessNotifyRoutineEx2
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsSetCreateProcessNotifyRoutineEx2 function


## -description


The <b>PsSetCreateProcessNotifyRoutineEx2</b> routine registers or removes a callback routine that notifies the caller when a process is created or deleted.


## -parameters




### -param NotifyType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_pscreateprocessnotifytype">PSCREATEPROCESSNOTIFYTYPE</a>-type value that indicates the type of process notification.


### -param NotifyInformation [in]

The address of the notification information for the specified type of process notification. If <i>NotifyType</i> is <b>PsCreateProcessNotifySubsystems</b>, <i>NotifyInformation</i> is a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pcreate_process_notify_routine_ex">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a> that specifies the entry point of the caller-supplied process-creation callback. 


### -param Remove [in]

A Boolean value that specifies whether <b>PsSetCreateProcessNotifyRoutineEx2</b> will add or remove a specified routine from the list of callback routines. If this parameter is <b>TRUE</b>, the specified routine is removed from the list of callback routines. If this parameter is <b>FALSE</b>, the specified routine is added to the list of callback routines. If <i>Remove</i> is <b>TRUE</b>, the system also waits for all in-flight callback routines to complete before returning.


## -returns



<b>PsSetCreateProcessNotifyRoutineEx2</b> returns one of the following NTSTATUS values:

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
The specified  routine is now registered with the operating system. The operating system calls this routine whenever a new process is created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified routine was already registered, or the operating system has reached its limit for registering process-creation callback routines.

<i> NotifyType</i> is not <b>PsCreateProcessNotifySubsystems</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The image that contains the callback routine pointer did not have IMAGE_DLLCHARACTERISTICS_FORCE_INTEGRITY set in its image header.

</td>
</tr>
</table>
 




## -remarks



Drivers can call <b>PsSetCreateProcessNotifyRoutineEx2</b> to register their process-creation notify routines.

After a driver-supplied routine is registered, it is called with the unique ID (indicated by <i>ProcessId</i>) 
        of the created or deleted process.  The <i>ParentId</i> identifies the parent process of the new process (this is the parent used for priority, affinity, quota, token, and handle inheritance, among others) if it was
        created with the inherit handles option.  If it was created without
        the inherit handle options, then the parent process ID is NULL.
        

If the <i>Create</i> value is TRUE, the subsystem process
        was created; FALSE indicates the process was deleted. 

When the process is created, the callback function is invoked just after the first thread in the
        process has been created. Conversely, for deletion, the function is invoked after the
        last thread in the process has terminated and the address space is about
        to be deleted. It is possible that the callback is only invoked for deletion without getting a creation
        call in cases where the process was created and deleted
        without a thread ever being created.

A driver must remove any callback function that it registers before it unloads. You can remove the callback by calling <b>PsSetCreateProcessNotifyRoutineEx2</b> with <i>Remove</i> = <b>TRUE</b>.  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pcreate_process_notify_routine_ex">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex">PsSetCreateProcessNotifyRoutineEx</a>
 

 

