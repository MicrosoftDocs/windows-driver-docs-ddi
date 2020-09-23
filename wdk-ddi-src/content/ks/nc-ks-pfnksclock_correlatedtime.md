---
UID: NC:ks.PFNKSCLOCK_CORRELATEDTIME
title: PFNKSCLOCK_CORRELATEDTIME (ks.h)
description: The routine is a system-supplied routine that retrieves and the following:KStrClockGetCorrelatedTime is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot.KStrClockGetCorrelatedPhysicalTime is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.
old-location: stream\kstrclockgetcorrelatedtime.htm
tech.root: stream
ms.assetid: 1fc71718-a1fb-4e82-9805-7830e761cd6d
ms.date: 04/23/2018
keywords: ["PFNKSCLOCK_CORRELATEDTIME callback function"]
ms.keywords: KStrClockGetCorrelatedPhysicalTime, KStrClockGetCorrelatedTime, PFNKSCLOCK_CORRELATEDTIME, SystemCorrelatedTime, SystemCorrelatedTime routine [Streaming Media Devices], ks/SystemCorrelatedTime, ksfunc_dd229adf-e2be-44ac-bda2-f947b0f559a3.xml, stream.kstrclockgetcorrelatedtime
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSCLOCK_CORRELATEDTIME
 - ks/PFNKSCLOCK_CORRELATEDTIME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - SystemCorrelatedTime
---

# PFNKSCLOCK_CORRELATEDTIME callback function


## -description

The routine 
      is a system-supplied routine that retrieves  and the following:

<i>KStrClockGetCorrelatedTime</i> is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot.

<i>KStrClockGetCorrelatedPhysicalTime</i> is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.

## -parameters

### -param FileObject 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure to which a handle was returned when the clock instance was created.

### -param SystemTime 

[out]
A pointer to a 64-bit integer containing the number of clock ticks since system boot.

## -returns

This routine returns the current system time as a value of type LONGLONG. This value is specified in 100 nanosecond units.

## -remarks

You can obtain an entry point for this routine by supplying a driver-allocated <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksclock_functiontable">KSCLOCK_FUNCTIONTABLE</a> structure in a <a href="/windows-hardware/drivers/stream/ksproperty-clock-functiontable">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request.

The system time is acquired from <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>.

Both time values are specified in 100 nanosecond units.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksclock_functiontable">KSCLOCK_FUNCTIONTABLE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kscorrelated_time">KSCORRELATED_TIME</a>



<a href="/windows-hardware/drivers/stream/ksproperty-clock-functiontable">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>