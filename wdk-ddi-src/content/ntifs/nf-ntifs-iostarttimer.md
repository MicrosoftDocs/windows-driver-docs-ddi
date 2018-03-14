---
UID: NF:ntifs.IoStartTimer
title: IoStartTimer function
author: windows-driver-content
description: The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second.
old-location: kernel\iostarttimer.htm
old-project: kernel
ms.assetid: 2e13d7da-7ef3-4c2e-b028-f7d37548c208
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoStartTimer, IoStartTimer routine [Kernel-Mode Driver Architecture], k104_bca7aa97-41e1-48e4-96df-52dd6109cd51.xml, kernel.iostarttimer, wdm/IoStartTimer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoStartTimer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoStartTimer function


## -description


The <b>IoStartTimer</b> routine enables the timer associated with a given device object so the driver-supplied <a href="..\wdm\nc-wdm-io_timer_routine.md">IoTimer</a> routine is called once per second.


## -syntax


````
VOID IoStartTimer(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to a device object whose timer routine is to be called.


## -returns



None




## -remarks



The driver must already have set up the IoTimer routine for the <i>DeviceObject</i> by calling <b>IoInitializeTimer</b>. 




## -see-also

<a href="..\wdm\nf-wdm-ioinitializetimer.md">IoInitializeTimer</a>



<a href="..\wdm\nc-wdm-io_timer_routine.md">IoTimer</a>



<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



<a href="..\wdm\nf-wdm-iostoptimer.md">IoStopTimer</a>



<a href="..\wdm\nf-wdm-kesettimer.md">KeSetTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStartTimer routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

