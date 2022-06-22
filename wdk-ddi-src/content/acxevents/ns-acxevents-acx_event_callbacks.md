---
UID: NS:acxevents._ACX_EVENT_CALLBACKS
tech.root: audio
title: ACX_EVENT_CALLBACKS
ms.date: 12/13/2021
targetos: Windows
description: The ACX_EVENT_CALLBACKS structure identifies the driver callbacks for ACX event operations.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_EVENT_CALLBACKS, *PACX_EVENT_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxevents.h
api_name:
 - _ACX_EVENT_CALLBACKS
 - PACX_EVENT_CALLBACKS
 - ACX_EVENT_CALLBACKS
f1_keywords:
 - _ACX_EVENT_CALLBACKS
 - acxevents/_ACX_EVENT_CALLBACKS
 - PACX_EVENT_CALLBACKS
 - acxevents/PACX_EVENT_CALLBACKS
 - ACX_EVENT_CALLBACKS
 - acxevents/ACX_EVENT_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_EVENT_CALLBACKS** structure identifies the driver callbacks for ACX event operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure. 

### -field EvtAcxEventEnable

The [EVT_ACX_EVENT_ENABLE](nc-acxevents-evt_acx_event_enable.md) callback.

### -field EvtAcxEventDisable

The [EVT_ACX_EVENT_DISABLE](nc-acxevents-evt_acx_event_disable.md) callback.

### -field EvtAcxEventProcessRequest

The [EVT_ACX_OBJECT_PROCESS_EVENT_REQUEST](..\acxrequest\nc-acxrequest-evt_acx_object_process_event_request.md) callback.

## -remarks

An ACXEVENT represents an asynchronous notification available at the driver level. Events can be added to ACXCIRCUITs, ACXSTREAMs, ACXELEMENTs and ACXPINs. Internally they are exposed as KS events to upper layers. 

### Example

This example shows the use of ACX_EVENT_CALLBACKS.

```cpp
    ACX_EVENT_CALLBACKS         eventCallbacks;
    ACX_EVENT_CONFIG            eventCfg;
 
    //
    // Add enable/disable callbacks for this element.
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &TestElement::EvtEventEnableCallback; 
    eventCallbacks.EvtAcxEventDisable = &TestElement::EvtEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);
    eventCfg.Set = &KSEVENTSETID_AudioControlChange;
    eventCfg.Id  = KSEVENT_CONTROL_CHANGE;
    eventCfg.Callbacks = &eventCallbacks;
```

## -see-also

- [acxevents.h header](index.md)

READY2GO
