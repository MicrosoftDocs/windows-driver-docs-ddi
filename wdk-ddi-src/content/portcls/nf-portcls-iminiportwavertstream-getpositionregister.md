---
UID: NF:portcls.IMiniportWaveRTStream.GetPositionRegister
title: IMiniportWaveRTStream::GetPositionRegister (portcls.h)
description: The GetPositionRegister method retrieves the information that the port driver requires to expose the position register to the audio subsystem and its clients.
tech.root: audio
ms.date: 10/31/2018
keywords: ["IMiniportWaveRTStream::GetPositionRegister"]
ms.keywords: IMiniportWaveRTStream::GetPositionRegister, GetPositionRegister, IMiniportWaveRTStream.GetPositionRegister, IMiniportWaveRTStream::GetPositionRegister, IMiniportWaveRTStream.GetPositionRegister
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
 - IMiniportWaveRTStream::GetPositionRegister
 - portcls/IMiniportWaveRTStream::GetPositionRegister
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStream.GetPositionRegister
product:
 - Windows
---

# IMiniportWaveRTStream::GetPositionRegister


## -description

The GetPositionRegister method retrieves the information that the port driver requires to expose the position register to the audio subsystem and its clients.

## -parameters

### -param Register

Output pointer to a KSRTAUDIO_HWREGISTER structure that describes the register mapping.

## -returns

This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.

## -remarks

The WaveRT port driver calls this method in response to a KSPROPERTY_RTAUDIO_POSITIONREGISTER property request from a client.

## -see-also

[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)

