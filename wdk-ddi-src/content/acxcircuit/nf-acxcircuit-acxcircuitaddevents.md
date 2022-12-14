---
UID: NF:acxcircuit.AcxCircuitAddEvents
tech.root: audio
title: AcxCircuitAddEvents
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitAddEvents function adds one or more events to an ACXCIRCUIT. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitAddEvents
f1_keywords:
 - AcxCircuitAddEvents
 - acxcircuit/AcxCircuitAddEvents
dev_langs:
 - c++
---

## -description

The **AcxCircuitAddEvents** function adds one or more events to an ACXCIRCUIT.

## -parameters

### -param Circuit

An existing ACXCIRCUIT object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Events

An existing ACXEVENT object containing one or more events.

### -param EventsCount

The number of events that will be added to the circuit. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxEvent represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. They are exposed as KS events to clients (upper user-mode layers).

### Example

Example usage is shown below.

Sample pending.

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
