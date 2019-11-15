---
UID: NF:portcls.IMiniportWaveRTStream.GetHWLatency
title: IMiniportWaveRTStream::GetHWLatency (portcls.h)
description: The GetHWLatency method retrieves information about sources of stream latency in the audio hardware.
tech.root: audio
ms.assetid: faddde96-d13f-4f19-9370-ea756e39c6d3
ms.date: 10/31/2018
ms.topic: method
f1_keywords:
 - "portcls/IMiniportWaveRTStream.GetHWLatency"
ms.keywords: IMiniportWaveRTStream::GetHWLatency, GetHWLatency, IMiniportWaveRTStream.GetHWLatency, IMiniportWaveRTStream::GetHWLatency, IMiniportWaveRTStream.GetHWLatency
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
 - IMiniportWaveRTStream.GetHWLatency
product: 
 - Windows
targetos: Windows

---

# IMiniportWaveRTStream::GetHWLatency


## -description

The GetHWLatency method retrieves information about sources of stream latency in the audio hardware.

## -parameters

### -param hwLatency
A pointer to a KSRTAUDIO_HWLATENCY structure into which the driver writes the hardware latency parameters.


## -remarks
The port driver calls this method in response to a KSPROPERTY_RTAUDIO_HWLATENCY property request from a client.
For more information about the sources of hardware latency in an audio stream, see the Stream Latency during Playback and Stream Latency during Recording topics.

## -see-also


[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)
