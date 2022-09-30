---
UID: NS:acxelements._ACX_AUDIOMODULE_CALLBACKS
tech.root: audio 
title: ACX_AUDIOMODULE_CALLBACKS
ms.date: 04/29/2022
targetos: Windows
description: The ACX_AUDIOMODULE_CALLBACKS structure identifies the driver callbacks for ACX audio module operations. 
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
req.typenames: ACX_AUDIOMODULE_CALLBACKS, *PACX_AUDIOMODULE_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_AUDIOMODULE_CALLBACKS
 - PACX_AUDIOMODULE_CALLBACKS
 - ACX_AUDIOMODULE_CALLBACKS
f1_keywords:
 - _ACX_AUDIOMODULE_CALLBACKS
 - acxelements/_ACX_AUDIOMODULE_CALLBACKS
 - PACX_AUDIOMODULE_CALLBACKS
 - acxelements/PACX_AUDIOMODULE_CALLBACKS
 - ACX_AUDIOMODULE_CALLBACKS
 - acxelements/ACX_AUDIOMODULE_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_AUDIOMODULE_CALLBACKS** structure identifies the driver callbacks for ACX audio module operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxAudioModuleProcessCommand

The [ACX_AUDIOMODULE_PROCESSCOMMAND](nc-acxelements-evt_acx_audiomodule_processcommand.md) callback.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


