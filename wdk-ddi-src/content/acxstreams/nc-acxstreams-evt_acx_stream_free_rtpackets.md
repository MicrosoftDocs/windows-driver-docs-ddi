---
UID: NC:acxstreams.EVT_ACX_STREAM_FREE_RTPACKETS
tech.root: audio
title: EVT_ACX_STREAM_FREE_RTPACKETS
ms.date: 04/05/2022
targetos: Windows
description: The EvtAcxStreamFreeRtPackets event tells the driver to free the RtPackets that were allocated in a previous call to EvtAcxStreamAllocateRtPackets.
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
 - EVT_ACX_STREAM_FREE_RTPACKETS
f1_keywords:
 - EVT_ACX_STREAM_FREE_RTPACKETS
 - acxstreams/EVT_ACX_STREAM_FREE_RTPACKETS
dev_langs:
 - c++
---

## -description

The EvtAcxStreamFreeRtPackets event tells the driver to free the RtPackets that were allocated in a previous call to EvtAcxStreamAllocateRtPackets. The same packets from that call are included. 

## -parameters

### -param Stream

An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Packets

A pointer to an array of [ACX_RTPACKET structures](ns-acxstreams-acx_rtpacket.md) that describes the location and size of the packets to be freed.

### -param PacketCount

Specifies the number of packets to be freed. Valid values are 1 or 2.

## -remarks

When work with the stream is complete, EvtAcxStreamFreeRtPackets is called after [EvtAcxStreamReleaseHardware](nc-acxstreams-evt_acx_stream_release_hardware.md). This allows the release hardware phase to finish deallocating bandwidth, freeing DMA resources and any other associated cleanup, to occur before te allocated RT buffers are then freed.

### Example

Example usage is shown below.

```cpp
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamFreeRtPackets               = Dsp_EvtStreamFreeRtPackets;

    RETURN_NTSTATUS_IF_FAILED(AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks));

// Later in the code need to free the packets...
#pragma code_seg("PAGE")
VOID
Codec_EvtStreamFreeRtPackets(
    _In_ ACXSTREAM Stream,
    _In_ PACX_RTPACKET Packets,
    _In_ ULONG PacketCount
    )
{
    PCODEC_STREAM_CONTEXT ctx;
    ULONG i;
    PVOID buffer;

    PAGED_CODE();

    ctx = GetCodecStreamContext(Stream);

    for (i = 0; i < PacketCount; ++i)
    {
        if (Packets[i].RtPacketBuffer.u.MdlType.Mdl)
        {
            buffer = MmGetMdlVirtualAddress(Packets[i].RtPacketBuffer.u.MdlType.Mdl);
            IoFreeMdl(Packets[i].RtPacketBuffer.u.MdlType.Mdl);
            ExFreePool(buffer);
        }
    }

    ExFreePool(Packets);

    ctx->PacketsCount = 0;
    ctx->PacketSize = 0;
    ctx->FirstPacketOffset = 0;
}
```

## -see-also

[acxstreams.h header](index.md)

READY2GO

EDITCOMPLETE
