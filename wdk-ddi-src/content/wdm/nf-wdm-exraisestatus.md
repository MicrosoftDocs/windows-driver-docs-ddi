---
UID: NF:wdm.ExRaiseStatus
title: ExRaiseStatus function
author: windows-driver-content
description: The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests.
old-location: kernel\exraisestatus.htm
old-project: kernel
ms.assetid: eefbec75-f441-492b-becb-98434253dd62
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.exraisestatus, ExRaiseStatus, wdm/ExRaiseStatus, ExRaiseStatus routine [Kernel-Mode Driver Architecture], k102_b188a166-f1f1-49bd-8195-aa72f86ca177.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
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

<a href="..\ntddk\nf-ntddk-exraisedatatypemisalignment.md">ExRaiseDatatypeMisalignment</a>



<a href="..\ntddk\nf-ntddk-exraiseaccessviolation.md">ExRaiseAccessViolation</a>



<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



<a href="..\wdm\nf-wdm-kebugcheckex.md">KeBugCheckEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExRaiseStatus routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

