---
UID: NF:portcls.IMiniportWaveRTStream.SetState
title: IMiniportWaveRTStream::SetState (portcls.h)
description: The SetState method changes the transport state of the audio stream.
tech.root: audio
ms.date: 09/29/2020
keywords: ["IMiniportWaveRTStream::SetState"]
ms.keywords: IMiniportWaveRTStream::SetState, SetState, IMiniportWaveRTStream.SetState, IMiniportWaveRTStream::SetState, IMiniportWaveRTStream.SetState
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
 - IMiniportWaveRTStream::SetState
 - portcls/IMiniportWaveRTStream::SetState
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStream::SetState
product:
 - Windows
---

# IMiniportWaveRTStream::SetState


## -description

The SetState method changes the transport state of the audio stream.

## -parameters

### -param State

[in]

Specifies the new state of the stream. This parameter is a [KSSTATE](../ks/ne-ks-ksstate.md) enumeration value.

## -returns

SetState returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

For most driver implementations, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable.

Transitions always occur in one of the following two sequences:

- STOP → ACQUIRE → PAUSE → RUN

- RUN → PAUSE → ACQUIRE → STOP

The [IMiniportWaveRT::NewStream](nf-portcls-iminiportwavert-newstream.md) method sets the initial state of the stream to KSSTATE_STOP.

## -see-also

[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)

[IMiniportWaveRT::NewStream](nf-portcls-iminiportwavert-newstream.md)

[KSSTATE](../ks/ne-ks-ksstate.md)

