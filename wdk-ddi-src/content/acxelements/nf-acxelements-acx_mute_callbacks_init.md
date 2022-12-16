---
UID: NF:acxelements.ACX_MUTE_CALLBACKS_INIT
tech.root: audio 
title: ACX_MUTE_CALLBACKS_INIT
ms.date: 04/29/2022
targetos: Windows
description: The ACX_MUTE_CALLBACKS_INIT function initializes a ACX_MUTE_CALLBACKS structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - ACX_MUTE_CALLBACKS_INIT
f1_keywords:
 - ACX_MUTE_CALLBACKS_INIT
 - acxelements/ACX_MUTE_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_MUTE_CALLBACKS_INIT** function initializes a [ACX_MUTE_CALLBACKS structure](ns-acxelements-acx_mute_callbacks.md). 

## -parameters

### -param Callbacks

A pointer to an initialized [ACX_MUTE_CALLBACKS structure](ns-acxelements-acx_mute_callbacks.md). 

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_MUTE_CALLBACKS              muteCallbacks;

    ACX_MUTE_CALLBACKS_INIT(&muteCallbacks);

    muteCallbacks.EvtAcxMuteAssignState = CodecR_EvtMuteAssignState;
    muteCallbacks.EvtAcxMuteRetrieveState = CodecR_EvtMuteRetrieveState;
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
