---
UID: NS:acxelements._ACX_PEAKMETER_CALLBACKS
tech.root: audio 
title: ACX_PEAKMETER_CALLBACKS
ms.date: 09/02/2021
targetos: Windows
description: The ACX_PEAKMETER_CALLBACKS structure identifies the driver callbacks for ACX peakmeter operations.
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
req.typenames: ACX_PEAKMETER_CALLBACKS, *PACX_PEAKMETER_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_PEAKMETER_CALLBACKS
 - PACX_PEAKMETER_CALLBACKS
 - ACX_PEAKMETER_CALLBACKS
f1_keywords:
 - _ACX_PEAKMETER_CALLBACKS
 - acxelements/_ACX_PEAKMETER_CALLBACKS
 - PACX_PEAKMETER_CALLBACKS
 - acxelements/PACX_PEAKMETER_CALLBACKS
 - ACX_PEAKMETER_CALLBACKS
 - acxelements/ACX_PEAKMETER_CALLBACKS
dev_langs:
 - c++
---

## -description

The ACX_PEAKMETER_CALLBACKS structure identifies the driver callbacks for ACX peakmeter operations.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field EvtAcxPeakMeterRetrieveLevel

The [ACX_PEAKMETER_RETRIEVE_LEVEL](nc-acxelements-evt_acx_peakmeter_retrieve_level.md) callback.

### -field EvtAcxPeakMeterProcessRequest

TBD TBD 

The [EVT_ACX_OBJECT_PROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/acxrequest/nc-acxrequest-evt_acx_object_process_request.md) callback. 

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_PEAKMETER_CALLBACKS         peakmeterCallbacks;
    ACX_PEAKMETER_CONFIG            peakmeterCfg;
    ACXPEAKMETER                    peakmeterElement;

...
        ACX_PEAKMETER_CALLBACKS peakmeterCallbacks;
        ACX_PEAKMETER_CALLBACKS_INIT(&peakmeterCallbacks);
        peakmeterCallbacks.EvtAcxPeakMeterRetrieveLevel = CodecR_EvtPeakMeterRetrieveLevelCallback;

        ACX_PEAKMETER_CONFIG peakmeterCfg;
        ACX_PEAKMETER_CONFIG_INIT(&peakmeterCfg);
        peakmeterCfg.ChannelsCount = MAX_CHANNELS;
        peakmeterCfg.Minimum = PEAKMETER_MINIMUM;
        peakmeterCfg.Maximum = PEAKMETER_MAXIMUM;
        peakmeterCfg.SteppingDelta = PEAKMETER_STEPPING_DELTA;
        peakmeterCfg.Callbacks = &peakmeterCallbacks;
```

## -see-also

- [acxelements.h header](index.md)

