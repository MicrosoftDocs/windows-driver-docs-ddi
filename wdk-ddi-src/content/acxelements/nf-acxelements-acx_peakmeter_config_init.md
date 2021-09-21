---
UID: NF:acxelements.ACX_PEAKMETER_CONFIG_INIT
tech.root: audio 
title: ACX_PEAKMETER_CONFIG_INIT
ms.date: 09/20/2021
targetos: Windows
description: TBD - The ACX_PEAKMETER_CONFIG_INIT function initializes an ACX_PEAKMETER_CONFIG structure.
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
 - ACX_PEAKMETER_CONFIG_INIT
f1_keywords:
 - ACX_PEAKMETER_CONFIG_INIT
 - acxelements/ACX_PEAKMETER_CONFIG_INIT
dev_langs:
 - c++
---

## -description

TBD - The ACX_PEAKMETER_CONFIG_INIT function initializes an [ACX_PEAKMETER_CONFIG](ns-acxelements-acx_peakmeter_config.md) structure.

## -parameters

### -param cfg

An [ACX_PEAKMETER_CONFIG](ns-acxelements-acx_peakmeter_config.md) structure.

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Create custom circuit-element (peakmeter)
    //
    ACX_PEAKMETER_CALLBACKS_INIT(&peakmeterCallbacks);
    peakmeterCallbacks.EvtAcxPeakMeterRetrieveLevel = CodecR_EvtPeakMeterRetrieveLevelCallback;

    ACX_PEAKMETER_CONFIG_INIT(&peakmeterCfg);
    peakmeterCfg.ChannelsCount = MAX_CHANNELS;
    peakmeterCfg.Minimum = PEAKMETER_MINIMUM;
    peakmeterCfg.Maximum = PEAKMETER_MAXIMUM;
    peakmeterCfg.SteppingDelta = PEAKMETER_STEPPING_DELTA;
    peakmeterCfg.Callbacks = &peakmeterCallbacks;
```

## -see-also

[acxelements.h header](index.md)

