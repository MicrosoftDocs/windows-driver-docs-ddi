---
UID: NS:strmini._HW_STREAM_DESCRIPTOR
title: "_HW_STREAM_DESCRIPTOR"
author: windows-driver-content
description: The minidriver uses the HW_STREAM_DESCRIPTOR structure to return stream information to the stream class driver.
old-location: stream\hw_stream_descriptor.htm
old-project: stream
ms.assetid: ebc44350-3093-44ba-a2c9-73133fd18db7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PHW_STREAM_DESCRIPTOR, strmini/HW_STREAM_DESCRIPTOR, PHW_STREAM_DESCRIPTOR structure pointer [Streaming Media Devices], _HW_STREAM_DESCRIPTOR, strclass-struct_57b4a9ea-44c1-4584-94f4-060a3fa58bf1.xml, HW_STREAM_DESCRIPTOR structure [Streaming Media Devices], stream.hw_stream_descriptor, strmini/PHW_STREAM_DESCRIPTOR, *PHW_STREAM_DESCRIPTOR, HW_STREAM_DESCRIPTOR
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
-	HW_STREAM_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: HW_STREAM_DESCRIPTOR, *PHW_STREAM_DESCRIPTOR
req.product: Windows 10 or later.
---

# _HW_STREAM_DESCRIPTOR structure


## -description


The minidriver uses the HW_STREAM_DESCRIPTOR structure to return stream information to the stream class driver.


## -syntax


````
typedef struct _HW_STREAM_DESCRIPTOR {
  HW_STREAM_HEADER      StreamHeader;
  HW_STREAM_INFORMATION StreamInfo;
} HW_STREAM_DESCRIPTOR, *PHW_STREAM_DESCRIPTOR;
````


## -struct-fields




### -field StreamHeader

Contains the <a href="..\strmini\ns-strmini-_hw_stream_header.md">HW_STREAM_HEADER</a> for the stream descriptor.


### -field StreamInfo

Contains the <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> block for the zero stream.


## -remarks


The minidriver returns this structure to the class driver in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568173">SRB_GET_STREAM_INFO</a> request. The class driver makes this request by calling the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine.

The class driver expects HW_STREAM_DESCRIPTOR to be laid out in memory as an <a href="..\strmini\ns-strmini-_hw_stream_header.md">HW_STREAM_HEADER</a> followed by an array of <a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a> structures. The array begins at the address of the <b>StreamInfo</b> member. The HW_STREAM_HEADER's <b>NumberOfStreams</b> member indicates the number of entries in the array. The minidriver uses HW_STREAM_HEADER to describe those kernel streaming properties of the driver as a whole, while each HW_STREAM_INFORMATION structure describes each individual stream the device supports.



## -see-also

<a href="..\strmini\ns-strmini-_hw_stream_header.md">HW_STREAM_HEADER</a>

<a href="..\strmini\ns-strmini-_hw_stream_information.md">HW_STREAM_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_STREAM_DESCRIPTOR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

