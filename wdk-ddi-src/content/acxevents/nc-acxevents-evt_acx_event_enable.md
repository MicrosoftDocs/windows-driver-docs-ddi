---
UID: NC:acxevents.EVT_ACX_EVENT_ENABLE
tech.root: audio
title: EVT_ACX_EVENT_ENABLE
ms.date:  10/21/2021
targetos: Windows
description: TBD
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
 - EVT_ACX_EVENT_ENABLE
f1_keywords:
 - EVT_ACX_EVENT_ENABLE
 - acxevents/EVT_ACX_EVENT_ENABLE
dev_langs:
 - c++
---

## -description

## -parameters

### -param Event

## -returns

## -remarks

### Example

Example pending.

```cpp
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


