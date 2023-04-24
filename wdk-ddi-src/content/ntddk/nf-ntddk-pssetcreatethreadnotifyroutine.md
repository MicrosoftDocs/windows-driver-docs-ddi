---
UID: NF:ntddk.PsSetCreateThreadNotifyRoutine
title: PsSetCreateThreadNotifyRoutine function (ntddk.h)
description: The PsSetCreateThreadNotifyRoutine routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["PsSetCreateThreadNotifyRoutine function"]
ms.keywords: PsSetCreateThreadNotifyRoutine, PsSetCreateThreadNotifyRoutine routine [Kernel-Mode Driver Architecture], k108_1fe3d941-1e48-4f07-bf57-ad7b2855947f.xml, kernel.pssetcreatethreadnotifyroutine, ntddk/PsSetCreateThreadNotifyRoutine
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsSetCreateThreadNotifyRoutine
 - ntddk/PsSetCreateThreadNotifyRoutine
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsSetCreateThreadNotifyRoutine
---

## -description

The **PsSetCreateThreadNotifyRoutine** routine registers a driver-supplied callback that is subsequently notified when a new thread is created and when such a thread is deleted.

## -parameters

### -param NotifyRoutine [in]

A pointer to the driver's implementation of [PCREATE_THREAD_NOTIFY_ROUTINE](./nc-ntddk-pcreate_thread_notify_routine.md) routine.

## -returns

**PsSetCreateThreadNotifyRoutine** either returns STATUS_SUCCESS or it returns STATUS_INSUFFICIENT_RESOURCES if it failed the callback registration.

## -remarks

Highest-level drivers can call **PsSetCreateThreadNotifyRoutine** to set up their thread-creation notify routines, declared as follows:

```cpp
VOID
(*PCREATE_THREAD_NOTIFY_ROUTINE) (
    IN HANDLE  ProcessId,
    IN HANDLE  ThreadId,
    IN BOOLEAN  Create
    );
```

For example, an IFS or highest-level system-profiling driver might register such a thread-creation callback to track the system-wide creation and deletion of threads against the driver's internal state.

A driver must remove any callbacks it registers before it unloads. You can remove the callback by calling the [PsRemoveCreateThreadNotifyRoutine](./nf-ntddk-psremovecreatethreadnotifyroutine.md) routine.

## -see-also

[PsGetCurrentProcessId](./nf-ntddk-psgetcurrentprocessid.md)

[PsGetCurrentThreadId](./nf-ntddk-psgetcurrentthreadid.md)

[PsIsSystemThread](../ntifs/nf-ntifs-psissystemthread.md)

[PsRemoveCreateThreadNotifyRoutine](./nf-ntddk-psremovecreatethreadnotifyroutine.md)

[PsSetCreateProcessNotifyRoutine](./nf-ntddk-pssetcreateprocessnotifyroutine.md)

[PsSetLoadImageNotifyRoutine](./nf-ntddk-pssetloadimagenotifyroutine.md)