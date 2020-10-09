---
UID: NC:strmini.PHW_QUERY_CLOCK_ROUTINE
title: PHW_QUERY_CLOCK_ROUTINE (strmini.h)
description: Each stream may have a clock associated to it. The class driver queries the clock by calling the stream minidriver-supplied StrMiniClock function, provided in each stream's HW_STREAM_OBJECT.
old-location: stream\strminiclock.htm
tech.root: stream
ms.assetid: ea230363-e2e8-48fb-982b-025615753e83
ms.date: 04/23/2018
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
 - StrMiniClock
---

# PHW_QUERY_CLOCK_ROUTINE callback function


## -description

Each stream may have a clock associated to it. The class driver queries the clock by calling the stream minidriver-supplied <i>StrMiniClock</i> function, provided in each stream's <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>.

## -parameters

### -param TimeContext

#### - HwTimeContext [in]

Pointer to the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a> structure that <i>StrMiniClock</i> must fill out with the requested information.

## -remarks

A stream specifies its <i>StrMiniClock</i> function within the <b>HwClockFunction</b> member of the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a> substructure of its <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>. The minidriver fills out the <b>HW_STREAM_OBJECT</b> for a stream within its <a href="/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a> routine in response to a SRB_OPEN_STREAM request.

When the class driver calls <i>StrMiniClock</i>, it fills in the <b>HwDeviceExtension</b>, <b>HwStreamObject</b>, and <b>Function</b> members of the <i>HwTimeContext</i> parameter. It expects <i>StrMiniClock</i> to fill in the <b>Time</b> member with the time value, in 100-nanosecond units, specified in the <i>Function</i> parameter. <i>StrMiniClock</i> must also fill in the <b>SystemTime</b> member with the current system time, by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a>, and converting the result to 100-nanosecond units.

The <i>StrMiniClock</i> routine must handle the functions specified in the <b>ClockSupportFlags</b> of the clock's HW_CLOCK_OBJECT. See <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a> for details.

## -see-also

<a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>