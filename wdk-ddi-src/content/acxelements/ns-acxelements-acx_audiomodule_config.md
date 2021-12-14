---
UID: NS:acxelements._ACX_AUDIOMODULE_CONFIG
tech.root: audio 
title: ACX_AUDIOMODULE_CONFIG
ms.date: 09/03/2021
targetos: Windows
description: The ACX_AUDIOMODULE_CONFIG structure is used to define the audio module configuration. 
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
req.typenames: ACX_AUDIOMODULE_CONFIG, *PACX_AUDIOMODULE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_AUDIOMODULE_CONFIG
 - PACX_AUDIOMODULE_CONFIG
 - ACX_AUDIOMODULE_CONFIG
f1_keywords:
 - _ACX_AUDIOMODULE_CONFIG
 - acxelements/_ACX_AUDIOMODULE_CONFIG
 - PACX_AUDIOMODULE_CONFIG
 - acxelements/PACX_AUDIOMODULE_CONFIG
 - ACX_AUDIOMODULE_CONFIG
 - acxelements/ACX_AUDIOMODULE_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_AUDIOMODULE_CONFIG structure is used to define the audio module configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Audio module configuration flags defined by the [ACX_AUDIOMODULE_CONFIG_FLAGS enum](ne-acxelements-acx_audiomodule_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxAudioModuleConfigNoFlags

### -field Descriptor

An [ACX_AUDIOMODULE_DESCRIPTOR](ns-acxelements-acx_audiomodule_descriptor.md) structure that describes the audio module.

### -field Callbacks

The [ACX_AUDIOMODULE_CALLBACKS structure](ns-acxelements-acx_audiomodule_callbacks.md) that identifies the driver callbacks for ACX audio module operations.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_AUDIOMODULE_CALLBACKS       audioModuleCallbacks;   
    ACX_AUDIOMODULE_CONFIG          audioModuleCfg;
    ACXAUDIOMODULE                  audioModuleElement;

    // Now add audio modules to the circuit
    // module 0

    ACX_AUDIOMODULE_CALLBACKS_INIT(&audioModuleCallbacks);
    audioModuleCallbacks.EvtAcxAudioModuleProcessCommand = CodecR_EvtProcessCommand0;

    ACX_AUDIOMODULE_CONFIG_INIT(&audioModuleCfg);
    audioModuleCfg.Name = &AudioModule0Id;
    audioModuleCfg.Descriptor.ClassId = AudioModule0Id;
    audioModuleCfg.Descriptor.InstanceId = AUDIOMODULE_INSTANCE_ID(0,0);
    audioModuleCfg.Descriptor.VersionMajor = AUDIOMODULE0_MAJOR;
    audioModuleCfg.Descriptor.VersionMinor = AUDIOMODULE0_MINOR;
    wcsncpy_s(audioModuleCfg.Descriptor.Name,
                ACX_AUDIOMODULE_MAX_NAME_CCH_SIZE,
                AUDIOMODULE0DESCRIPTION,
                wcslen(AUDIOMODULE0DESCRIPTION));
    audioModuleCfg.Callbacks = &audioModuleCallbacks;

```

## -see-also

[acxelements.h header](index.md)

