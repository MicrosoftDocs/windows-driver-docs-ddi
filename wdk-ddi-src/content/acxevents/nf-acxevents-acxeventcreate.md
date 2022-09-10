---
UID: NF:acxevents.AcxEventCreate
tech.root: audio
title: AcxEventCreate
ms.date: 06/22/2022
targetos: Windows
description: The AcxEventCreate function creates an event.
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

The **AcxEventCreate** function creates an ACX event.

## -parameters

### -param Object

An ACXOBJECT that is described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An [ACX_EVENT_CONFIG](ns-acxevents-acx_event_config.md) structure that defines the ACX event configuration.

### -param Event

The newly created ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An ACXEVENT represents an asynchronous notification available at the driver level. Events can be added to ACXCIRCUITs, ACXSTREAMs, ACXELEMENTs and ACXPINs. Internally they are exposed as KS Events to upper layers. For more information about KS Events, see [KS Events](/windows-hardware/drivers/stream/ks-events).

### Example

This example code snip, shows how ACX uses AcxEventCreate to create an audio jack change event.

```cpp
    NTSTATUS status = STATUS_SUCCESS;
    
    PAGED_CODE();

    ACX_EVENT_CALLBACKS         eventCallbacks;
    ACX_EVENT_CONFIG            eventCfg;
    AFX_PIN_EVENT_CONTEXT       *eventCtx;
    ACXEVENT                    jackEvent;
    WDF_OBJECT_ATTRIBUTES       attributes;

    //
    // Add jack info change event to this jack object
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &AfxPin::EvtJackEventEnableCallback;
    eventCallbacks.EvtAcxEventDisable = &AfxPin::EvtJackEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);
    eventCfg.Set = &KSEVENTSETID_PinCapsChange;
    eventCfg.Id = KSEVENT_PINCAPS_JACKINFOCHANGE;
    eventCfg.Callbacks = &eventCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, AFX_PIN_EVENT_CONTEXT);
    attributes.ParentObject = GetObjectHandle();
    status = AcxEventCreate(GetObjectHandle(), &attributes, &eventCfg, &jackEvent);
```

## -see-also

- [acxevents.h header](index.md)

