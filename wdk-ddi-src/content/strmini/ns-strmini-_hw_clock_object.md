---
UID: NS:strmini._HW_CLOCK_OBJECT
title: _HW_CLOCK_OBJECT (strmini.h)
description: The HW_CLOCK_OBJECT structure describes the clock associated with a stream.
old-location: stream\hw_clock_object.htm
tech.root: stream
ms.assetid: d6afe946-90cb-4b17-94ed-2e7c508985a3
ms.date: 04/23/2018
keywords: ["HW_CLOCK_OBJECT structure"]
ms.keywords: "*PHW_CLOCK_OBJECT, HW_CLOCK_OBJECT, HW_CLOCK_OBJECT structure [Streaming Media Devices], PHW_CLOCK_OBJECT, PHW_CLOCK_OBJECT structure pointer [Streaming Media Devices], _HW_CLOCK_OBJECT, strclass-struct_95b6e9db-af87-415b-aad2-b3763c4dd0d9.xml, stream.hw_clock_object, strmini/HW_CLOCK_OBJECT, strmini/PHW_CLOCK_OBJECT"
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
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
req.typenames: HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT
f1_keywords:
 - _HW_CLOCK_OBJECT
 - strmini/_HW_CLOCK_OBJECT
 - PHW_CLOCK_OBJECT
 - strmini/PHW_CLOCK_OBJECT
 - HW_CLOCK_OBJECT
 - strmini/HW_CLOCK_OBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - strmini.h
api_name:
 - HW_CLOCK_OBJECT
---

# _HW_CLOCK_OBJECT structure


## -description

The HW_CLOCK_OBJECT structure describes the clock associated with a stream.

## -struct-fields

### -field HwClockFunction

Pointer to the stream's <a href="/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a> routine.

### -field ClockSupportFlags

Specifies which options the <i>StrMiniClock</i> routine supports.





#### CLOCK_SUPPORT_CAN_READ_ONBOARD_CLOCK

The <i>StrMiniClock</i> routine can return the current clock value for the stream's clock. The <i>StrMiniClock</i> routine must be able to handle a <b>Function</b> setting of TIME_READ_ONBOARD_CLOCK in the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a> structure passed as a parameter.



#### CLOCK_SUPPORT_CAN_RETURN_STREAM_TIME

The <i>StrMiniClock</i> routine can return the current presentation time stamp for the stream. The <i>StrMiniClock</i> routine must be able to handle a <b>Function</b> setting of TIME_GET_STREAM_TIME in the <a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a> structure passed as a parameter.

### -field Reserved

Reserved for system use. Do not use.

## -see-also

<a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a>