---
UID: NF:wdm.ExRaiseStatus
title: ExRaiseStatus function
author: windows-driver-content
description: The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.
old-location: kernel\exraisestatus.htm
old-project: kernel
ms.assetid: eefbec75-f441-492b-becb-98434253dd62
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExRaiseStatus, ExRaiseStatus routine [Kernel-Mode Driver Architecture], k102_b188a166-f1f1-49bd-8195-aa72f86ca177.xml, kernel.exraisestatus, wdm/ExRaiseStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExRaiseStatus
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExRaiseStatus function


## -description


The <b>ExRaiseStatus</b> routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.


## -syntax


````
VOID ExRaiseStatus(
  _In_ NTSTATUS Status
);
````


## -parameters




### -param Status [in]

Specifies one of the system-defined STATUS_<i>XXX</i> values. 


## -returns



None




## -remarks



Highest-level drivers, particularly file systems, can call <b>ExRaiseStatus</b>. 




## -see-also

<a href="..\ntddk\nf-ntddk-exraiseaccessviolation.md">ExRaiseAccessViolation</a>



<a href="..\ntddk\nf-ntddk-exraisedatatypemisalignment.md">ExRaiseDatatypeMisalignment</a>



<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



<a href="..\wdm\nf-wdm-kebugcheckex.md">KeBugCheckEx</a>



 

 


