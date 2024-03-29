---
UID: NF:portcls.PcGetTimeInterval
title: PcGetTimeInterval function (portcls.h)
description: The PcGetTimeInterval function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.
old-location: audio\pcgettimeinterval.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcGetTimeInterval function"]
ms.keywords: PcGetTimeInterval, PcGetTimeInterval function [Audio Devices], audio.pcgettimeinterval, audpc-routines_a68c0cf5-01b7-4e01-a719-f0bdea2d367f.xml, portcls/PcGetTimeInterval
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetTimeInterval function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - PcGetTimeInterval
 - portcls/PcGetTimeInterval
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcGetTimeInterval
---

# PcGetTimeInterval function


## -description

The <b>PcGetTimeInterval</b> function returns the time elapsed since a specified time. Time is measured in 100-nanosecond units.

## -parameters

### -param Since [in]


Specifies the time from which to measure the interval. Typically, this function is called once with a "since" of zero to get the current time, and is called subsequently with a "since" of the recorded current time to get time intervals from that time.

## -returns

<b>PcGetTimeInterval</b> returns the current time minus <i>Since</i>.

## -remarks

The value that is specified in parameter <i>Since</i> is measured in 100-nanosecond units. If <i>Since</i> is zero, the time returned is the number of 100-nanosecond ticks since January 1, 1601. The time units are the same as those used to specify the system time in the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime~r1">KeQuerySystemTime</a> function.

The following macros from portcls.h are useful for converting seconds, milliseconds, and microseconds to 100-millisecond units:

GTI_SECONDS

GTI_MILLISECONDS

GTI_MICROSECONDS

This function can be used for timing purposes by first saving the current time,


```
  ULONGLONG ullTime = PcGetTimeInterval(0);
```

and then checking to see whether the required interval has passed


```
  if (PcGetTimeInterval(ullTime) >= GTI_MILLISECONDS(5))
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime~r1">KeQuerySystemTime</a>
