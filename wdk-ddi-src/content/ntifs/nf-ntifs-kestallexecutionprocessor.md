---
UID: NF:ntifs.KeStallExecutionProcessor
title: KeStallExecutionProcessor function (ntifs.h)
description: Learn more about the KeStallExecutionProcessor routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["KeStallExecutionProcessor function"]
ms.keywords: KeStallExecutionProcessor, kernel.kestallexecutionprocessor, wdm/KeStallExecutionProcessor
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeStallExecutionProcessor
 - ntifs/KeStallExecutionProcessor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hal.dll
api_name:
 - KeStallExecutionProcessor
---

# KeStallExecutionProcessor function (ntifs.h)

## -description

The **KeStallExecutionProcessor** routine stalls the caller on the current processor for a specified time interval.

## -parameters

### -param MicroSeconds [in]

Specifies the number of microseconds to stall.

## -returns

None

## -remarks

**KeStallExecutionProcessor** is a processor-dependent routine that busy-waits for at least the specified number of microseconds, but not significantly longer.

This routine is for use by device drivers and other software that must wait for an interval of less than a clock tick but more than for a few instructions. If you use this routine you must minimize the stall interval, typically to less than 50 microseconds. If a driver must wait for a longer interval, you should use a different [synchronization technique](/windows-hardware/drivers/kernel/synchronization-techniques).

## -see-also

[**KeDelayExecutionThread**](../wdm/nf-wdm-kedelayexecutionthread.md)

[**KeWaitForMultipleObjects**](../wdm/nf-wdm-kewaitformultipleobjects.md)

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)
