---
UID: NC:acxstreams.EVT_ACX_STREAM_SET_RENDER_PACKET
tech.root: audio
title: EVT_ACX_STREAM_SET_RENDER_PACKET
ms.date: 07/17/2024
targetos: Windows
description: The EvtAcxStreamSetRenderPacket event tells the driver which packet was just released by the client.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **EvtAcxStreamSetRenderPacket** event tells the driver which packet was just released by the client.

If there are no glitches, this packet should be (CurrentRenderPacket + 1), where CurrentRenderPacket is the packet the driver is currently streaming from. The driver should continue to increase the CurrentRenderPacket as packets are rendered instead of changing its CurrentRenderPacket to match this value. The property will include the packet index (0-based) and, if appropriate, an EOS flag with the byte offset of the end of the stream in the current packet.

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Packet

The number of the packet written by the OS to the WaveRT buffer. Depending on the values provided by the driver to [AcxRtStreamNotifyPacketComplete](nf-acxstreams-acxrtstreamnotifypacketcomplete.md), the Packet number may skip values.

### -param Flags

Flags can be 0 or `KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM = 0x200`, indicating the Packet is the last packet in the stream, and EosPacketLength is a valid length in bytes for the packet. For more information see _OptionsFlags_ in [KSSTREAM_HEADER structure (ks.h)](/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header).

### -param EosPacketLength

The length of the EOS packet if `KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM = 0x200` is specified in Flags. Zero is a valid value. If `KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM`  is not specified in Flags, this parameter should be ignored. The EosPacketLength is measured in bytes.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

STATUS_DATA_LATE_ERROR – The driver returns this error if the OS passes a packet number that has already transferred or is currently transferring. In this case, a glitch condition has occurred. The driver may optionally use some of the data from the packet or continue playing out the data previously written to this packet number.

STATUS_DATA_OVERRUN – The driver returns this error if the OS passes a packet number that is higher than can be stored in the WaveRT buffer. In this case, a glitch condition has occurred. The driver may optionally ignore the data in the packet.

STATUS_INVALID_DEVICE_STATE – The driver returns this error if the OS calls this routine after previously setting the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag.

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status. This includes any Flag values not specifically defined above.

## -remarks

After the OS calls this routine, the driver may optionally use the provided information to optimize the hardware transfer. For example, the driver might optimize DMA transfers, or program hardware to stop transfer at the end of the specified packet in case the OS does not call this routine again to inform the driver of another packet. This can mitigate audible effects of underflow, for example introducing an audible gap rather than repeating a circular buffer. The driver however is still obligated to increase its internal packet counter and signal notification events at a nominal real time rate.

Depending on hardware capabilities, if the KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM flag is specified, the driver may silence-fill a portion of the WaveRT buffer that follows the EOS packet in case the hardware transfers data beyond the EOS position.

The client starts by pre-rolling a buffer. When the client calls ReleaseBuffer, this will translate to a call in AudioKSE that will call into the ACX layer, which will call EvtAcxStreamSetRenderPacket on the active ACXSTREAM. The property will include the packet index (0-based) and, if appropriate, an EOS flag with the byte offset of the end of the stream in the current packet.  
  
### Example

Example usage is shown below.

```cpp
    //
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);

    rtCallbacks.EvtAcxStreamSetRenderPacket = EvtStreamSetRenderPacket;

    status = AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks);
```

```cpp
#pragma code_seg("PAGE")
NTSTATUS
EvtStreamSetRenderPacket(
    _In_ ACXSTREAM Stream,
    _In_ ULONG     Packet,
    _In_ ULONG     Flags,
    _In_ ULONG     EosPacketLength
    )
{
    PSTREAM_CONTEXT ctx;
    NTSTATUS        status = STATUS_SUCCESS;

    PAGED_CODE();

    ctx = GetStreamContext(Stream);

    currentPacket = (ULONG)InterlockedCompareExchange((LONG*)&ctx->m_CurrentPacket, -1, -1);

    if (Packet <= currentPacket)
    {
        status = STATUS_DATA_LATE_ERROR;
    }
    else if (Packet > currentPacket + 1)
    {
        status = STATUS_DATA_OVERRUN;
    }

    return status;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
