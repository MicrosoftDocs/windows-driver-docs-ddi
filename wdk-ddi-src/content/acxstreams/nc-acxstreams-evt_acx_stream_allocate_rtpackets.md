---
UID: NC:acxstreams.EVT_ACX_STREAM_ALLOCATE_RTPACKETS
tech.root: audio
title: EVT_ACX_STREAM_ALLOCATE_RTPACKETS
ms.date: 04/05/2022
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

The **EvtAcxStreamAllocateRtPackets** event tells the driver to allocate RtPackets for streaming. 

## -parameters

### -param Stream

An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PacketCount

Specifies the number of packets to be allocated. Valid values are 1 or 2. Event-driven streams will use two packets while timer-driven streams will use one packet.

### -param PacketSize

The packet size, measured in bytes.

### -param Packets

A pointer that receives a pointer to an array of [ACX_RTPACKET structures](ns-acxstreams-acx_rtpacket.md) that describes the location and size of the packets.

The initial ACX version supports only WdfMemoryDescriptorTypeMdl buffers for the ACX_RTPACKET RtPacketBuffer member. The RtPacketBuffer must be page-aligned and have a page-aligned byte count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The initial ACX version will call with PacketCount = 1 or PacketCount = 2 when the StreamModel is AcxStreamModelRtPacket. With PacketCount = 2, the driver can allocate a single buffer that is shared between the two packets or the driver can allocate two separate buffers.

If the driver allocates a single buffer to be shared across two packets, the second ACX_RTPACKET structure should have a WDF_MEMORY_DESCRIPTOR_TYPE = WdfMemoryDescriptorTypeInvalid. The RtPacketOffset for the second ACX_RTPACKET structure should be a valid offset into the RtPacketBuffer of the first ACX_RTPACKET structure and should align with the first ACX_RTPACKET structure's RtPacketOffset + RtPacketSize.

EvtAcxStreamAllocateRtPackets is called before [EvtAcxStreamPrepareHardware](nc-acxstreams-evt_acx_stream_prepare_hardware.md) to allow the RT packet allocation to occur before EvtAcxStreamPrepareHardware.

The buffer allocation typically only involves allocating system memory in such a way that it can be used with the DMA hardware. Typically, the buffer allocation will not have any effect on the streaming hardware. The prepare hardware phase is used as the driver is getting the stream ready to run, by completing tasks such as reserving bandwidth, programming DMA, and completing the preparation for the request to run the stream. Typically, the prepare hardware code will make use of the allocated buffers for preparing the DMA and related activities to be ready to start the stream.

### Example

Example usage is shown below.

```cpp
    //
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
    NTSTATUS status = STATUS_SUCCESS;
    PCODEC_STREAM_CONTEXT ctx;
    PACX_RTPACKET packets = NULL;
    PVOID packetBuffer = NULL;
    ULONG i;
    ULONG packetAllocSizeInPages = 0;
    ULONG packetAllocSizeInBytes = 0;
    ULONG firstPacketOffset = 0;
    size_t packetsSize = 0;

    PAGED_CODE();

    ctx = GetCodecStreamContext(Stream);

    if (PacketCount > 2)
    {
        status = STATUS_INVALID_PARAMETER;
        goto exit;
    }

    status = RtlSizeTMult(PacketCount, sizeof(ACX_RTPACKET), &packetsSize);
    if (!NT_SUCCESS(status)) {
        goto exit;
    }

    packets = (PACX_RTPACKET)ExAllocatePool2(POOL_FLAG_NON_PAGED, packetsSize, DRIVER_TAG);
    if (!packets) {
        status = STATUS_NO_MEMORY;
        goto exit;
    }

    // We need to allocate page-aligned buffers, to ensure no kernel memory leaks
    // to user space. Round up the packet size to page aligned, then calculate
    // the first packet's buffer offset so packet 0 ends on a page boundary and
    // packet 1 begins on a page boundary.
    status = RtlULongAdd(PacketSize, PAGE_SIZE - 1, &packetAllocSizeInPages);
    if (!NT_SUCCESS(status)) {
        goto exit;
    }
    packetAllocSizeInPages = packetAllocSizeInPages / PAGE_SIZE;
    packetAllocSizeInBytes = PAGE_SIZE * packetAllocSizeInPages;
    firstPacketOffset = packetAllocSizeInBytes - PacketSize;

    for (i = 0; i < PacketCount; ++i)
    {
        PMDL pMdl = NULL;

        ACX_RTPACKET_INIT(&packets[i]);

        packetBuffer = ExAllocatePool2(POOL_FLAG_NON_PAGED, packetAllocSizeInBytes, DRIVER_TAG);
        if (packetBuffer == NULL) {
            status = STATUS_NO_MEMORY;
            goto exit;
        }

        pMdl = IoAllocateMdl(packetBuffer, packetAllocSizeInBytes, FALSE, TRUE, NULL);
        if (pMdl == NULL) {
            status = STATUS_NO_MEMORY;
            goto exit;
        }

        MmBuildMdlForNonPagedPool(pMdl);

        WDF_MEMORY_DESCRIPTOR_INIT_MDL(
            &((packets)[i].RtPacketBuffer),
            pMdl,
            packetAllocSizeInBytes);

        packets[i].RtPacketSize = PacketSize;
        if (i == 0)
        {
            packets[i].RtPacketOffset = firstPacketOffset;
        }
        else
        {
            packets[i].RtPacketOffset = 0;
        }
        m_Packets[i] = packetBuffer;

        packetBuffer = NULL;
    }

    *Packets = packets;
    packets = NULL;
    ctx->PacketsCount = PacketCount;
    ctx->PacketSize = PacketSize;
    ctx->FirstPacketOffset = firstPacketOffset;

exit:
    if (packetBuffer)
    {
        ExFreePoolWithTag(packetBuffer, DRIVER_TAG);
    }
    if (packets)
    {
        FreeRtPackets(packets, PacketCount);
    }
    return status;
}
```


## -see-also

- [acxstreams.h header](index.md)
