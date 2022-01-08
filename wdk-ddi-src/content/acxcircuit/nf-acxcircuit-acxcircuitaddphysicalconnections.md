---
UID: NF:acxcircuit.AcxCircuitAddPhysicalConnections
tech.root: audio
title: AcxCircuitAddPhysicalConnections
ms.date: 08/16/2021
targetos: Windows
description: The AcxCircuitAddPhysicalConnections function adds physical connections to an existing (TBD or new?) Acx circuit. 
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
 - AcxCircuitAddPhysicalConnections
f1_keywords:
 - AcxCircuitAddPhysicalConnections
 - acxcircuit/AcxCircuitAddPhysicalConnections
dev_langs:
 - c++
---

## -description

The AcxCircuitAddPhysicalConnections function adds physical connections to an existing (TBD or new?) Acx circuit. 

## -parameters

### -param Circuit

TBD - An existing (TBD?) ACXCIRCUIT circuit object.  For more information, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).
 
### -param Connections

A pointer to an [ACX_CONNECTION structure](..\acxpin\ns-acxpin-acx_connection.md) that describes the pin structure including the pin IDs. 

### -param ConnectionsCount

TBD - The number of physical connections that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - This code was commented out for some reason, is it OK to use?

```cpp
    //
    // Add downstream physical connection.
    //
    RtlInitUnicodeString(&targetName, CODEC_NEXT_CIRCUIT_STR);
    status = WdfStringCreate(&targetName, WDF_NO_OBJECT_ATTRIBUTES, &wdfTargetName);

    ACX_PHYSICAL_CONNECTION_INIT(&phyConnection);
    phyConnection.Flags = AcxPhysicalConnectionFromPinId;
    phyConnection.FromPin.Id = 1;
    phyConnection.TargetName = wdfTargetName;
    phyConnection.TargetPinId = 0; // TODO: hardcoded for now.

    status = AcxCircuitAddPhysicalConnections(circuit, &phyConnection, 1);
```

## -see-also

[acxcircuit.h header](index.md)

