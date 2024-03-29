---
UID: NF:wdm.ExLocalTimeToSystemTime
title: ExLocalTimeToSystemTime function (wdm.h)
description: The ExLocalTimeToSystemTime routine converts a system time value for the current time zone to an unbiased, GreenGMT value.
old-location: kernel\exlocaltimetosystemtime.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExLocalTimeToSystemTime function"]
ms.keywords: ExLocalTimeToSystemTime, ExLocalTimeToSystemTime routine [Kernel-Mode Driver Architecture], k102_f7743a3b-822e-433e-bdf2-d7bf4ef606f5.xml, kernel.exlocaltimetosystemtime, wdm/ExLocalTimeToSystemTime
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExLocalTimeToSystemTime
 - wdm/ExLocalTimeToSystemTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExLocalTimeToSystemTime
---

# ExLocalTimeToSystemTime function


## -description

The <b>ExLocalTimeToSystemTime</b> routine converts a system time value for the current time zone to an unbiased, GreenGMT value.

## -parameters

### -param LocalTime [in]


A pointer to a variable set to the locale-specific time.

### -param SystemTime [out]


A pointer to the returned value for GMT system time.

## -remarks

<b>ExLocalTimeToSystemTime</b> adds the time-zone bias at the current locale to compute the corresponding GMT system time value.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>
