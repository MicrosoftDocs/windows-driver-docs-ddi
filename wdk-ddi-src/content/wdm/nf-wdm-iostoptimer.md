---
UID: NF:wdm.IoStopTimer
title: IoStopTimer function
author: windows-driver-content
description: The IoStopTimer routine disables the timer for a specified device object so the driver-supplied IoTimer routine is not called.
old-location: kernel\iostoptimer.htm
old-project: kernel
ms.assetid: 4b903046-8f96-4299-94e7-85900be1bbd4
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoStopTimer, IoStopTimer routine [Kernel-Mode Driver Architecture], k104_dfedf779-1137-44c1-ab06-223c3ce6e9c6.xml, kernel.iostoptimer, wdm/IoStopTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStopTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoStopTimer function


## -description


The <b>IoStopTimer</b> routine disables the timer for a specified device object so the driver-supplied <a href="..\wdm\nc-wdm-io_timer_routine.md">IoTimer</a> routine is not called. 


## -syntax


````
VOID IoStopTimer(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object with which the <a href="..\wdm\nc-wdm-io_timer_routine.md">IoTimer</a> routine is associated.


## -returns



None




## -remarks



The driver-supplied <a href="..\wdm\nc-wdm-io_timer_routine.md">IoTimer</a> routine can be reenabled with a call to <b>IoStartTimer</b>.

Do not call <b>IoStopTimer</b> from within the <i>IoTimer</i> routine. 




## -see-also

<a href="..\wdm\nf-wdm-ioinitializetimer.md">IoInitializeTimer</a>



<a href="..\wdm\nf-wdm-iostarttimer.md">IoStartTimer</a>



 

 


