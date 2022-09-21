---
UID: NS:acxelements._ACX_VOLUME_CONFIG
tech.root: audio 
title: ACX_VOLUME_CONFIG
ms.date: 04/29/2022
targetos: Windows
description: The ACX_VOLUME_CONFIG structure is used to define the acx volume configuration. 
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
req.typenames: ACX_VOLUME_CONFIG, *PACX_VOLUME_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_VOLUME_CONFIG
 - PACX_VOLUME_CONFIG
 - ACX_VOLUME_CONFIG
f1_keywords:
 - _ACX_VOLUME_CONFIG
 - acxelements/_ACX_VOLUME_CONFIG
 - PACX_VOLUME_CONFIG
 - acxelements/PACX_VOLUME_CONFIG
 - ACX_VOLUME_CONFIG
 - acxelements/ACX_VOLUME_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_VOLUME_CONFIG** structure is used to define the acx volume configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Acx volume configuration flags defined by the [ACX_VOLUME_CONFIG_FLAGS enum](ne-acxelements-acx_volume_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxVolumeConfigNoFlags

### -field ChannelsCount

The number of channels. This is a one based count.

### -field Maximum

The maximum boost level for the volume.

### -field Minimum

The minimum boost level for the volume.

### -field SteppingDelta

The stepping delta for the volume.

### -field Callbacks

The [ACX_VOLUME_CALLBACKS structure](ns-acxelements-acx_volume_callbacks.md) that identifies the driver callbacks for ACX volume operations.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_VOLUME_CALLBACKS            volumeCallbacks;
    ACX_VOLUME_CONFIG               volumeCfg;

    ACX_VOLUME_CALLBACKS_INIT(&volumeCallbacks);
    volumeCallbacks.EvtAcxVolumeAssignLevel = CodecC_EvtVolumeAssignLevelCallback;
    volumeCallbacks.EvtAcxVolumeRetrieveLevel = CodecC_EvtVolumeRetrieveLevelCallback;

    ACX_VOLUME_CONFIG_INIT(&volumeCfg);
    volumeCfg.ChannelsCount = MAX_CHANNELS;
    volumeCfg.Minimum = VOLUME_LEVEL_MINIMUM;
    volumeCfg.Maximum = VOLUME_LEVEL_MAXIMUM;
    volumeCfg.SteppingDelta = VOLUME_STEPPING;
    volumeCfg.Callbacks = &volumeCallbacks;

```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


