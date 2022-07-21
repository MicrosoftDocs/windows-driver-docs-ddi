---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_CAPTURE_PACKET
tech.root: audio
title: EVT_ACX_STREAM_GET_CAPTURE_PACKET
ms.date: 01/25/2022
targetos: Windows
description: The EvtAcxStreamGetCapturePacket tells the driver to indicate which packet (0-based) was completely filled most recently, including the QPC value at the time the driver started filling the packet. 
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
 - EVT_ACX_STREAM_GET_CAPTURE_PACKET
f1_keywords:
 - EVT_ACX_STREAM_GET_CAPTURE_PACKET
 - acxstreams/EVT_ACX_STREAM_GET_CAPTURE_PACKET
dev_langs:
 - c++
---

## -description

The EvtAcxStreamGetCapturePacket tells the driver to indicate which packet (0-based) was completely filled most recently, including the QPC value at the time the driver started filling the packet. 

## -parameters

### -param Stream

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param LastCapturePacket

A value indicating the position of the last captured packet. This is a 0-based index indicating how many complete packets of data have been captured. 

### -param QPCPacketStart

A value indicating the start time of the last captured packet. 

### -param MoreData

Returns TRUE if there is more data ready immediately. The OS may optionally immediately call this routine again after processing the packet to get the next packet information. If the driver returns FALSE, then capture is operating at real time.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Before reading captured audio data from the audio buffer, the OS calls this routine to get information about the available data.

The packet number identifies a packet within the stream. This resets to zero when [EVT_ACX_STREAM_RELEASEHARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md) has been called for the stream. The number advances with each captured buffer. From the packet number the OS can derive the packet location within the audio buffer and can also derive the stream position of the packet relative to start of stream.

The OS may call this routine at any time. In normal operation, the OS calls this routine after the driver calls [AcxRtStreamNotifyPacketComplete](/windows-hardware/drivers/ddi/acxstreams/nf-acxstreams-acxrtstreamnotifypacketcomplete) or after a previous call returns true for MoreData. When the OS calls this routine, the driver may assume that the OS has finished reading all previous packets. If the hardware has captured enough data, the driver may immediately burst the next complete packet to the audio buffer and call AcxRtStreamNotifyPacketComplete again. In the case of capture overflow (when the OS does not read data quickly enough) the audio driver may drop or overwrite some audio data. The audio driver drops or overwrites oldest data first. The audio driver may continue to advance its internal packet counter even though the OS may not have read the data.

### Example

Example usage is shown below.

```cpp
#pragma code_seg("PAGE")
NTSTATUS
CodecC_EvtStreamGetCapturePacket(
    _In_ ACXSTREAM          Stream,
    _Out_ ULONG           * LastCapturePacket,
    _Out_ ULONGLONG       * QPCPacketStart,
    _Out_ BOOLEAN         * MoreData
)
{
    PCODEC_STREAM_CONTEXT ctx;
    CCaptureStreamEngine* streamEngine = nullptr;
    ULONG currentPacket;
    LONGLONG qpcPacketStart;

    PAGED_CODE();

    ctx = GetCodecStreamContext(Stream);
    // Retrieve the current packet that is being written to by the audio hardware
    currentPacket = (ULONG)InterlockedCompareExchange((LONG*)&ctx->CurrentPacket, -1, -1);
    qpcPacketStart = InterlockedCompareExchange64(&ctx->LastPacketStart.QuadPart, -1, -1);

    // The Last capture packet is the packet before the current packet.
    *LastCapturePacket = currentPacket - 1;
    *QPCPacketStart = (ULONGLONG)qpcPacketStart;
    *MoreData = FALSE;

    return STATUS_SUCCESS;
}

```

## -see-also

- [acxstreams.h header](index.md)

READY2GO

EDITCOMPLETE
