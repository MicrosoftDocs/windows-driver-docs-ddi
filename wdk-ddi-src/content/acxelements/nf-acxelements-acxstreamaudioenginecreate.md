---
UID: NF:acxelements.AcxStreamAudioEngineCreate
tech.root: audio 
title: AcxStreamAudioEngineCreate
ms.date: 09/23/2021
targetos: Windows
description: TBD - The AcxStreamAudioEngineCreate function is used to create a stream audio engine that that will be associated with a stream ACX object parent. 
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
 - AcxStreamAudioEngineCreate
f1_keywords:
 - AcxStreamAudioEngineCreate
 - acxelements/AcxStreamAudioEngineCreate
dev_langs:
 - c++
---

## -description

TBD - The AcxStreamAudioEngineCreate function is used to create a stream audio engine that that will be associated with a stream ACX object parent. 

## -parameters

### -param Stream

An ACXSTREAM object that represents an audio stream on a specific circuit’s hardware. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param AudioEngine

An ACXAUDIOENGINE audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the stream audio engine with the parent stream object (TBD???).

### -param Config

An initialized [ACX_STREAMAUDIOENGINE_CONFIG structure](ns-acxelements-acx_streamaudioengine_config.md) that describes the configuration of the audio engine.

### -param StreamAudioEngine

A pointer to a location that receives the handle to the newly created ACXSTREAMAUDIOENGINE ACX audio stream engine object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                        status;
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACXSTREAM                       stream;
    ACXELEMENT                      elements[2] = {0};
    ACX_STREAMAUDIOENGINE_CONFIG    audioEngineCfg;

        ACX_STREAMAUDIOENGINE_CONFIG_INIT(&audioEngineCfg);
        audioEngineCfg.VolumeElement = volumeElement;
        audioEngineCfg.MuteElement = muteElement;
        audioEngineCfg.PeakMeterElement = peakmeterElement;
        audioEngineCfg.Callbacks = &streamAudioEngineCallbacks;

        WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_STREAMAUDIOENGINE_CONTEXT);
        attributes.ParentObject = stream;

        status = AcxStreamAudioEngineCreate(stream, circuitCtx->AudioEngineElement, &attributes, &audioEngineCfg, (ACXSTREAMAUDIOENGINE*)&elements[0]);
```

## -see-also

[acxelements.h header](index.md)

