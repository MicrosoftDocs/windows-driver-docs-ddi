---
UID: NF:acxtargets.AcxTargetStreamCreate
tech.root: audio
title: AcxTargetStreamCreate
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetStreamCreate function is used to create a target stream.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetStreamCreate
f1_keywords:
 - AcxTargetStreamCreate
 - acxtargets/AcxTargetStreamCreate
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamCreate** function is used to create a target stream.

## -parameters

### -param Device

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the current ACXCIRCUIT.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various object's values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An initialized [ACX_TARGET_STREAM_CONFIG structure](ns-acxtargets-acx_target_stream_config.md) that describes the configuration of the target stream.

### -param TargetStream

A pointer to a location that receives a handle to the new ACXTARGETSTREAM Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Drivers should use the ACXSTREAMBRIDGE to automatically propagate an audio stream down-level to the other connected circuits.

### Example

```cpp

    WDF_OBJECT_ATTRIBUTES               attributes;
    PAGGREGATOR_PIN_CONTEXT             pinCtx;
    ACXSTREAM                           stream;
    AGGREGATOR_STREAM_CONTEXT*          streamCtx;
    ACX_TARGET_STREAM_CONFIG            targetStreamCfg;

    streamCtx = GetAggregatorStreamContext(stream);
    ASSERT(streamCtx);
    streamCtx->StreamState = AcxStreamStateStop;

    pinCtx = GetAggregatorPinContext(Pin);

    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = stream;

...

        ACX_TARGET_STREAM_CONFIG_INIT(&targetStreamCfg);
        targetStreamCfg.TargetCircuit = pinCtx->TargetPins[i]->TargetCircuit;
        targetStreamCfg.PinId = pinCtx->TargetPins[i]->TargetPinId;
        targetStreamCfg.DataFormat = StreamFormat;
        targetStreamCfg.SignalProcessingMode = SignalProcessingMode;
        targetStreamCfg.OptionalParameters = VarArguments;

...

        status = AcxTargetStreamCreate(Device, &attributes, &targetStreamCfg, &streamCtx->TargetStreams[i]);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
