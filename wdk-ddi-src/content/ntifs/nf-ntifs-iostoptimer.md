---
UID: NF:ntifs.IoStopTimer
title: IoStopTimer function
author: windows-driver-content
description: The IoStopTimer routine disables the timer for a specified device object so the driver-supplied IoTimer routine is not called.
old-location: kernel\iostoptimer.htm
old-project: kernel
ms.assetid: 4b903046-8f96-4299-94e7-85900be1bbd4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , I, IoStopTimer, IoStopTimer routine [Kernel-Mode Driver Architecture], S, T, e, i, k104_dfedf779-1137-44c1-ab06-223c3ce6e9c6.xml, kernel.iostoptimer, m, o, p, r, t, wdm/IoStopTimer"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoStopTimer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
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

<a href="..\wdm\nf-wdm-iostarttimer.md">IoStartTimer</a>



<a href="..\wdm\nf-wdm-ioinitializetimer.md">IoInitializeTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStopTimer routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

