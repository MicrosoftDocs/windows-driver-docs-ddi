---
UID: NF:wdm.ExSystemTimeToLocalTime
title: ExSystemTimeToLocalTime function (wdm.h)
description: The ExSystemTimeToLocalTime routine converts a GMT system time value to the local system time for the current time zone.
old-location: kernel\exsystemtimetolocaltime.htm
tech.root: kernel
ms.assetid: d77ce60e-7b23-4f60-af63-d613ceba281e
ms.date: 04/30/2018
keywords: ["ExSystemTimeToLocalTime function"]
ms.keywords: ExSystemTimeToLocalTime, ExSystemTimeToLocalTime routine [Kernel-Mode Driver Architecture], k102_9cf20274-70ae-41f6-b56f-2dc8aa7fd0e3.xml, kernel.exsystemtimetolocaltime, wdm/ExSystemTimeToLocalTime
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
 - ExSystemTimeToLocalTime
 - wdm/ExSystemTimeToLocalTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExSystemTimeToLocalTime
---

# ExSystemTimeToLocalTime function


## -description

The <b>ExSystemTimeToLocalTime</b> routine converts a GMT system time value to the local system time for the current time zone.

## -parameters

### -param SystemTime 

[in]
A pointer to a variable set to the unbiased, GMT system time.

### -param LocalTime 

[out]
A pointer to the returned value for the current locale.

## -remarks

<b>ExSystemTimeToLocalTime</b> subtracts the time-zone bias from the GMT system time value to compute the corresponding time at the current locale.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>

