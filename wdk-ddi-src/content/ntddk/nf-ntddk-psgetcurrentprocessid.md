---
UID: NF:ntddk.PsGetCurrentProcessId
title: PsGetCurrentProcessId function (ntddk.h)
description: The PsGetCurrentProcessId routine identifies the current thread's process.
tech.root: kernel
ms.date: 09/22/2025
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetCurrentProcessId
 - ntddk/PsGetCurrentProcessId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetCurrentProcessId
---

# PsGetCurrentProcessId function

## -description

The **PsGetCurrentProcessId** routine identifies the current thread's process.

## -returns

**PsGetCurrentProcessId** returns the process ID of the process that created the current thread.

## -remarks

**PsGetCurrentProcessId** returns the process ID of the process that originally created the current thread, which is not necessarily the process that the thread is currently attached to. In scenarios where a thread may be attached to a different process context (via APC state), this can differ from `PsGetProcessId(PsGetCurrentProcess())`.

- **PsGetCurrentProcessId()** - Returns the process ID of the process that created the thread
- **PsGetProcessId(PsGetCurrentProcess())** - Returns the process ID of the process that the thread is currently attached to

Use **PsGetCurrentProcessId** when you need the ID of the process that owns the thread. Use **PsGetProcessId(PsGetCurrentProcess())** when you need the ID of the process context the thread is currently operating in.

## -see-also

[**IoGetCurrentProcess**](../wdm/nf-wdm-iogetcurrentprocess.md)

[**PsGetCurrentProcess**](/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)

[**PsGetCurrentThread**](./nf-ntddk-psgetcurrentthread.md)

[**PsGetCurrentThreadId**](./nf-ntddk-psgetcurrentthreadid.md)

[**PsGetProcessId**](./nf-ntddk-psgetprocessid.md)

[**PsSetCreateProcessNotifyRoutine**](./nf-ntddk-pssetcreateprocessnotifyroutine.md)

[**PsSetCreateThreadNotifyRoutine**](./nf-ntddk-pssetcreatethreadnotifyroutine.md)

[**PsSetLoadImageNotifyRoutine**](./nf-ntddk-pssetloadimagenotifyroutine.md)
