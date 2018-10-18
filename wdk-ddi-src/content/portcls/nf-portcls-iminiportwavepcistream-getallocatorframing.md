---
UID: NF:portcls.IMiniportWavePciStream.GetAllocatorFraming
title: IMiniportWavePciStream::GetAllocatorFraming
author: windows-driver-content
description: The GetAllocatorFraming method gets the preferred allocator-framing parameters for the stream.
old-location: audio\iminiportwavepcistream_getallocatorframing.htm
tech.root: audio
ms.assetid: 0b140ddc-52b5-4aee-afeb-5b2be57fe7b7
ms.date: 5/8/2018
ms.keywords: GetAllocatorFraming, GetAllocatorFraming method [Audio Devices], GetAllocatorFraming method [Audio Devices],IMiniportWavePciStream interface, IMiniportWavePciStream interface [Audio Devices],GetAllocatorFraming method, IMiniportWavePciStream.GetAllocatorFraming, IMiniportWavePciStream::GetAllocatorFraming, audio.iminiportwavepcistream_getallocatorframing, audmp-routines_aef1d53f-2db6-4372-90fa-fb501c199e41.xml, portcls/IMiniportWavePciStream::GetAllocatorFraming
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWavePciStream.GetAllocatorFraming
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::GetAllocatorFraming


## -description


The <code>GetAllocatorFraming</code> method gets the preferred allocator-framing parameters for the stream.


## -parameters




### -param AllocatorFraming [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a> structure into which the method writes the miniport driver's allocator-framing preferences for this stream.


## -returns



<code>GetAllocatorFraming</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The miniport driver should not assume that the actual allocator-framing parameters for the stream match those specified in the <code>GetAllocatorFraming</code> call. The port driver interprets the allocation-framing parameters from the <code>GetAllocatorFraming</code> as the miniport driver's preferences. Other factors might outweigh these preferences, however, when the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">SysAudio system driver</a> builds the audio filter graph.

See the discussion of allocator framing in <a href="https://msdn.microsoft.com/6d83c015-cf8f-40b4-bf28-de865a5bfe2d">WavePci Latency</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536725">IMiniportWavePciStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>
 

 

