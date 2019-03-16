---
UID: NS:ksmedia.__unnamed_struct_50
title: KSWAVE_OUTPUT_CAPABILITIES (ksmedia.h)
description: The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device.
old-location: stream\kswave_output_capabilities.htm
tech.root: stream
ms.assetid: 3f7d534d-bfd8-4aca-a14d-97c047fb5aeb
ms.date: 04/23/2018
ms.keywords: "*PKSWAVE_OUTPUT_CAPABILITIES, KSWAVE_OUTPUT_CAPABILITIES, KSWAVE_OUTPUT_CAPABILITIES structure [Streaming Media Devices], PKSWAVE_OUTPUT_CAPABILITIES, PKSWAVE_OUTPUT_CAPABILITIES structure pointer [Streaming Media Devices], dvdref_7660f724-15c2-419f-a0d9-c432069547a3.xml, ksmedia/KSWAVE_OUTPUT_CAPABILITIES, ksmedia/PKSWAVE_OUTPUT_CAPABILITIES, stream.kswave_output_capabilities"
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- KSWAVE_OUTPUT_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: KSWAVE_OUTPUT_CAPABILITIES, *PKSWAVE_OUTPUT_CAPABILITIES
---

# KSWAVE_OUTPUT_CAPABILITIES structure


## -description


The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device.


## -struct-fields




### -field MaximumChannelsPerConnection

Specifies the maximum number of channels per connection.


### -field MinimumBitsPerSample

Specifies the minimum bits per sample.


### -field MaximumBitsPerSample

Specifies the maximum bits per sample.


### -field MinimumSampleFrequency

Specifies the minimum sampling frequency.


### -field MaximumSampleFrequency

Specifies the maximum sampling frequency.


### -field TotalConnections

Indicates the total number of connections.


### -field StaticConnections

Indicates the number of static connections.


### -field StreamingConnections

Indicates the number of streaming connections.


### -field ActiveConnections

Indicates the number of active connections.


### -field ActiveStaticConnections

Indicates the number of active static connections.


### -field ActiveStreamingConnections

Indicates the number of active streaming connections.


### -field Total3DConnections

Indicates the total number of 3D connections.


### -field Static3DConnections

Indicates the number of static 3D connections.


### -field Streaming3DConnections

Indicates the number of streaming 3D connections.


### -field Active3DConnections

Indicates the number of active 3D connections.


### -field ActiveStatic3DConnections

Indicates the number of static 3D connections.


### -field ActiveStreaming3DConnections

Indicates the number of streaming 3D connections.


### -field TotalSampleMemory

Specifies the total amount of sample memory.


### -field FreeSampleMemory

Specifies the available free sample memory.


### -field LargestFreeContiguousSampleMemory

Specifies the largest, free contiguous amount of sample memory.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566523">KSPROPERTY_WAVE_OUTPUT_CAPABILITIES</a> property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566523">KSPROPERTY_WAVE_OUTPUT_CAPABILITIES</a>
 

 

