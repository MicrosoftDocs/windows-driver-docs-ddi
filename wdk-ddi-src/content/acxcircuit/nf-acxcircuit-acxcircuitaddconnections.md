---
UID: NF:acxcircuit.AcxCircuitAddConnections
tech.root: audio
title: AcxCircuitAddConnections
ms.date: 02/01/2022
targetos: Windows
description: The AcxCircuitAddConnections function adds connections to an Acx circuit. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitAddConnections
f1_keywords:
 - AcxCircuitAddConnections
 - acxcircuit/AcxCircuitAddConnections
dev_langs:
 - c++
---

## -description

The **AcxCircuitAddConnections** function adds connections to an Acx circuit.

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).
  
### -param Connections

A pointer to an [ACX_CONNECTION structure](/windows-hardware/drivers/ddi/acxrequest/acxpin/ns-acxpin-acx_connection) that describes the pin structure including the pin IDs.

### -param ConnectionsCount

The number of connections that will be added to the circuit. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Explicitly connect the circuit/elements. Note that driver doesn't 
    // need to perform this step when circuit/elements are connected in the 
    // same order as they were added to the circuit. By default ACX connects
    // the elements starting from the sink circuit pin and ending with the 
    // source circuit pin for both render and capture devices.
    //
    // circuit.pin[default_sink]    -> 1st element.pin[default_in]
    // 1st element.pin[default_out] -> 2nd element.pin[default_in]
    // 2nd element.pin[default_out] -> circuit.pin[default_source]
    //

    const int numElements = 2;
    const int numConnections = numElements + 1;

    ACXCIRCUIT                      Circuit;

    ACX_CONNECTION connections[numConnections];
    ACX_CONNECTION_INIT(&connections[0], Circuit, Elements[ElementCount - 2]);
    ACX_CONNECTION_INIT(&connections[1], Elements[ElementCount - 2], Elements[ElementCount - 1]);
    ACX_CONNECTION_INIT(&connections[2], Elements[ElementCount - 1], Circuit);

    //
    // Add the connections linking circuit to elements.
    //
    status = AcxCircuitAddConnections(Circuit, connections, SIZEOF_ARRAY(connections));
```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic