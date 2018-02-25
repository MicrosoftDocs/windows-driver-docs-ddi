---
UID: NS:ksmedia.KSWAVE_OUTPUT_CAPABILITIES
title: KSWAVE_OUTPUT_CAPABILITIES
author: windows-driver-content
description: The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device.
old-location: stream\kswave_output_capabilities.htm
old-project: stream
ms.assetid: 3f7d534d-bfd8-4aca-a14d-97c047fb5aeb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSWAVE_OUTPUT_CAPABILITIES, ,, A, B, C, E, I, K, KSWAVE_OUTPUT_CAPABILITIES, KSWAVE_OUTPUT_CAPABILITIES structure [Streaming Media Devices], L, O, P, PKSWAVE_OUTPUT_CAPABILITIES, PKSWAVE_OUTPUT_CAPABILITIES structure pointer [Streaming Media Devices], S, T, U, V, W, _, dvdref_7660f724-15c2-419f-a0d9-c432069547a3.xml, ksmedia/KSWAVE_OUTPUT_CAPABILITIES, ksmedia/PKSWAVE_OUTPUT_CAPABILITIES, stream.kswave_output_capabilities"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSWAVE_OUTPUT_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: KSWAVE_OUTPUT_CAPABILITIES, *PKSWAVE_OUTPUT_CAPABILITIES
---

# KSWAVE_OUTPUT_CAPABILITIES structure


## -description


The KSWAVE_OUTPUT_CAPABILITIES structure is used to describe the output capabilities of a device.


## -syntax


````
typedef struct {
  ULONG MaximumChannelsPerConnection;
  ULONG MinimumBitsPerSample;
  ULONG MaximumBitsPerSample;
  ULONG MinimumSampleFrequency;
  ULONG MaximumSampleFrequency;
  ULONG TotalConnections;
  ULONG StaticConnections;
  ULONG StreamingConnections;
  ULONG ActiveConnections;
  ULONG ActiveStaticConnections;
  ULONG ActiveStreamingConnections;
  ULONG Total3DConnections;
  ULONG Static3DConnections;
  ULONG Streaming3DConnections;
  ULONG Active3DConnections;
  ULONG ActiveStatic3DConnections;
  ULONG ActiveStreaming3DConnections;
  ULONG TotalSampleMemory;
  ULONG FreeSampleMemory;
  ULONG LargestFreeContiguousSampleMemory;
} KSWAVE_OUTPUT_CAPABILITIES, *PKSWAVE_OUTPUT_CAPABILITIES;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSWAVE_OUTPUT_CAPABILITIES structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

