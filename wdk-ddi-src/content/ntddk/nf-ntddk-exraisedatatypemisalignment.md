---
UID: NF:ntddk.ExRaiseDatatypeMisalignment
title: ExRaiseDatatypeMisalignment function (ntddk.h)
description: The ExRaiseDatatypeMisalignment routine can be used with structured exception handling to throw a driver-determined exception for a misaligned data type that occurs when a driver processes I/O requests.
old-location: kernel\exraisedatatypemisalignment.htm
tech.root: kernel
ms.assetid: 5c8bfd13-31e0-461f-93d2-53ce15c53cdb
ms.date: 04/30/2018
keywords: ["ExRaiseDatatypeMisalignment function"]
ms.keywords: ExRaiseDatatypeMisalignment, ExRaiseDatatypeMisalignment routine [Kernel-Mode Driver Architecture], k102_ff274a50-ae59-4591-9484-6bc068601ee8.xml, kernel.exraisedatatypemisalignment, ntddk/ExRaiseDatatypeMisalignment
f1_keywords:
 - "ntddk/ExRaiseDatatypeMisalignment"
 - "ExRaiseDatatypeMisalignment"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExRaiseDatatypeMisalignment
targetos: Windows
req.typenames: 
---

# ExRaiseDatatypeMisalignment function


## -description


The <b>ExRaiseDatatypeMisalignment</b> routine can be used with structured exception handling to throw a driver-determined exception for a misaligned data type that occurs when a driver processes I/O requests.


## -remarks



<b>ExRaiseDatatypeMisalignment</b> raises an exception with the exception code set to STATUS_DATATYPE_MISALIGNMENT.

Because <b>ExRaiseDatatypeMisalignment</b> can only be used at IRQL = PASSIVE_LEVEL, only high-level drivers typically use this routine — for example, file system drivers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exraiseaccessviolation">ExRaiseAccessViolation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exraisestatus">ExRaiseStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>
 

 

