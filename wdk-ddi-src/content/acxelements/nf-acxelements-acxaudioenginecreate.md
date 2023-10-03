---
UID: NF:acxelements.AcxAudioEngineCreate
tech.root: audio
title: AcxAudioEngineCreate
ms.date: 12/15/2022
targetos: Windows
description: The AcxAudioEngineCreate function is used to create an audio engine that that will be associated with a circuit WDFDEVICE device object parent.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxAudioEngineCreate
f1_keywords:
 - AcxAudioEngineCreate
 - acxelements/AcxAudioEngineCreate
dev_langs:
 - c++
---

## -description

The **AcxAudioEngineCreate** function is used to create an audio engine that that will be associated with a circuit WDFDEVICE device object parent.

## -parameters

### -param Object

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit.

### -param Attributes

A [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that is used to associate the AcxAudioEngine with the parent circuit object. Note that additional WDF attributes such as as WDF_EXECUTION_LEVEL or WDF_SYNCHRONIZATION_SCOPE, should not be set using the *Attributes* parameter as they are a managed by ACX.

### -param Config

An initialized [ACX_AUDIOENGINE_CONFIG structure](ns-acxelements-acx_audioengine_config.md) that describes the configuration of the audio engine.

### -param AudioEngine

A pointer to a location that receives the handle to the new ACXAUDIOENGINE object that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                        status;
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACX_AUDIOENGINE_CONFIG          audioEngineCfg;

    ACX_AUDIOENGINE_CONFIG_INIT(&audioEngineCfg);

    audioEngineCfg.HostPin = Pins[HostPin];
    audioEngineCfg.OffloadPin = Pins[OffloadPin];
    audioEngineCfg.LoopbackPin = Pins[LoopbackPin];
    audioEngineCfg.VolumeElement = volumeElement;
    audioEngineCfg.MuteElement = muteElement;
    audioEngineCfg.PeakMeterElement = peakmeterElement;
    audioEngineCfg.Callbacks = &audioEngineCallbacks;

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_ENGINE_CONTEXT);
    attributes.ParentObject = Circuit;

    status = AcxAudioEngineCreate(Circuit, &attributes, &audioEngineCfg, AudioEngine);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
