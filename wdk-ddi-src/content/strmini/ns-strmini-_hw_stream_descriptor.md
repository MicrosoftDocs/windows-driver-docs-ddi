---
UID: NS:strmini._HW_STREAM_DESCRIPTOR
title: "_HW_STREAM_DESCRIPTOR"
author: windows-driver-content
description: The minidriver uses the HW_STREAM_DESCRIPTOR structure to return stream information to the stream class driver.
old-location: stream\hw_stream_descriptor.htm
tech.root: stream
ms.assetid: ebc44350-3093-44ba-a2c9-73133fd18db7
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PHW_STREAM_DESCRIPTOR, HW_STREAM_DESCRIPTOR, HW_STREAM_DESCRIPTOR structure [Streaming Media Devices], PHW_STREAM_DESCRIPTOR, PHW_STREAM_DESCRIPTOR structure pointer [Streaming Media Devices], _HW_STREAM_DESCRIPTOR, strclass-struct_57b4a9ea-44c1-4584-94f4-060a3fa58bf1.xml, stream.hw_stream_descriptor, strmini/HW_STREAM_DESCRIPTOR, strmini/PHW_STREAM_DESCRIPTOR"
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
-	HW_STREAM_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: HW_STREAM_DESCRIPTOR, *PHW_STREAM_DESCRIPTOR
---

# _HW_STREAM_DESCRIPTOR structure


## -description


The minidriver uses the HW_STREAM_DESCRIPTOR structure to return stream information to the stream class driver.


## -struct-fields




### -field StreamHeader

Contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a> for the stream descriptor.


### -field StreamInfo

Contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a> block for the zero stream.


## -remarks



The minidriver returns this structure to the class driver in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568173">SRB_GET_STREAM_INFO</a> request. The class driver makes this request by calling the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine.

The class driver expects HW_STREAM_DESCRIPTOR to be laid out in memory as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a> followed by an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a> structures. The array begins at the address of the <b>StreamInfo</b> member. The HW_STREAM_HEADER's <b>NumberOfStreams</b> member indicates the number of entries in the array. The minidriver uses HW_STREAM_HEADER to describe those kernel streaming properties of the driver as a whole, while each HW_STREAM_INFORMATION structure describes each individual stream the device supports.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559690">HW_STREAM_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559692">HW_STREAM_INFORMATION</a>
 

 

