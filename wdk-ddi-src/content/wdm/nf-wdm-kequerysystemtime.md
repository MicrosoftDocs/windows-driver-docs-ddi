---
UID: NF:wdm.KeQuerySystemTime
title: KeQuerySystemTime macro
author: windows-driver-content
description: The KeQuerySystemTime routine obtains the current system time.
old-location: kernel\kequerysystemtime.htm
old-project: kernel
ms.assetid: de271bd2-93cf-444d-889d-09c7e654e688
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeQuerySystemTime, KeQuerySystemTime routine [Kernel-Mode Driver Architecture], k105_0eaf1b30-c365-45ac-828c-fbcc7cd71ff3.xml, kernel.kequerysystemtime, wdm/KeQuerySystemTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	KeQuerySystemTime
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQuerySystemTime macro


## -description


The <b>KeQuerySystemTime</b> routine obtains the current system time.


## -syntax


````
VOID KeQuerySystemTime(
  _Out_ PLARGE_INTEGER CurrentTime
);
````


## -parameters




### -param CurrentCount

TBD






#### - CurrentTime [out]

Pointer to the current time on return from <b>KeQuerySystemTime</b>. 


## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>. 




## -see-also

<a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>



<a href="..\wdm\nf-wdm-kequerytickcount.md">KeQueryTickCount</a>



<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQuerySystemTime routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

