---
UID: NC:strmini.PHW_QUERY_CLOCK_ROUTINE
title: PHW_QUERY_CLOCK_ROUTINE (strmini.h)
description: Each stream may have a clock associated to it. The class driver queries the clock by calling the stream minidriver-supplied StrMiniClock function, provided in each stream's HW_STREAM_OBJECT.
tech.root: stream
ms.date: 04/22/2022
keywords: ["PHW_QUERY_CLOCK_ROUTINE callback function"]
ms.keywords: PHW_QUERY_CLOCK_ROUTINE, StrMiniClock, StrMiniClock routine [Streaming Media Devices], stream.strminiclock, strmini-routines_d53b0cf1-3c0c-435f-bc44-732f6418ebb8.xml, strmini/StrMiniClock
req.header: strmini.h
req.include-header: Strmini.h
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
 - PHW_QUERY_CLOCK_ROUTINE
 - strmini/PHW_QUERY_CLOCK_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - strmini.h
api_name:
 - PHW_QUERY_CLOCK_ROUTINE
---

## -description

Each stream may have a clock associated to it. The class driver queries the clock by calling the stream minidriver-supplied *StrMiniClock* function, provided in each stream's [HW_STREAM_OBJECT](./ns-strmini-_hw_stream_object.md).

## -parameters

### -param TimeContext [in]

Pointer to the [HW_TIME_CONTEXT](./ns-strmini-_hw_time_context.md) structure that *StrMiniClock* must fill out with the requested information.

## -remarks

A stream specifies its *StrMiniClock* function within the **HwClockFunction** member of the [HW_CLOCK_OBJECT](./ns-strmini-_hw_clock_object.md) substructure of its [HW_STREAM_OBJECT](./ns-strmini-_hw_stream_object.md). The minidriver fills out the **HW_STREAM_OBJECT** for a stream within its [StrMiniReceiveDevicePacket](./nc-strmini-phw_receive_device_srb.md) routine in response to a SRB_OPEN_STREAM request.

When the class driver calls *StrMiniClock*, it fills in the **HwDeviceExtension**, **HwStreamObject**, and **Function** members of the *TimeContext* parameter. It expects *StrMiniClock* to fill in the **Time** member with the time value, in 100-nanosecond units, specified in the *Function* parameter. *StrMiniClock* must also fill in the **SystemTime** member with the current system time, by calling [KeQueryPerformanceCounter](../ntifs/nf-ntifs-kequeryperformancecounter.md), and converting the result to 100-nanosecond units.

The *StrMiniClock* routine must handle the functions specified in the **ClockSupportFlags** of the clock's HW_CLOCK_OBJECT. See [HW_CLOCK_OBJECT](./ns-strmini-_hw_clock_object.md) for details.

## -see-also

[HW_CLOCK_OBJECT](./ns-strmini-_hw_clock_object.md)

[HW_TIME_CONTEXT](./ns-strmini-_hw_time_context.md)