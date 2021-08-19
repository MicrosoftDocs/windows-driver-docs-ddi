---
UID: NC:acxstreams.EVT_ACX_STREAM_PREPARE_HARDWARE
tech.root: audio
title: EVT_ACX_STREAM_PREPARE_HARDWARE
ms.date: 07/09/2021
targetos: Windows
description: The EvtAcxStreamPrepareHardware event tells the driver when the hardware has been prepared. (TBD is being prepared?)
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
 - EVT_ACX_STREAM_PREPARE_HARDWARE
f1_keywords:
 - EVT_ACX_STREAM_PREPARE_HARDWARE
 - acxstreams/EVT_ACX_STREAM_PREPARE_HARDWARE
dev_langs:
 - c++
---

## -description

The EvtAcxStreamPrepareHardware event tells the driver when the hardware has been prepared. (TBD is being prepared?)

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - Need to see if this is the correct code sample

Example usage is shown below.

```cpp
EVT_WDF_DEVICE_PREPARE_HARDWARE     Codec_EvtDevicePrepareHardware;

#pragma code_seg("PAGE")
NTSTATUS
Codec_EvtStreamPrepareHardware(
    _In_ ACXSTREAM Stream
    )
{
    PCODEC_STREAM_CONTEXT ctx;
    CStreamEngine * streamEngine = NULL;

    PAGED_CODE();

    ctx = GetCodecStreamContext(Stream);

    streamEngine = (CStreamEngine*)ctx->StreamEngine;

    return streamEngine->PrepareHardware();
}


```

## -see-also

[acxstreams.h header](index.md)

[EVT_ACX_STREAM_RUN_HARDWARE](nc-acxstreams-evt_acx_stream_run.md)

[EVT_ACX_STREAM_PAUSE_HARDWARE](nc-acxstreams-evt_acx_stream_pause.md)

[EVT_ACX_STREAM_RELEASE_HARDWARE](nc-acxstreams-evt_acx_stream_release_hardware.md)

