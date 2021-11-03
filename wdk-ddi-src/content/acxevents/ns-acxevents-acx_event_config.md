---
UID: NS:acxevents._ACX_EVENT_CONFIG
tech.root: audio
title: ACX_EVENT_CONFIG
ms.date:  10/21/2021
targetos: Windows
description: The ACX_EVENT_CONFIG structure is used to define the acx event configuration. 
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
req.typenames: ACX_EVENT_CONFIG, *PACX_EVENT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxevents.h
api_name:
 - _ACX_EVENT_CONFIG
 - PACX_EVENT_CONFIG
 - ACX_EVENT_CONFIG
f1_keywords:
 - _ACX_EVENT_CONFIG
 - acxevents/_ACX_EVENT_CONFIG
 - PACX_EVENT_CONFIG
 - acxevents/PACX_EVENT_CONFIG
 - ACX_EVENT_CONFIG
 - acxevents/ACX_EVENT_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_EVENT_CONFIG structure is used to define the acx event configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure. 

### -field Flags

Bitwise OR of [ACX_PNPEVENT_CONFIG_FLAGS](ne-acxevents-acx_pnpevent_config_flags.md). 

### -field Set

A 

### -field Id

A number that represents the element ID.

??
/windows-hardware/drivers/audio/audio-drivers-event-sets

### -field Type

### -field Callbacks

The [ACX_EVENT_CALLBACKS structure](ns-acxevents-acx_event_callbacks.md) that identifies the driver callbacks for ACX event operations.

## -remarks

### Example

The example shows the use of the TBD

```cpp

    //
    // Add an audio control change event to this volume element.
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &AfxVolume::EvtVolumeEventEnableCallback; 
    eventCallbacks.EvtAcxEventDisable = &AfxVolume::EvtVolumeEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);
    eventCfg.Set = &KSEVENTSETID_AudioControlChange;
    eventCfg.Id  = KSEVENT_CONTROL_CHANGE;
    eventCfg.Callbacks = &eventCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, AFX_VOLUME_EVENT_CONTEXT);
    status = ACXINTERNAL(AcxEventCreate)(m_AcxGlobals, GetObjectHandle(), &attributes, &eventCfg, &m_Event);


    //
    // Init volume event context.
    //
    eventCtx = GetAfxVolumeEventContext(m_Event);
    ASSERT(eventCtx);

    eventCtx->AfxVolume = this; // weak ref to volume object.

    //
    // Add the event to the inner element object.
    //
    status = ACXINTERNAL(AcxElementAddEvents)(m_AcxGlobals, (ACXELEMENT)GetObjectHandle(), &m_Event, 1);


```


## -see-also

[acxcircuit.h header](index.md)



