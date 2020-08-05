---
UID: NS:strmini._HW_TIME_CONTEXT
title: _HW_TIME_CONTEXT (strmini.h)
description: The class driver passes an HW_TIME_CONTEXT structure as a parameter to be filled in by a stream's StrMiniClock routine, or returns a completed HW_TIME_CONTEXT structure when it responds to a StreamClassQueryMasterClock or StreamClassQueryMasterClockSync request.
old-location: stream\hw_time_context.htm
tech.root: stream
ms.assetid: 4f349089-ff50-4f69-941f-ba3e9225abec
ms.date: 04/23/2018
keywords: ["HW_TIME_CONTEXT structure"]
ms.keywords: "*PHW_TIME_CONTEXT, HW_TIME_CONTEXT, HW_TIME_CONTEXT structure [Streaming Media Devices], PHW_TIME_CONTEXT, PHW_TIME_CONTEXT structure pointer [Streaming Media Devices], _HW_TIME_CONTEXT, strclass-struct_2c3e01ab-3b53-47cb-816f-994c0b7113b0.xml, stream.hw_time_context, strmini/HW_TIME_CONTEXT, strmini/PHW_TIME_CONTEXT"
f1_keywords:
 - "strmini/HW_TIME_CONTEXT"
 - "HW_TIME_CONTEXT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- strmini.h
api_name:
- HW_TIME_CONTEXT
targetos: Windows
req.typenames: HW_TIME_CONTEXT, *PHW_TIME_CONTEXT
---

# _HW_TIME_CONTEXT structure


## -description


The class driver passes an HW_TIME_CONTEXT structure as a parameter to be filled in by a stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a> routine, or returns a completed HW_TIME_CONTEXT structure when it responds to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclocksync">StreamClassQueryMasterClockSync</a> request.


## -struct-fields




### -field HwDeviceExtension

Points to the minidriver's device extension buffer. The class driver fills in this member when it passes the structure to a stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a>, or to the callback passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a>. When passed as a parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclocksync">StreamClassQueryMasterClockSync</a>, the caller must fill in this member itself.

The minidriver may use its device extension to record private information global to the minidriver. The minidriver sets the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field HwStreamObject

When the class driver passes HW_TIME_CONTEXT to a stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a> routine, this member points to the stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a> structure.

When the class driver passes a completed HW_TIME_CONTEXT structure to the callback provided by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a>, it fills in this member with a pointer to the stream object of the stream that makes the query request.


### -field Function

Specifies the type of time value that is stored in the <b>Time</b> member. The possible values are:





#### TIME_GET_STREAM_TIME

The <b>Time</b> member holds the current presentation time stamp.



#### TIME_READ_ONBOARD_CLOCK

The <b>Time</b> member holds the current clock time.


### -field Time

The time value, in 100-nanosecond units, specified by the <b>Function</b> member.


### -field SystemTime

The current system time, in 100-nanosecond units.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_clock_object">HW_CLOCK_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_query_clock_routine">StrMiniClock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclock">StreamClassQueryMasterClock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nf-strmini-streamclassquerymasterclocksync">StreamClassQueryMasterClockSync</a>
 

 

