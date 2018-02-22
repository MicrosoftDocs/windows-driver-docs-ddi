---
UID: NC:ntddk.PCREATE_THREAD_NOTIFY_ROUTINE
title: PCREATE_THREAD_NOTIFY_ROUTINE
author: windows-driver-content
description: A callback routine implemented by a driver to notify the caller when a thread is created or deleted.
old-location: kernel\pcreate_thread_notify_routine.htm
old-project: kernel
ms.assetid: AAA62659-D12C-4EEC-8D74-6138B34128CE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.pcreate_thread_notify_routine, SetCreateThreadNotifyRoutine callback function [Kernel-Mode Driver Architecture], SetCreateThreadNotifyRoutine, PCREATE_THREAD_NOTIFY_ROUTINE, PCREATE_THREAD_NOTIFY_ROUTINE, ntddk/SetCreateThreadNotifyRoutine
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
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ntddk.h
apiname:
-	SetCreateThreadNotifyRoutine
product: Windows
targetos: Windows
req.typenames: "*PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA"
---

# PCREATE_THREAD_NOTIFY_ROUTINE callback


## -description


A callback routine implemented by a driver to notify the caller when a thread is created or deleted.
<div class="alert"><b>Warning</b>  The actions that  you can perform in this routine are restricted for safe calls. See <a href="https://msdn.microsoft.com/c01b3fd9-7f4e-4d1a-a726-b31b0eebf094">Best Practices</a>. </div><div> </div>

## -prototype


````
PCREATE_THREAD_NOTIFY_ROUTINE SetCreateThreadNotifyRoutine;

void SetCreateThreadNotifyRoutine(
  _In_ HANDLE  ProcessId,
  _In_ HANDLE  ThreadId,
  _In_ BOOLEAN Create
)
{ ... }
````


## -parameters




### -param ProcessId [in]

The process ID of the process.


### -param ThreadId [in]

The thread ID of the thread.


### -param Create [in]

Indicates whether the thread was created (<b>TRUE</b>) or deleted (<b>FALSE</b>).


## -returns



This callback function does not return a value.




## -remarks



Highest-level drivers can call <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a> or <a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a> to register their thread-creation notify routine.

The driver's thread-notify routine runs at IRQL = PASSIVE_LEVEL or APC_LEVEL. When a thread is created, the thread-notify routine runs in the context of the thread that created the new thread. When a thread is deleted, the thread-notify routine runs in the context of this thread when the thread exits. 




## -see-also

<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutine.md">PsSetCreateThreadNotifyRoutine</a>



<a href="..\ntddk\nf-ntddk-pssetcreatethreadnotifyroutineex.md">PsSetCreateThreadNotifyRoutineEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCREATE_THREAD_NOTIFY_ROUTINE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

