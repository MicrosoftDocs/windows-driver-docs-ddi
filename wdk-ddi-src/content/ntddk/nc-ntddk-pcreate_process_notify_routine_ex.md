---
UID: NC:ntddk.PCREATE_PROCESS_NOTIFY_ROUTINE_EX
title: PCREATE_PROCESS_NOTIFY_ROUTINE_EX
author: windows-driver-content
description: A callback routine implemented by a driver to notify the caller when a process is created or exits.
old-location: kernel\pcreate_process_notify_routine_ex.htm
old-project: kernel
ms.assetid: 071BD24F-AA58-4A39-8059-CEF6D7105DB6
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PCREATE_PROCESS_NOTIFY_ROUTINE_EX, PCREATE_PROCESS_NOTIFY_ROUTINE_EX callback, SetCreateProcessNotifyRoutineEx, SetCreateProcessNotifyRoutineEx callback function [Kernel-Mode Driver Architecture], kernel.pcreate_process_notify_routine_ex, ntddk/SetCreateProcessNotifyRoutineEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	SetCreateProcessNotifyRoutineEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCREATE_PROCESS_NOTIFY_ROUTINE_EX callback function


## -description


A callback routine implemented by a driver to notify the caller when a process is created or exits.
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager#best">Best Practices</a>. </div><div> </div>

## -parameters




### -param Process


### -param ProcessId [in]

The process ID of the process.


### -param CreateInfo [in, out, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559960">PS_CREATE_NOTIFY_INFO</a> structure that contains information about the new process. 


#### - ParentId [in]

The process ID of the parent process.


## -returns



This callback function does not return a value.




## -remarks



Highest-level drivers call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559953">PsSetCreateProcessNotifyRoutineEx</a> to register their implementation of  <i>PCREATE_PROCESS_NOTIFY_ROUTINE_EX</i> routine. An installable file system (IFS) or highest-level system-profiling driver might register a process-creation callback routine to track which processes are created and deleted against the driver's internal state across the system. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559953">PsSetCreateProcessNotifyRoutineEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt805891">PsSetCreateProcessNotifyRoutineEx2</a>
 

 

