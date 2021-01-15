---
UID: NC:ks.PFNKSCORRELATEDTIME
title: PFNKSCORRELATEDTIME (ks.h)
description: A streaming minidriver's KStrCorrelatedTime routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time.
old-location: stream\kstrcorrelatedtime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNKSCORRELATEDTIME callback function"]
ms.keywords: KStrCorrelatedTime, KStrCorrelatedTime routine [Streaming Media Devices], PFNKSCORRELATEDTIME, ks/KStrCorrelatedTime, ksfunc_06af0f33-8ffd-4f9e-83ad-9f37f3b18f5d.xml, stream.kstrcorrelatedtime
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
 - PFNKSCORRELATEDTIME
 - ks/PFNKSCORRELATEDTIME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSCORRELATEDTIME
---

# PFNKSCORRELATEDTIME callback function


## -description

A streaming minidriver's <i>KStrCorrelatedTime</i> routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time.

## -parameters

### -param Context 

[in]
Pointer to the minidriver-supplied information context. The minidriver passes the information context to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclockex">KsAllocateDefaultClockEx</a> in the function's <i>DeferredContext</i> parameter when the minidriver allocates a custom DPC timer object.

### -param SystemTime 

[out]
Specifies a pointer to a variable that receives the performance counter frequency.

## -returns

Returns the value of the performance counter in units of ticks.

## -remarks

Typically, if a minidriver supplies a <i>KStrCorrelatedTime</i> callback function, the minidriver must also supply <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnkssettimer">KStrSetTimer</a> and <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscanceltimer">KStrCancelTimer</a> callback functions.

The minidriver-supplied <i>KStrCorrelatedTimer </i>must have the same characteristics as <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscanceltimer">KStrCancelTimer</a>



<a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscorrelatedtime">KStrCorrelatedTime</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclockex">KsAllocateDefaultClockEx</a>

