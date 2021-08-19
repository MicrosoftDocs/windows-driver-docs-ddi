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

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

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

