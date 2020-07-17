---
UID: NF:ntddk.ExRaiseAccessViolation
title: ExRaiseAccessViolation function (ntddk.h)
description: The ExRaiseAccessViolation routine can be used with structured exception handling to throw a driver-determined exception for a memory access violation that occurs when a driver processes I/O requests.
old-location: kernel\exraiseaccessviolation.htm
tech.root: kernel
ms.assetid: c35e07c0-ffbd-4110-bb32-b47a512129dd
ms.date: 04/30/2018
keywords: ["ExRaiseAccessViolation function"]
ms.keywords: ExRaiseAccessViolation, ExRaiseAccessViolation routine [Kernel-Mode Driver Architecture], k102_71b4c053-599c-4a6d-8a59-08aae6bdc534.xml, kernel.exraiseaccessviolation, ntddk/ExRaiseAccessViolation
f1_keywords:
 - "ntddk/ExRaiseAccessViolation"
 - "ExRaiseAccessViolation"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
- ExRaiseAccessViolation
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExRaiseAccessViolation function


## -description


The <b>ExRaiseAccessViolation</b> routine can be used with structured exception handling to throw a driver-determined exception for a memory access violation that occurs when a driver processes I/O requests.


## -remarks



<b>ExRaiseAccessViolation</b> raises an exception with the exception code set to STATUS_ACCESS_VIOLATION.

Because <b>ExRaiseAccessViolation</b> can only be used at IRQL = PASSIVE_LEVEL, only high-level drivers typically use this routine—for example, file system drivers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exraisedatatypemisalignment">ExRaiseDatatypeMisalignment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exraisestatus">ExRaiseStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>
 

 

