---
UID: NC:acxstreams.EVT_ACX_STREAM_FREE_RTPACKETS
tech.root: audio
title: EVT_ACX_STREAM_FREE_RTPACKETS
ms.date: 07/01/2021
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

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic) that represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param Packets

A pointer to a [ACX_RTPACKET structure](ns-acxstreams-acx_rtpacket.md) that describes the location and size of the packets to be freed.

### -param PacketCount

The number of packets in (since?) a TBD. This is 0/1 TBD based count. These packets will be freed (TBD?).

## -remarks


### Example

TBD - should we show more code here?

Example usage is shown below.

```cpp
    // Init RT streaming callbacks.
    //
    ACX_RT_STREAM_CALLBACKS rtCallbacks;
    ACX_RT_STREAM_CALLBACKS_INIT(&rtCallbacks);
    rtCallbacks.EvtAcxStreamFreeRtPackets               = Dsp_EvtStreamFreeRtPackets;

    RETURN_NTSTATUS_IF_FAILED(AcxStreamInitAssignAcxRtStreamCallbacks(StreamInit, &rtCallbacks));

    // Later in the code need to free the packets...
    //
    callbacks = GetRtStreamCallbacks();

    callbacks->EvtAcxStreamFreeRtPackets((ACXSTREAM)Object, packets, packetsToAllocate);
    packets = NULL;
```

## -see-also

[acxstreams.h header](index.md)

