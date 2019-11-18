---
UID: NF:portcls.IMiniportWaveRTStream.FreeAudioBuffer
title: IMiniportWaveRTStream::FreeAudioBuffer (portcls.h)
description: The FreeAudioBuffer method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStream::AllocateAudioBuffer.
tech.root: audio
ms.assetid: ba0f4d00-cc63-4dbd-bfb1-5d90bec6a6bd
ms.date: 10/31/2018
ms.topic: method
f1_keywords:
 - "portcls/IMiniportWaveRTStream.FreeAudioBuffer"
ms.keywords: IMiniportWaveRTStream::FreeAudioBuffer, FreeAudioBuffer, IMiniportWaveRTStream.FreeAudioBuffer, IMiniportWaveRTStream::FreeAudioBuffer, IMiniportWaveRTStream.FreeAudioBuffer
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IMiniportWaveRTStream.FreeAudioBuffer
product: 
 - Windows
targetos: Windows

---

# IMiniportWaveRTStream::FreeAudioBuffer


## -description

The FreeAudioBuffer method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStream::AllocateAudioBuffer.

## -parameters

### -param AudioBufferMdl
Specifies a memory descriptor list (MDL) previously allocated with a call to IMiniportWaveRTStream::AllocateAudioBuffer.


### -param BufferSize
Output pointer for the number of bytes that the method has written to the Attributes buffer. This parameter points to a ULONG variable into which the method writes the byte count.



## -remarks

## -see-also


[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)
