---
UID: NF:acxevents.ACX_EVENT_CONFIG_INIT
tech.root: audio
title: ACX_EVENT_CONFIG_INIT
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
 - ACX_EVENT_CONFIG_INIT
f1_keywords:
 - ACX_EVENT_CONFIG_INIT
 - acxevents/ACX_EVENT_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The ACX_EVENT_CONFIG_INIT function initializes an [ACX_EVENT_CONFIG](ns-acxevents-acx_event_config.md) structure.


## -parameters

### -param Config

An initialized [ACX_EVENT_CONFIG structure](ns-acxevents-acx_event_config.md) that describes the configuration of the acx event.


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



