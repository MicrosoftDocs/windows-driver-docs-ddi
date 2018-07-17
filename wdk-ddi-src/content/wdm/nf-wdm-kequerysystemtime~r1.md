---
UID: NF:wdm.KeQuerySystemTime~r1
title: KeQuerySystemTime function
author: windows-driver-content
description: The KeQuerySystemTime routine obtains the current system time.
old-location: kernel\kequerysystemtime.htm
old-project: kernel
ms.assetid: de271bd2-93cf-444d-889d-09c7e654e688
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeQuerySystemTime, KeQuerySystemTime routine [Kernel-Mode Driver Architecture], k105_0eaf1b30-c365-45ac-828c-fbcc7cd71ff3.xml, kernel.kequerysystemtime, wdm/KeQuerySystemTime
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQuerySystemTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQuerySystemTime function


## -description


The <b>KeQuerySystemTime</b> routine obtains the current system time.


## -parameters




### -param CurrentCount [out]

Pointer to LARGE_INTEGER variable that receives the current time. 




## -remarks



System time is a count of 100-nanosecond intervals since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. To adjust this value for the local time zone use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553053">KeQueryPerformanceCounter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553071">KeQueryTickCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553075">KeQueryTimeIncrement</a>
 

 

