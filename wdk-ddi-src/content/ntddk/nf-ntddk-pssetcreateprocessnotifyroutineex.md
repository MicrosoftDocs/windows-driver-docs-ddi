---
UID: NF:ntddk.PsSetCreateProcessNotifyRoutineEx
title: PsSetCreateProcessNotifyRoutineEx function (ntddk.h)
description: The PsSetCreateProcessNotifyRoutineEx routine registers or removes a callback routine that notifies the caller when a process is created or exits.
old-location: kernel\pssetcreateprocessnotifyroutineex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsSetCreateProcessNotifyRoutineEx function"]
ms.keywords: PsSetCreateProcessNotifyRoutineEx, PsSetCreateProcessNotifyRoutineEx routine [Kernel-Mode Driver Architecture], k108_b68156fb-55d5-4192-a4d0-d74603647f42.xml, kernel.pssetcreateprocessnotifyroutineex, ntddk/PsSetCreateProcessNotifyRoutineEx
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1 and Windows Server 2008.
req.target-min-winversvr: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsSetCreateProcessNotifyRoutineEx
 - ntddk/PsSetCreateProcessNotifyRoutineEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsSetCreateProcessNotifyRoutineEx
---

# PsSetCreateProcessNotifyRoutineEx function


## -description

The <b>PsSetCreateProcessNotifyRoutineEx</b> routine registers or removes a callback routine that notifies the caller when a process is created or exits.

## -parameters

### -param NotifyRoutine [in]


A pointer to the <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine_ex">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a> routine to register or remove. The operating system calls this routine whenever a new process is created.

### -param Remove [in]


A Boolean value that specifies whether <b>PsSetCreateProcessNotifyRoutineEx</b> will add or remove a specified routine from the list of callback routines. If this parameter is <b>TRUE</b>, the specified routine is removed from the list of callback routines. If this parameter is <b>FALSE</b>, the specified routine is added to the list of callback routines. If <i>Remove</i> is <b>TRUE</b>, the system also waits for all in-flight callback routines to complete before returning.

## -returns

<b>PsSetCreateProcessNotifyRoutineEx</b> returns one of the following NTSTATUS values:

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
The specified routine is now registered with the operating system. The operating system calls this routine whenever a new process is created.

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

Highest-level drivers can call <b>PsSetCreateProcessNotifyRoutineEx</b> to register a <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine_ex">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a> routine. An installable file system (IFS) or highest-level system-profiling driver might register a process-creation callback routine to track which processes are created and deleted against the driver's internal state across the system. 

A driver must remove any callback routines that it registers before it unloads. You can remove the callback routine by calling <b>PsSetCreateProcessNotifyRoutineEx</b> with <i>Remove</i> set to <b>TRUE</b>. A driver must not make this call from its implementation of the [*PCREATE_PROCESS_NOTIFY_ROUTINE_EX*](./nc-ntddk-pcreate_process_notify_routine_ex.md) callback routine. 

The operating system calls the driver's process-notify routine at PASSIVE_LEVEL inside a critical region with <a href="/windows-hardware/drivers/kernel/types-of-apcs">normal kernel APCs</a> disabled. When a process is created, the process-notify routine runs just after the first thread in the process has been created. When a process is deleted, the process-notify routine runs in the context of the last thread to exit from the process.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pcreate_process_notify_routine_ex">PCREATE_PROCESS_NOTIFY_ROUTINE_EX</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_ps_create_notify_info">PS_CREATE_NOTIFY_INFO</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>
