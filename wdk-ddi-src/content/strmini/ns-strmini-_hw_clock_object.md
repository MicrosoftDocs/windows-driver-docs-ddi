---
UID: NS:strmini._HW_CLOCK_OBJECT
title: "_HW_CLOCK_OBJECT"
author: windows-driver-content
description: The HW_CLOCK_OBJECT structure describes the clock associated with a stream.
old-location: stream\hw_clock_object.htm
old-project: stream
ms.assetid: d6afe946-90cb-4b17-94ed-2e7c508985a3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PHW_CLOCK_OBJECT, HW_CLOCK_OBJECT, HW_CLOCK_OBJECT structure [Streaming Media Devices], PHW_CLOCK_OBJECT, PHW_CLOCK_OBJECT structure pointer [Streaming Media Devices], _HW_CLOCK_OBJECT, strclass-struct_95b6e9db-af87-415b-aad2-b3763c4dd0d9.xml, stream.hw_clock_object, strmini/HW_CLOCK_OBJECT, strmini/PHW_CLOCK_OBJECT"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	strmini.h
api_name:
-	HW_CLOCK_OBJECT
product: Windows
targetos: Windows
req.typenames: HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT
req.product: Windows 10 or later.
---

# _HW_CLOCK_OBJECT structure


## -description


The HW_CLOCK_OBJECT structure describes the clock associated with a stream.


## -syntax


````
typedef struct _HW_CLOCK_OBJECT {
  PHW_CLOCK_FUNCTION HwClockFunction;
  ULONG              ClockSupportFlags;
  ULONG              Reserved[2];
} HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT;
````


## -struct-fields




### -field HwClockFunction

Pointer to the stream's <a href="..\strmini\nc-strmini-phw_query_clock_routine.md">StrMiniClock</a> routine.


### -field ClockSupportFlags

Specifies which options the <i>StrMiniClock</i> routine supports.





#### CLOCK_SUPPORT_CAN_READ_ONBOARD_CLOCK

The <i>StrMiniClock</i> routine can return the current clock value for the stream's clock. The <i>StrMiniClock</i> routine must be able to handle a <b>Function</b> setting of TIME_READ_ONBOARD_CLOCK in the <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a> structure passed as a parameter.



#### CLOCK_SUPPORT_CAN_RETURN_STREAM_TIME

The <i>StrMiniClock</i> routine can return the current presentation time stamp for the stream. The <i>StrMiniClock</i> routine must be able to handle a <b>Function</b> setting of TIME_GET_STREAM_TIME in the <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a> structure passed as a parameter.


### -field Reserved

Reserved for system use. Do not use.


## -see-also

<a href="..\strmini\nc-strmini-phw_query_clock_routine.md">StrMiniClock</a>



<a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>



<a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_CLOCK_OBJECT structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

