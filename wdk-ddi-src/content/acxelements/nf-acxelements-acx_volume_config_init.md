---
UID: NF:acxelements.ACX_VOLUME_CONFIG_INIT
tech.root: audio 
title: ACX_VOLUME_CONFIG_INIT
ms.date: 09/21/2021
targetos: Windows
description: TBD - The ACX_VOLUME_CONFIG_INIT function initializes an ACX_VOLUME_CONFIG structure.
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
 - ACX_VOLUME_CONFIG_INIT
f1_keywords:
 - ACX_VOLUME_CONFIG_INIT
 - acxelements/ACX_VOLUME_CONFIG_INIT
dev_langs:
 - c++
---

## -description

TBD - The ACX_VOLUME_CONFIG_INIT function initializes an [ACX_VOLUME_CONFIG](ns-acxelements-acx_volume_config.md) structure.

## -parameters

### -param cfg

An [ACX_VOLUME_CONFIG](ns-acxelements-acx_volume_config.md) structure.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_VOLUME_CONFIG               volumeCfg;

    ACX_VOLUME_CONFIG_INIT(&volumeCfg);
    volumeCfg.ChannelsCount = MAX_CHANNELS;
    volumeCfg.Minimum = VOLUME_LEVEL_MINIMUM;
    volumeCfg.Maximum = VOLUME_LEVEL_MAXIMUM;
    volumeCfg.SteppingDelta = VOLUME_STEPPING;
    volumeCfg.Callbacks = &volumeCallbacks;
```

## -see-also

[acxelements.h header](index.md)

