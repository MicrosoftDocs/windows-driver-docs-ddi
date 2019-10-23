---
UID: NF:wdm.ExLocalTimeToSystemTime
title: ExLocalTimeToSystemTime function (wdm.h)
description: The ExLocalTimeToSystemTime routine converts a system time value for the current time zone to an unbiased, GreenGMT value.
old-location: kernel\exlocaltimetosystemtime.htm
tech.root: kernel
ms.assetid: ef4fcb57-2960-4cd3-9abc-f8c5bc46e1a3
ms.date: 04/30/2018
ms.keywords: ExLocalTimeToSystemTime, ExLocalTimeToSystemTime routine [Kernel-Mode Driver Architecture], k102_f7743a3b-822e-433e-bdf2-d7bf4ef606f5.xml, kernel.exlocaltimetosystemtime, wdm/ExLocalTimeToSystemTime
ms.topic: function
f1_keywords:
 - "wdm/ExLocalTimeToSystemTime"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExLocalTimeToSystemTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExLocalTimeToSystemTime function


## -description


The <b>ExLocalTimeToSystemTime</b> routine converts a system time value for the current time zone to an unbiased, GreenGMT value.


## -parameters




### -param LocalTime [in]

A pointer to a variable set to the locale-specific time.


### -param SystemTime [out]

A pointer to the returned value for GMT system time.


## -returns



None




## -remarks



<b>ExLocalTimeToSystemTime</b> adds the time-zone bias at the current locale to compute the corresponding GMT system time value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>
 

 

