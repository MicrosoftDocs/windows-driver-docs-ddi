---
UID: NC:acxstreams.EVT_ACX_STREAM_GET_CAPTURE_PACKET
tech.root: audio
title: EVT_ACX_STREAM_GET_CAPTURE_PACKET
ms.date: 07/07/2021
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

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param LastCapturePacket

A value indicating the position of the last captured packet. This is a 0/1 TBD value. 

### -param QPCPacketStart

A value indicating the position of the last captured packet. This is a 0/1 TBD value. 


### -param MoreData

A PBOOLEAN value indicating of there is more data.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks


### Example

TBD - Was not sure which sample code to show here.

Example usage is shown below.

```cpp

```

## -see-also

[acxstreams.h header](index.md)

