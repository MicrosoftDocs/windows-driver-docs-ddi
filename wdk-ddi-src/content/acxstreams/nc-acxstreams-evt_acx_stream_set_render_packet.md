---
UID: NC:acxstreams.EVT_ACX_STREAM_SET_RENDER_PACKET
tech.root: audio
title: EVT_ACX_STREAM_SET_RENDER_PACKET
ms.date: 07/01/2021
targetos: Windows
description: The EvtAcxStreamSetRenderPacket event tells the driver which packet was just released by the client.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - EVT_ACX_STREAM_SET_RENDER_PACKET
f1_keywords:
 - EVT_ACX_STREAM_SET_RENDER_PACKET
 - acxstreams/EVT_ACX_STREAM_SET_RENDER_PACKET
dev_langs:
 - c++
---

## -description

The EvtAcxStreamSetRenderPacket event tells the driver which packet was just released by the client. 

If there are no glitches, this packet should be (CurrentRenderPacket + 1), where CurrentRenderPacket is the packet the driver is currently streaming from. The driver should continue to increase the CurrentRenderPacket as packets are rendered instead of changing its CurrentRenderPacket to match this value. The property will include the packet index (0-based) and, if appropriate, an EOS flag with the byte offset of the end of the stream in the current packet.  

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param Packet

The  packet number that was just released by the client driver. This is a one (TBD or zero?) based packet count, maintained by the TBD.

### -param Flags

Flags can be 0 or AcxStreamSetRenderPacketEndOfStream, indicating the Packet is the last packet in the stream. 

### -param EosPacketLength

The EosPacketLength is a valid length in bytes for the packet.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

TBD TBD TBD 

Do any of these return values apply here?

STATUS_DATA_LATE_ERROR – The driver returns this error if the OS passes a packet number that has already transferred or is currently transferring. In this case, a glitch condition has occurred. The driver may optionally use some of the data from the packet or continue playing out the data previously written to this packet number. 

STATUS_DATA_OVERRUN – The driver returns this error if the OS passes a packet number that is higher than can be stored in the WaveRT buffer. In this case, a glitch condition has occurred. The driver may optionally ignore the data in the packet. 

STATUS_INVALID_DEVICE_STATE – The driver returns this error if the OS calls this routine after a previously setting the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag. 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status. This includes any Flag values not specifically defined above.


TBD TBD TBD 


## -remarks

Once the stream is created and the resources are allocated, the application will call Start on the stream to start playback. Note that an application should call GetBuffer/ReleaseBuffer before starting the stream to ensure the first packet that will start playing immediately will have valid audio data.  

The client starts by pre-rolling a buffer. When the client calls ReleaseBuffer, this will translate to a call in AudioKSE that will call into the ACX layer, which will call EvtAcxStreamSetRenderPacket on the active ACXSTREAM. The property will include the packet index (0-based) and, if appropriate, an EOS flag with the byte offset of the end of the stream in the current packet.  
  
After the sink circuit finishes with a packet, it will trigger the buffer-complete notification that will release clients waiting to fill the next packet with render audio data.  

### Example

TBD - should we show more code here?

Example usage is shown below.

```cpp
// Init RT streaming callbacks.
//
ACX_RT_STREAM_CALLBACKS rtCallbacks;
ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);

rtCallbacks.EvtAcxStreamSetRenderPacket = DspR_EvtStreamSetRenderPacket;

RETURN_NTSTATUS_IF_FAILED(AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks));
```

## -see-also

[acxstreams.h header](index.md)

