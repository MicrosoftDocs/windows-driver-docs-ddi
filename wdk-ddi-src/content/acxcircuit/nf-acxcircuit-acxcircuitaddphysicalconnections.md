---
UID: NF:acxcircuit.AcxCircuitAddPhysicalConnections
tech.root: audio
title: AcxCircuitAddPhysicalConnections
ms.date: 02/01/2022
targetos: Windows
description: The AcxCircuitAddPhysicalConnections function adds physical connections to an ACXCIRCUIT. 
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

The **AcxCircuitAddPhysicalConnections** function adds physical connections to an ACXCIRCUIT.

## -parameters

### -param Circuit

An existing ACXCIRCUIT object.  For more information, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Connections

A pointer to an [ACX_CONNECTION structure](/windows-hardware/drivers/ddi/acxrequest/acxpin/ns-acxpin-acx_connection) that describes the pin structure including the pin IDs.

### -param ConnectionsCount

The number of physical connections that will be added to the circuit. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

At this time this DDI is reserved. See DDIs of ACXMANAGER, ACXCIRCUITTEMPLATE and ACXCOMPOSITEMPLATE on how to link multiple ACXCIRCUITs together. 

### Example

Example usage is shown below.

```cpp

```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
