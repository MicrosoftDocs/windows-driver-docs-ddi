---
UID: NC:ntddk.PCREATE_PROCESS_NOTIFY_ROUTINE
title: PCREATE_PROCESS_NOTIFY_ROUTINE (ntddk.h)
description: Process-creation callback implemented by a driver to track the system-wide creation and deletion of processes against the driver's internal state.
old-location: kernel\pcreate_process_notify_routine.htm
tech.root: kernel
ms.assetid: 2C5B3C90-04A9-48CF-9162-0E069A483C5F
ms.date: 04/30/2018
ms.keywords: PCREATE_PROCESS_NOTIFY_ROUTINE, PCREATE_PROCESS_NOTIFY_ROUTINE callback, SetCreateProcessNotifyRoutine, SetCreateProcessNotifyRoutine callback function [Kernel-Mode Driver Architecture], kernel.pcreate_process_notify_routine, ntddk/SetCreateProcessNotifyRoutine
f1_keywords:
 - "ntddk/SetCreateProcessNotifyRoutine"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- SetCreateProcessNotifyRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCREATE_PROCESS_NOTIFY_ROUTINE callback function


## -description


Process-creation callback implemented by a driver  to track the system-wide creation and deletion of processes against the driver's internal state.
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager#best">Best Practices</a>. </div><div> </div>

## -parameters




### -param ParentId [in]

The process ID of the parent process.


### -param ProcessId [in]

The process ID of the process.


### -param Create [in]

Indicates whether the process was created (<b>TRUE</b>) or deleted (<b>FALSE</b>).


## -remarks



Highest-level drivers call <b>PsSetCreateProcessNotifyRoutine</b> to register their process-creation notify routines.

A driver's process-notify routine is also called with <i>Create</i> set to <b>FALSE</b>, typically when the last thread within a process has terminated and the process address space is about to be deleted.

 The operating system calls the driver's process-notify routine at PASSIVE_LEVEL inside a critical region with <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/types-of-apcs">normal kernel APCs</a> disabled. When a process is created, the process-notify routine runs in the context of the thread that created the new process. When a process is deleted, the process-notify routine runs in the context of the last thread to exit from the process.




## -see-also




<b>PsSetCreateProcessNotifyRoutine</b>
 

 

