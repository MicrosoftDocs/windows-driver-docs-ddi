---
UID: NS:acxevents._ACX_EVENT_CONFIG
tech.root: audio
title: ACX_EVENT_CONFIG
ms.date: 12/09/2021
targetos: Windows
description: The ACX_EVENT_CONFIG structure is used to configure an ACXEVENT. 
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

The **ACX_EVENT_CONFIG** structure is used to configure an ACXEVENT.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Flags

Bitwise OR of [ACX_PNPEVENT_CONFIG_FLAGS](ne-acxevents-acx_pnpevent_config_flags.md).

### -field Set

Specifies the event set. This member is a pointer to a GUID that uniquely identifies the event set. See the list of event-set GUIDs in [Audio Drivers Event Sets](/windows-hardware/drivers/audio/audio-drivers-event-sets).

This is a KSEVENTSETID, for example KSEVENTSETID_AudioControlChange. For more information about, see [KSEVENTDATA structure (ks.h)](/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata).

### -field Id

Specifies the event ID. This member identifies an event item within the event set. If the event set contains N items, valid event IDs are integers in the range 0 to N-1.

### -field Type

The event value type (operation data) is a [KSEVENTDATA structure](/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata) that specifies the notification method to use for this event.

### -field Callbacks

The [ACX_EVENT_CALLBACKS structure](ns-acxevents-acx_event_callbacks.md) that identifies the driver callbacks for ACX event operations.

## -remarks

### Example

The example shows how ACX uses the ACX_EVENT_CONFIG structure.

```cpp
    ACX_EVENT_CONFIG            eventCfg;
    ACX_EVENT_CALLBACKS         eventCallbacks;
 
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
```

## -see-also

- [acxevents.h header](index.md)

READY2GO
