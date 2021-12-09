---
UID: NF:acxevents.ACX_EVENT_CALLBACKS_INIT
tech.root: audio
title: ACX_EVENT_CALLBACKS_INIT
ms.date: 12/09/2021
targetos: Windows
description: The ACX_EVENT_CALLBACKS_INIT function initializes a ACX_EVENTS_CALLBACKS structure.
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
 - ACX_EVENT_CALLBACKS_INIT
f1_keywords:
 - ACX_EVENT_CALLBACKS_INIT
 - acxevents/ACX_EVENT_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_EVENT_CALLBACKS_INIT function initializes a [ACX_EVENTS_CALLBACKS structure](ns-acxevents-acx_event_callbacks.md). No inputs are used with this function.

## -parameters

### -param Callbacks

A pointer to an initialized [ACX_EVENTS_CALLBACKS structure](ns-acxevents-acx_event_callbacks.md).

## -remarks

### Example

This example shows the use of ACX_EVENT_CALLBACKS_INIT.

```cpp
    ACX_EVENT_CALLBACKS         eventCallbacks;
    ACX_EVENT_CONFIG            eventCfg;
    //
    // Add an audio control change event to this volume element.
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &AfxVolume::EvtVolumeEventEnableCallback; 
    eventCallbacks.EvtAcxEventDisable = &AfxVolume::EvtVolumeEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);
```

## -see-also

[acxcircuit.h header](index.md)


