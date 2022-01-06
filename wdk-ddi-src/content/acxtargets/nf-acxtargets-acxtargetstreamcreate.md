---
UID: NF:acxtargets.AcxTargetStreamCreate
tech.root: audio
title: AcxTargetStreamCreate
ms.date:  11/11/2021
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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

## -parameters

### -param Device

### -param Attributes

### -param Config

### -param TargetStream

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

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

        ACX_TARGET_STREAM_CONFIG_INIT(&targetStreamCfg);
        targetStreamCfg.TargetCircuit = pinCtx->TargetPins[i]->TargetCircuit;
        targetStreamCfg.PinId = pinCtx->TargetPins[i]->TargetPinId;
        targetStreamCfg.DataFormat = StreamFormat;
        targetStreamCfg.SignalProcessingMode = SignalProcessingMode;
        targetStreamCfg.OptionalParameters = VarArguments;

        status = AcxTargetStreamCreate(Device, &attributes, &targetStreamCfg, &streamCtx->TargetStreams[i]);
```

## -see-also

[acxtargets.h header](index.md)