---
UID: NS:acxelements._ACX_VOLUME_CALLBACKS
tech.root: audio 
title: ACX_VOLUME_CALLBACKS
ms.date: 08/01/2022
targetos: Windows
description: The ACX_VOLUME_CALLBACKS structure identifies the driver callbacks for ACX volume operations.
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
req.typenames: ACX_VOLUME_CALLBACKS, *PACX_VOLUME_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_VOLUME_CALLBACKS
 - PACX_VOLUME_CALLBACKS
 - ACX_VOLUME_CALLBACKS
f1_keywords:
 - _ACX_VOLUME_CALLBACKS
 - acxelements/_ACX_VOLUME_CALLBACKS
 - PACX_VOLUME_CALLBACKS
 - acxelements/PACX_VOLUME_CALLBACKS
 - ACX_VOLUME_CALLBACKS
 - acxelements/ACX_VOLUME_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_VOLUME_CALLBACKS** structure identifies the driver callbacks for ACX volume operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxVolumeAssignLevel

The [EVT_ACX_VOLUME_ASSIGN_LEVEL](nc-acxelements-evt_acx_volume_assign_level.md) callback.

### -field EvtAcxRampedVolumeAssignLevel

The [EVT_ACX_RAMPED_VOLUME_ASSIGN_LEVEL](nc-acxelements-evt_acx_ramped_volume_assign_level.md) callback.

### -field EvtAcxVolumeRetrieveLevel

The [EVT_ACX_VOLUME_RETRIEVE_LEVEL](nc-acxelements-evt_acx_volume_retrieve_level.md) callback.

### -field EvtAcxVolumeProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/nc-acxrequest-evt_acx_object_process_request) callback. 

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

## -see-also

- [acxelements.h header](index.md)


