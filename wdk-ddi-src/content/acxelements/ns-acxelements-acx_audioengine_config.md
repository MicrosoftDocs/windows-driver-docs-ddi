---
UID: NS:acxelements._ACX_AUDIOENGINE_CONFIG
tech.root: audio 
title: ACX_AUDIOENGINE_CONFIG
ms.date: 09/03/2021
targetos: Windows
description: The ACX_AUDIOENGINE_CONFIG structure is used to define the audio engine configuration. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_AUDIOENGINE_CONFIG, *PACX_AUDIOENGINE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_AUDIOENGINE_CONFIG
 - PACX_AUDIOENGINE_CONFIG
 - ACX_AUDIOENGINE_CONFIG
f1_keywords:
 - _ACX_AUDIOENGINE_CONFIG
 - acxelements/_ACX_AUDIOENGINE_CONFIG
 - PACX_AUDIOENGINE_CONFIG
 - acxelements/PACX_AUDIOENGINE_CONFIG
 - ACX_AUDIOENGINE_CONFIG
 - acxelements/ACX_AUDIOENGINE_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_AUDIOENGINE_CONFIG structure is used to define the audio engine configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Audio engine configuration flags defined by the [ACX_AUDIOENGINE_CONFIG_FLAGS enum](ne-acxelements-acx_audioengine_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxAudioEngineConfigNoFlags

### -field HostPin

TBD - An existing (or new TBD?) ACXPIN object that serves as the host (TBD) for the audio engine. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -field OffloadPin

An existing ACXPIN object that represents the offload pin.

### -field LoopbackPin

An existing ACXPIN object that represents the loop back pin.

### -field VolumeElement

An existing ACXVOLUME object that is used for volume operations by the audio engine.

### -field MuteElement

An existing ACXMUTE object that is used for mute operations by the audio engine.

### -field PeakMeterElement

An existing ACXPEAKMETER object that is used for peakmeter operations by the audio engine.

### -field Callbacks

An [ACX_AUDIOENGINE_CALLBACKS structure](ns-acxelements-acx_audioengine_callbacks.md) that defines the callbacks for the audio engine. 

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_AUDIOENGINE_CONFIG          audioEngineCfg;  
    ACX_AUDIOENGINE_CALLBACKS       audioEngineCallbacks;

    // Initialize the config structure
    ACX_AUDIOENGINE_CONFIG_INIT(&audioEngineCfg);
    // Set the values of the structure
    audioEngineCfg.HostPin = Pins[HostPin];
    audioEngineCfg.OffloadPin = Pins[OffloadPin];
    audioEngineCfg.LoopbackPin = Pins[LoopbackPin];
    audioEngineCfg.VolumeElement = volumeElement;
    audioEngineCfg.MuteElement = muteElement;
    audioEngineCfg.PeakMeterElement = peakmeterElement;
    audioEngineCfg.Callbacks = &audioEngineCallbacks;
```

## -see-also

- [acxelements.h header](index.md)

TBD - Please review this topic