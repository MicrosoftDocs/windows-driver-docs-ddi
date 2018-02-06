---
UID: NS:strmini._HW_TIME_CONTEXT
title: "_HW_TIME_CONTEXT"
author: windows-driver-content
description: The class driver passes an HW_TIME_CONTEXT structure as a parameter to be filled in by a stream's StrMiniClock routine, or returns a completed HW_TIME_CONTEXT structure when it responds to a StreamClassQueryMasterClock or StreamClassQueryMasterClockSync request.
old-location: stream\hw_time_context.htm
old-project: stream
ms.assetid: 4f349089-ff50-4f69-941f-ba3e9225abec
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: HW_TIME_CONTEXT, strclass-struct_2c3e01ab-3b53-47cb-816f-994c0b7113b0.xml, HW_TIME_CONTEXT structure [Streaming Media Devices], _HW_TIME_CONTEXT, strmini/HW_TIME_CONTEXT, PHW_TIME_CONTEXT, PHW_TIME_CONTEXT structure pointer [Streaming Media Devices], *PHW_TIME_CONTEXT, stream.hw_time_context, strmini/PHW_TIME_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	strmini.h
apiname:
-	HW_TIME_CONTEXT
product: Windows
targetos: Windows
req.typenames: HW_TIME_CONTEXT, *PHW_TIME_CONTEXT
req.product: Windows 10 or later.
---

# _HW_TIME_CONTEXT structure


## -description


The class driver passes an HW_TIME_CONTEXT structure as a parameter to be filled in by a stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a> routine, or returns a completed HW_TIME_CONTEXT structure when it responds to a <a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a> or <a href="..\strmini\nf-strmini-streamclassquerymasterclocksync.md">StreamClassQueryMasterClockSync</a> request.


## -syntax


````
typedef struct _HW_TIME_CONTEXT {
  struct _HW_DEVICE_EXTENSION  *HwDeviceExtension;
  struct _HW_STREAM_OBJECT  *HwStreamObject;
  TIME_FUNCTION               Function;
  ULONGLONG                   Time;
  ULONGLONG                   SystemTime;
} HW_TIME_CONTEXT, *PHW_TIME_CONTEXT;
````


## -struct-fields




### -field _HW_DEVICE_EXTENSION

 


### -field HwDeviceExtension

Points to the minidriver's device extension buffer. The class driver fills in this member when it passes the structure to a stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a>, or to the callback passed to <a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a>. When passed as a parameter to <a href="..\strmini\nf-strmini-streamclassquerymasterclocksync.md">StreamClassQueryMasterClockSync</a>, the caller must fill in this member itself.

The minidriver may use its device extension to record private information global to the minidriver. The minidriver sets the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, and <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field _HW_STREAM_OBJECT

 


### -field HwStreamObject

When the class driver passes HW_TIME_CONTEXT to a stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a> routine, this member points to the stream's <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a> structure.

When the class driver passes a completed HW_TIME_CONTEXT structure to the callback provided by <a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a>, it fills in this member with a pointer to the stream object of the stream that makes the query request.


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

<a href="..\strmini\nf-strmini-streamclassquerymasterclock.md">StreamClassQueryMasterClock</a>

<a href="..\strmini\nf-strmini-streamclassquerymasterclocksync.md">StreamClassQueryMasterClockSync</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a>

<a href="..\strmini\ns-strmini-_hw_clock_object.md">HW_CLOCK_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_TIME_CONTEXT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

