---
UID: NS:acxelements._ACX_MUTE_CALLBACKS
tech.root: audio 
title: ACX_MUTE_CALLBACKS
ms.date: 08/01/2022
targetos: Windows
description: The ACX_MUTE_CALLBACKS structure identifies the driver callbacks for ACX mute operations.
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
req.typenames: ACX_MUTE_CALLBACKS, *PACX_MUTE_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_MUTE_CALLBACKS
 - PACX_MUTE_CALLBACKS
 - ACX_MUTE_CALLBACKS
f1_keywords:
 - _ACX_MUTE_CALLBACKS
 - acxelements/_ACX_MUTE_CALLBACKS
 - PACX_MUTE_CALLBACKS
 - acxelements/PACX_MUTE_CALLBACKS
 - ACX_MUTE_CALLBACKS
 - acxelements/ACX_MUTE_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_MUTE_CALLBACKS** structure identifies the driver callbacks for ACX mute operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxMuteAssignState

The [EVT_ACX_MUTE_ASSIGN_STATE](nc-acxelements-evt_acx_mute_assign_state.md) callback.

### -field EvtAcxMuteRetrieveState

The [EVT_ACX_MUTE_RETRIEVE_STATE](nc-acxelements-evt_acx_mute_retrieve_state.md) callback.

### -field EvtAcxMuteProcessRequest

The [EVT_ACX_OBJECT_PROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/nc-acxrequest-evt_acx_object_process_request) callback.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header\]\(index.md\)
