---
UID: NF:acxstreams.AcxStreamAddConnections
tech.root: audio
title: AcxStreamAddConnections
ms.date: 02/02/2022
targetos: Windows
description: The AcxStreamAddConnections function adds explicit connections to a new ACX stream during EvtAcxCircuitCreateStream
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
 - AcxStreamAddConnections
f1_keywords:
 - AcxStreamAddConnections
 - acxstreams/AcxStreamAddConnections
dev_langs:
 - c++
---

## -description

The AcxStreamAddConnections function adds explicit connections to a new ACX stream during [EvtAcxCircuitCreateStream](..\acxcircuit\nc-acxcircuit-evt_acx_circuit_create_stream.md)

## -parameters

### -param Stream

An existing ACXSTREAM stream object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Connections

An [ACX_CONNECTION structure](..\acxpin\ns-acxpin-acx_connection.md) that contains information about the connections to add the stream.

### -param ConnectionsCount

The number of connections that are in the stream. This is a 1 based count. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

If the driver does not call AcxStreamAddConnections during EvtAcxCircuitCreateStream, the ACX framework will automatically assign connections between any ACXELEMENT objects that were added to the ACXSTREAM.

### Example

Example usage is shown below.

```cpp
    //
    // Explicitly connect the elements of the stream. Note that the driver doesn't 
    // need to perform this step when elements are connected in the same order
    // as they were added to the stream.
    //

    const int numElements = 2;
    const int numConnections = numElements + 1;

    ACXSTREAM                      Stream;

    ACX_CONNECTION connections[numConnections];
    ACX_CONNECTION_INIT(&connections[0], Stream, Elements[ElementCount - 2]);
    ACX_CONNECTION_INIT(&connections[1], Elements[ElementCount - 2], Elements[ElementCount - 1]);
    ACX_CONNECTION_INIT(&connections[2], Elements[ElementCount - 1], Stream);

    //
    // Add the connections linking stream to elements.
    //
    status = AcxStreamAddConnections(Stream, connections, SIZEOF_ARRAY(connections));
```

## -see-also

[acxstreams.h header](index.md)

READY2GO
