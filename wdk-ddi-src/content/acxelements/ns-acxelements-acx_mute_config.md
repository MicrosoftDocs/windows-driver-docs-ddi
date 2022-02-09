---
UID: NS:acxelements._ACX_MUTE_CONFIG
tech.root: audio 
title: ACX_MUTE_CONFIG
ms.date: 09/03/2021
targetos: Windows
description: The ACX_MUTE_CONFIG structure is used to define the audio mute configuration. 
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
req.typenames: ACX_MUTE_CONFIG, *PACX_MUTE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_MUTE_CONFIG
 - PACX_MUTE_CONFIG
 - ACX_MUTE_CONFIG
f1_keywords:
 - _ACX_MUTE_CONFIG
 - acxelements/_ACX_MUTE_CONFIG
 - PACX_MUTE_CONFIG
 - acxelements/PACX_MUTE_CONFIG
 - ACX_MUTE_CONFIG
 - acxelements/ACX_MUTE_CONFIG
dev_langs:
 - c++
---

## -description

The ACX_MUTE_CONFIG structure is used to define the audio mute configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Audio key word spotter configuration flags defined by the [ACX_MUTE_CONFIG_FLAGS enum](ne-acxelements-acx_mute_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxMuteConfigNoFlags.

### -field ChannelsCount

The number of channels. This is a  one based count.

### -field Callbacks

The [ACX_MUTE_CALLBACKS structure](ns-acxelements-acx_mute_callbacks.md) that identifies the driver callbacks for ACX mute operations.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_MUTE_CALLBACKS              muteCallbacks;
    ACX_MUTE_CONFIG                 muteCfg;
    ACXMUTE                         muteElement;

    //
    // Create three elements to handle mute for the audioengine element
    //
    ACX_MUTE_CALLBACKS_INIT(&muteCallbacks);
    muteCallbacks.EvtAcxMuteAssignState = CodecR_EvtMuteAssignState;
    muteCallbacks.EvtAcxMuteRetrieveState = CodecR_EvtMuteRetrieveState;

    ACX_MUTE_CONFIG_INIT(&muteCfg);
    muteCfg.ChannelsCount = MAX_CHANNELS;
    muteCfg.Name = &KSAUDFNAME_WAVE_MUTE;
    muteCfg.Callbacks = &muteCallbacks;
```

## -see-also

[acxelements.h header](index.md)

