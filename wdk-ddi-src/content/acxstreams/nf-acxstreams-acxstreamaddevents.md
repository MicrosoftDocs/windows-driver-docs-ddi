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

AcxStreamAddEvents adds events to and existing/new (TBD?) stream using an An [AcxEvent]() (DocsTeam - need link to ACX Object Summary topic) object. TBD

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new [ACXSTREAM Object]() (DocsTeam - need link to ACX Object Summary topic). An ACXSTREAM Object represents an audio stream created by a circuit. ACX objects are WDF object-like, i.e., the ACX driver interacts with them in the same way as WDF when creating, deleting, and interacting with them. For more information, see [WDF Architecture](/windows-hardware/drivers/wdf/kernel-mode-driver-framework-architecture) and [Framework Object Life Cycle](/windows-hardware/drivers/wdf/framework-object-life-cycle).

The ACXSTREAM Object is the driver component that’s created to represent an audio stream, created by a circuit. The Stream is composed of a list of Elements created based on the parent Circuit’s Elements.   An AcxStream aggregates zero or n AcxElements-like objects. By default, AcxElements are connected in the same order of assembly. An AcxStream is associated with only one ACX circuit. ACX supports two types of streams: basic ACX stream objects used by non-streaming circuits, and ACX RT stream objects used by streaming circuits.

### -param Events

A pointer to a location that receives a handle to the ACXEVENT Object. An [AcxEvent]() (DocsTeam - need link to ACX Object Summary topic) represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers.

### -param EventsCount

A count of the events. This is a 0/1 TBD based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

- TBD No sample code was located

Example usage is shown below.

```cpp

```

## -see-also

[acxstreams.h header](index.md)

