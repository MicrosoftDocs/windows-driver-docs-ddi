---
UID: NS:acxelements._ACX_STREAMAUDIOENGINE_CONFIG
tech.root: audio 
title: ACX_STREAMAUDIOENGINE_CONFIG
ms.date: 09/02/2021
targetos: Windows
description: The ACX_STREAMAUDIOENGINE_CONFIG structure is used to define the audio engine stream configuration. 
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
req.typenames: ACX_STREAMAUDIOENGINE_CONFIG, *PACX_STREAMAUDIOENGINE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_STREAMAUDIOENGINE_CONFIG
 - PACX_STREAMAUDIOENGINE_CONFIG
 - ACX_STREAMAUDIOENGINE_CONFIG
f1_keywords:
 - _ACX_STREAMAUDIOENGINE_CONFIG
 - acxelements/_ACX_STREAMAUDIOENGINE_CONFIG
 - PACX_STREAMAUDIOENGINE_CONFIG
 - acxelements/PACX_STREAMAUDIOENGINE_CONFIG
 - ACX_STREAMAUDIOENGINE_CONFIG
 - acxelements/ACX_STREAMAUDIOENGINE_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_STREAMAUDIOENGINE_CONFIG structure is used to define the audio engine stream configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.
 
### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Audio engine configuration flags defined by the [ACX_STREAMAUDIOENGINE_CONFIG_FLAGS enum](ne-acxelements-acx_streamaudioengine_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxStreamAudioEngineConfigNoFlags. 

### -field VolumeElement

An existing ACXVOLUME object that is used for volume operations by the audio engine.

### -field MuteElement

An existing ACXMUTE object that is used for mute operations by the audio engine.

### -field PeakMeterElement

An existing ACXPEAKMETER object that is used for peakmeter operations by the audio engine.

### -field Callbacks

The [ACX_STREAMAUDIOENGINE_CALLBACKS structure](ns-acxelements-acx_streamaudioengine_callbacks.md) that identifies the driver callbacks for ACX audio engine streaming operations.

## -remarks

### Example

Example usage is shown below.

```cpp
        ACX_STREAMAUDIOENGINE_CONFIG audioEngineCfg;
        ACX_STREAMAUDIOENGINE_CONFIG_INIT(&audioEngineCfg);
        audioEngineCfg.VolumeElement = volumeElement;
        audioEngineCfg.MuteElement = muteElement;
        audioEngineCfg.PeakMeterElement = peakmeterElement;
        audioEngineCfg.Callbacks = &streamAudioEngineCallbacks;
```

## -see-also

[acxelements.h header](index.md)

