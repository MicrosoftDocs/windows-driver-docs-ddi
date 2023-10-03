---
UID: NF:acxevents.ACX_EVENT_CONFIG_INIT
tech.root: audio
title: ACX_EVENT_CONFIG_INIT
ms.date: 06/22/2022
targetos: Windows
description: The ACX_EVENT_CONFIG_INIT function initializes an ACX_EVENT_CONFIG structure.
prerelease: false
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

The **ACX_EVENT_CONFIG_INIT** function initializes an [ACX_EVENT_CONFIG](ns-acxevents-acx_event_config.md) structure. No inputs are used with this function.

## -parameters

### -param Config

An initialized [ACX_EVENT_CONFIG structure](ns-acxevents-acx_event_config.md) that describes the configuration of the event.

## -remarks

### Example

This example shows the use of ACX_EVENT_CONFIG_INIT.

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
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxevents.h header](index.md)
