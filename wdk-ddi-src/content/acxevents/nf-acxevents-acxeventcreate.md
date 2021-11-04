---
UID: NF:acxevents.AcxEventCreate
tech.root: audio
title: AcxEventCreate
ms.date: 11/03/2021
targetos: Windows
description: The AcxEventCreate function creates an acx event.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
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
 - LibDef
api_location:
 - acxevents.h
api_name:
 - AcxEventCreate
f1_keywords:
 - AcxEventCreate
 - acxevents/AcxEventCreate
dev_langs:
 - c++
---

## -description

The AcxEventCreate function creates an acx event.

## -parameters

### -param Object

 An ACXOBJECT that is described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).


### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the event with the parent WDF device object (TBD???).

### -param Config

An [ACX_EVENT_CONFIG](ns-acxevents-acx_event_config.md) structure defines how to add circuits for an ACX circuit factory.


### -param Event

The newly created ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxEvent represents an asynchronous notification available at the driver level. Events can be added to AcxCircuits, AcxStreams, AcxElements and AcxPins. Internally they are exposed as KS events to upper layers. 

### Example

TBD - I was not able to find any sample or testing code.

```cpp

```


## -see-also

[acxcircuit.h header](index.md)



