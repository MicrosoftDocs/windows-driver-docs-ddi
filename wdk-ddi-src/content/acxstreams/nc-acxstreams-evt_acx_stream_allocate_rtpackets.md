---
UID: NC:acxstreams.EVT_ACX_STREAM_ALLOCATE_RTPACKETS
tech.root: audio
title: EVT_ACX_STREAM_ALLOCATE_RTPACKETS
ms.date: 07/08/2021
targetos: Windows
description: The EvtAcxStreamAllocateRtPackets event tells the driver to allocate RtPackets for streaming.
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
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - EVT_ACX_STREAM_ALLOCATE_RTPACKETS
f1_keywords:
 - EVT_ACX_STREAM_ALLOCATE_RTPACKETS
 - acxstreams/EVT_ACX_STREAM_ALLOCATE_RTPACKETS
dev_langs:
 - c++
---

## -description

The EvtAcxStreamAllocateRtPackets event tells the driver to allocate RtPackets for streaming. 

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PacketCount

The number of packets in (since?) a TBD. This is 0/1 TBD based count.

### -param PacketSize

The packet size, measured in bytes.

### -param Packets

A pointer to a [ACX_RTPACKET structure](ns-acxstreams-acx_rtpacket.md) that describes the location and size of the packets.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The initial ACX version will call with PacketCount = 2 when the StreamModel is AcxStreamModelRtPacket. If the driver uses a single buffer for both packets, the RtPacketBuffer should be the same for both. 

### Example

Example usage is shown below.

TBD - Please review code snip

```cpp
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamAllocateRtPackets       = Codec_EvtStreamAllocateRtPackets;

...

#pragma code_seg("PAGE")
NTSTATUS
Codec_EvtStreamAllocateRtPackets(
    _In_ ACXSTREAM Stream,
    _In_ ULONG PacketCount,
    _In_ ULONG PacketSize,
    _Out_ PACX_RTPACKET *Packets
    )
{
    PCODEC_STREAM_CONTEXT ctx;
    CStreamEngine * streamEngine = NULL;

    PAGED_CODE();

    ctx = GetCodecStreamContext(Stream);

    streamEngine = (CStreamEngine*)ctx->StreamEngine;

    return streamEngine->AllocateRtPackets(PacketCount, PacketSize, Packets);
}
```


## -see-also

[acxstreams.h header](index.md)

