---
UID: NF:wdm.KeQueryRuntimeThread
title: KeQueryRuntimeThread function (wdm.h)
description: The KeQueryRuntimeThread routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks.
old-location: kernel\kequeryruntimethread.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeQueryRuntimeThread function"]
ms.keywords: KeQueryRuntimeThread, KeQueryRuntimeThread routine [Kernel-Mode Driver Architecture], k105_e8f1a28f-98f1-447c-bb72-1d1da6b50f01.xml, kernel.kequeryruntimethread, wdm/KeQueryRuntimeThread
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
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
 - KeQueryRuntimeThread
 - wdm/KeQueryRuntimeThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQueryRuntimeThread
---

# KeQueryRuntimeThread function


## -description

The <b>KeQueryRuntimeThread</b> routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks.

## -parameters

### -param Thread [in]


Pointer to a dispatcher object of type KTHREAD.

### -param UserTime [out]


Pointer to the memory location where <b>KeQueryRuntimeThread</b> returns the accumulated user-mode run time of the current thread, in clock ticks.

## -returns

<b>KeQueryRuntimeThread</b> returns the accumulated kernel-mode run time of the current thread, in clock ticks.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerytimeincrement">KeQueryTimeIncrement</a>
