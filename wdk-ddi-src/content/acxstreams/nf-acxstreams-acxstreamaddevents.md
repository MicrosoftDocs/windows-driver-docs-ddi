---
UID: NF:acxstreams.AcxStreamAddEvents
tech.root: audio
title: AcxStreamAddEvents
ms.date: 07/28/2022
targetos: Windows
description: AcxStreamAddEvents adds events to a stream using an an ACXEVENT object. 
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

**AcxStreamAddEvents** adds events to an existing stream using an ACXEVENT object. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Stream

An existing ACXSTREAM Object. An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements.

### -param Events

A pointer to the ACXEVENT Objects to be added to the Stream. An ACXEVENT object represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers.  For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param EventsCount

A count of the events. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACXEVENT event;
    ...
    AcxStreamAddEvents(Stream, &event, 1);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)

