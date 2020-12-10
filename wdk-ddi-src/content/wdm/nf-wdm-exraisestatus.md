---
UID: NF:wdm.ExRaiseStatus
title: ExRaiseStatus function (wdm.h)
description: The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.
old-location: kernel\exraisestatus.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExRaiseStatus function"]
ms.keywords: ExRaiseStatus, ExRaiseStatus routine [Kernel-Mode Driver Architecture], k102_b188a166-f1f1-49bd-8195-aa72f86ca177.xml, kernel.exraisestatus, wdm/ExRaiseStatus
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExRaiseStatus
 - wdm/ExRaiseStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExRaiseStatus
---

# ExRaiseStatus function


## -description

The <b>ExRaiseStatus</b> routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.

## -parameters

### -param Status 

[in]
Specifies one of the system-defined STATUS_<i>XXX</i> values.

## -remarks

Highest-level drivers, particularly file systems, can call <b>ExRaiseStatus</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exraiseaccessviolation">ExRaiseAccessViolation</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exraisedatatypemisalignment">ExRaiseDatatypeMisalignment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>
