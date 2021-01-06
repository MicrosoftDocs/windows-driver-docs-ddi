---
UID: NF:portcls.IMiniportWaveRTStream.GetClockRegister
title: IMiniportWaveRTStream::GetClockRegister (portcls.h)
description: The GetClockRegister method retrieves the information that the port driver requires to expose the clock register to the audio subsystem and its clients.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IMiniportWaveRTStream::GetClockRegister"]
ms.keywords: IMiniportWaveRTStream::GetClockRegister, GetClockRegister, IMiniportWaveRTStream.GetClockRegister, IMiniportWaveRTStream::GetClockRegister, IMiniportWaveRTStream.GetClockRegister
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
targetos: Windows
f1_keywords:
 - IMiniportWaveRTStream::GetClockRegister
 - portcls/IMiniportWaveRTStream::GetClockRegister
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStream.GetClockRegister
product:
 - Windows
---

# IMiniportWaveRTStream::GetClockRegister


## -description

The GetClockRegister method retrieves the information that the port driver requires to expose the clock register to the audio subsystem and its clients.

## -parameters

### -param Register

Output pointer to a KSRTAUDIO_HWREGISTER structure that describes the register mapping.

## -returns

This method returns NTSTATUS which contains a status value of STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

The port driver calls this method in response to a KSPROPERTY_RTAUDIO_CLOCKREGISTER property request from a client.

A clock register is a counter that increments at the frequency of the internal hardware clock that drives the internal bus of the audio device.The register increments by one with each tick of the clock. The register begins counting when the device powers on, and it continues to run until the device powers off. The clock register is used by software to synchronize two or more devices with independent hardware clocks.

## -see-also

[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)

