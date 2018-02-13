---
UID: NF:wdm.KeQueryTimeIncrement
title: KeQueryTimeIncrement function
author: windows-driver-content
description: The KeQueryTimeIncrement routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.
old-location: kernel\kequerytimeincrement.htm
old-project: kernel
ms.assetid: f8291e2b-a7a1-4a19-9137-fcd93e62bbaf
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.kequerytimeincrement, KeQueryTimeIncrement routine [Kernel-Mode Driver Architecture], k105_dc7a4658-7d4b-4b60-a8c8-693c36d68b27.xml, KeQueryTimeIncrement, wdm/KeQueryTimeIncrement
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeQueryTimeIncrement
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryTimeIncrement function


## -description


The <b>KeQueryTimeIncrement</b> routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.


## -syntax


````
ULONG KeQueryTimeIncrement(void);
````


## -parameters






## -returns



<b>KeQueryTimeIncrement</b> returns a ULONG value indicating the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts.




## -remarks



At startup time, the operating system determines the time increment to use for the system time. This time increment remains constant until the computer restarts. During this time, calls to <b>KeQueryTimeIncrement</b> always return the same time increment value. The time increment does not change while the computer is running, and it does not change as the result of a suspend-resume cycle.




## -see-also

<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>



<a href="..\wdm\nf-wdm-kequerytickcount.md">KeQueryTickCount</a>



<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryTimeIncrement routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

