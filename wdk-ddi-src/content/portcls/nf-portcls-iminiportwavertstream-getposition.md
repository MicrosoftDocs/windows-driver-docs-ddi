---
UID: NF:portcls.IMiniportWaveRTStream.GetPosition
title: IMiniportWaveRTStream::GetPosition
author: windows-driver-content
description: The GetPosition method retrieves the current play or record position as a byte offset from the beginning of the buffer.
tech.root: audio
ms.assetid: f5d1cef6-64ab-478e-9ad9-6f3b84633f99
ms.author: windowsdriverdev
ms.date: 10/31/2018
ms.topic: method
ms.keywords: IMiniportWaveRTStream::GetPosition, GetPosition, IMiniportWaveRTStream.GetPosition, IMiniportWaveRTStream::GetPosition, IMiniportWaveRTStream.GetPosition
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL or DISPATCH_LEVEL.
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
 - IMiniportWaveRTStream.GetPosition
product: 
 - Windows
targetos: Windows

---

# IMiniportWaveRTStream::GetPosition


## -description

The GetPosition method retrieves the current play or record position as a byte offset from the beginning of the buffer.

## -parameters

### -param Position
Pointer to a KSAUDIO_POSITION structure. For a wave rendering stream, the method writes the write position and the play position into this structure. For a wave-capture stream, the method writes the read position and the record position into the structure. Positions are specified as byte offsets from the beginning of the cyclic buffer.

## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.

## -remarks

The WaveRT port driver calls this method in response to a KSPROPERTY_AUDIO_POSITION property request from a client.

## -see-also

[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)