---
UID: NF:wdm.RtlTimeFieldsToTime
title: RtlTimeFieldsToTime function (wdm.h)
description: The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value.
old-location: kernel\rtltimefieldstotime.htm
tech.root: kernel
ms.assetid: 5873b627-6ef4-4e2c-8a53-921f37b729bc
ms.date: 04/30/2018
keywords: ["RtlTimeFieldsToTime function"]
ms.keywords: RtlTimeFieldsToTime, RtlTimeFieldsToTime routine [Kernel-Mode Driver Architecture], k109_9b5d67de-92c3-4fb7-bcd7-4e045ae9ada4.xml, kernel.rtltimefieldstotime, wdm/RtlTimeFieldsToTime
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
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlTimeFieldsToTime
 - wdm/RtlTimeFieldsToTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlTimeFieldsToTime
---

# RtlTimeFieldsToTime function


## -description

The <b>RtlTimeFieldsToTime</b> routine converts <b>TIME_FIELDS</b> information to a system time value.

## -parameters

### -param TimeFields 

[in]
Pointer to the following structure, containing the time information to be converted:


```cpp
typedef struct TIME_FIELDS {
    CSHORT Year;
    CSHORT Month;
    CSHORT Day;
    CSHORT Hour;
    CSHORT Minute;
    CSHORT Second;
    CSHORT Milliseconds;
    CSHORT Weekday;
} TIME_FIELDS;
```





#### Year

Specifies a value from 1601 on.



#### Month

Specifies a value from 1 to 12.



#### Day

Specifies a value from 1 to 31.



#### Hour

Specifies a value from 0 to 23.



#### Minute

Specifies a value from 0 to 59.



#### Second

Specifies a value from 0 to 59.



#### Milliseconds

Specifies a value from 0 to 999.



#### Weekday

Specifies a value from 0 to 6 (Sunday to Saturday).

### -param Time 

[out]
Pointer to a buffer, which is to contain the converted system time value as a large integer.

## -returns

<b>RtlTimeFieldsToTime</b> returns <b>TRUE</b> if the input <i>TimeFields</i> data was successfully converted.

## -remarks

<b>RtlTimeFieldsToTime</b> ignores the <b>Weekday</b> value in <i>TimeFields</i>.

Callers of <b>RtlTimeFieldsToTime</b> can be running at any IRQL if both input buffers are resident.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>

