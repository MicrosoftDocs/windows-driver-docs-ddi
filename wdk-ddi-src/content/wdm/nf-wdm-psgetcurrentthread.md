---
UID: NF:wdm.PsGetCurrentThread
title: PsGetCurrentThread function (wdm.h)
description: Learn how the PsGetCurrentThread routine (wdm.h) identifies the current thread.
old-location: kernel\psgetcurrentthread.htm
tech.root: kernel
ms.date: 07/30/2021
keywords: ["PsGetCurrentThread function"]
ms.keywords: ExGetCurrentResourceThread, PsGetCurrentThread, PsGetCurrentThread routine [Kernel-Mode Driver Architecture], k108_75fb6f47-8a13-4f2c-9b94-a8b7125bbcb6.xml, kernel.psgetcurrentthread, wdm/PsGetCurrentThread
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - PsGetCurrentThread
 - wdm/PsGetCurrentThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsGetCurrentThread
---

# PsGetCurrentThread function (wdm.h)

## -description

The **PsGetCurrentThread** routine identifies the current thread.

## -returns

**PsGetCurrentThread** returns a pointer to the executive thread object that represents the currently executing thread.

## -remarks

## -see-also

[KeGetCurrentThread](./nf-wdm-kegetcurrentthread.md)

[PsCreateSystemThread](./nf-wdm-pscreatesystemthread.md)

[PsGetCurrentProcess](/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)

[PsGetCurrentProcessId](../ntddk/nf-ntddk-psgetcurrentprocessid.md)

[PsIsSystemThread](../ntifs/nf-ntifs-psissystemthread.md)
