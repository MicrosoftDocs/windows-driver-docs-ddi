---
UID: NF:ntddk.ExRaiseAccessViolation
title: ExRaiseAccessViolation function
author: windows-driver-content
description: The ExRaiseAccessViolation routine can be used with structured exception handling to throw a driver-determined exception for a memory access violation that occurs when a driver processes I/O requests.
old-location: kernel\exraiseaccessviolation.htm
old-project: kernel
ms.assetid: c35e07c0-ffbd-4110-bb32-b47a512129dd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExRaiseAccessViolation, kernel.exraiseaccessviolation, ntddk/ExRaiseAccessViolation, k102_71b4c053-599c-4a6d-8a59-08aae6bdc534.xml, ExRaiseAccessViolation routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExRaiseAccessViolation
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# ExRaiseAccessViolation function


## -description


The <b>ExRaiseAccessViolation</b> routine can be used with structured exception handling to throw a driver-determined exception for a memory access violation that occurs when a driver processes I/O requests.


## -syntax


````
VOID  ExRaiseAccessViolation(void);
````


## -parameters





## -returns


None



## -remarks


<b>ExRaiseAccessViolation</b> raises an exception with the exception code set to STATUS_ACCESS_VIOLATION.

Because <b>ExRaiseAccessViolation</b> can only be used at IRQL = PASSIVE_LEVEL, only high-level drivers typically use this routine—for example, file system drivers.



## -see-also

<a href="..\wdm\nf-wdm-kebugcheckex.md">KeBugCheckEx</a>

<a href="..\wdm\nf-wdm-exraisestatus.md">ExRaiseStatus</a>

<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>

<a href="..\ntddk\nf-ntddk-exraisedatatypemisalignment.md">ExRaiseDatatypeMisalignment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExRaiseAccessViolation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

