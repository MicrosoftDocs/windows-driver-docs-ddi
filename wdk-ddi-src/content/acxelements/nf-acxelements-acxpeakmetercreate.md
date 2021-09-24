---
UID: NF:acxelements.AcxPeakMeterCreate
tech.root: audio 
title: AcxPeakMeterCreate
ms.date: 09/22/2021
targetos: Windows
description: TBD - The AcxPeakMeterCreate function is used to create an ACX peak meter object that that will be associated with a circuit object parent. 
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
 - AcxPeakMeterCreate
f1_keywords:
 - AcxPeakMeterCreate
 - acxelements/AcxPeakMeterCreate
dev_langs:
 - c++
---

## -description

TBD - The AcxPeakMeterCreate function is used to create an ACX peak meter object that that will be associated with a circuit object (TBD???) parent. 

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit. TBD - conditional on something to determine if this is the parent?

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the peakmeter object with the parent circuit object (TBD???).

### -param Config

An initialized [ACX_PEAKMETER_CONFIG structure](ns-acxelements-acx_peakmeter_config.md) that describes the configuration of the audio level peak meter.

### -param PeakMeter

A pointer to a location that receives the handle to the newly created ACXPEAKMETER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    WDF_OBJECT_ATTRIBUTES           attributes;
 
    ACX_PEAKMETER_CALLBACKS         peakmeterCallbacks;
    ACX_PEAKMETER_CONFIG            peakmeterCfg;
    ACXPEAKMETER                    peakmeterElement;
    CODEC_PEAKMETER_ELEMENT_CONTEXT*peakmeterCtx;

    ACX_PEAKMETER_CALLBACKS_INIT(&peakmeterCallbacks);
    peakmeterCallbacks.EvtAcxPeakMeterRetrieveLevel = CodecR_EvtPeakMeterRetrieveLevelCallback;

    ACX_PEAKMETER_CONFIG_INIT(&peakmeterCfg);
    peakmeterCfg.ChannelsCount = MAX_CHANNELS;
    peakmeterCfg.Minimum = PEAKMETER_MINIMUM;
    peakmeterCfg.Maximum = PEAKMETER_MAXIMUM;
    peakmeterCfg.SteppingDelta = PEAKMETER_STEPPING_DELTA;
    peakmeterCfg.Callbacks = &peakmeterCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_PEAKMETER_ELEMENT_CONTEXT);
    attributes.ParentObject = Circuit;

    status = AcxPeakMeterCreate(Circuit, &attributes, &peakmeterCfg, &peakmeterElement);
```

## -see-also

[acxelements.h header](index.md)

