---
UID: NF:acxstreams.AcxStreamAddEvents
tech.root: audio
title: AcxStreamAddEvents
ms.date: 07/13/2021
targetos: Windows
description: AcxStreamAddEvents adds events to and existing/new (TBD?) stream using an an AcxEvent object. 
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
 - AcxStreamAddEvents
f1_keywords:
 - AcxStreamAddEvents
 - acxstreams/AcxStreamAddEvents
dev_langs:
 - c++
---

## -description

AcxStreamAddEvents adds events to and existing/new (TBD?) stream using an AcxEvent object. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Events

A pointer to a location that receives a handle to the ACXEVENT Object. An AcxEvent object that represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers.  For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param EventsCount

A count of the events. This is a 0/1 TBD based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - No sample code or unit tests were located

Example usage is shown below.

```cpp

```

## -see-also

[acxstreams.h header](index.md)

