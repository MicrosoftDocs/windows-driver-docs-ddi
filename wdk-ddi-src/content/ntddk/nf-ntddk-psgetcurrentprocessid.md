---
UID: NF:ntddk.PsGetCurrentProcessId
title: PsGetCurrentProcessId function (ntddk.h)
description: The PsGetCurrentProcessId routine identifies the current thread's process.
old-location: kernel\psgetcurrentprocessid.htm
tech.root: kernel
ms.assetid: 9434f740-34c1-4244-813d-3fe9f1ead333
ms.date: 04/30/2018
keywords: ["PsGetCurrentProcessId function"]
ms.keywords: PsGetCurrentProcessId, PsGetCurrentProcessId routine [Kernel-Mode Driver Architecture], k108_e38b09ef-d948-4eb9-bfdd-24b25ba55034.xml, kernel.psgetcurrentprocessid, ntddk/PsGetCurrentProcessId
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

The <b>PsGetCurrentProcessId</b> routine identifies the current thread's process.

## -returns

<b>PsGetCurrentProcessId</b> returns the process ID of the current thread's process.

## -see-also

[IoGetCurrentProcess](../wdm/nf-wdm-iogetcurrentprocess.md)



[PsGetCurrentProcess](/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



[PsGetCurrentThread](./nf-ntddk-psgetcurrentthread.md)



[PsGetCurrentThreadId](./nf-ntddk-psgetcurrentthreadid.md)



[PsSetCreateProcessNotifyRoutine](./nf-ntddk-pssetcreateprocessnotifyroutine.md)



[PsSetCreateThreadNotifyRoutine](./nf-ntddk-pssetcreatethreadnotifyroutine.md)



[PsSetLoadImageNotifyRoutine](./nf-ntddk-pssetloadimagenotifyroutine.md)