---
UID: NF:acxstreams.AcxStreamBridgeCreate
tech.root: audio
title: AcxStreamBridgeCreate
ms.date: 12/16/2022
targetos: Windows
description: The AcxStreamBridgeCreate function uses a stream configuration to create a StreamBridge for a circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - AcxStreamBridgeCreate
f1_keywords:
 - AcxStreamBridgeCreate
 - acxstreams/AcxStreamBridgeCreate
dev_langs:
 - c++
---

## -description

The **AcxStreamBridgeCreate** function uses a ACX_STREAM_BRIDGE_CONFIG to create a StreamBridge for a circuit.

An ACXSTREAMBRIDGE is used by a circuit to propagate a stream creation, stream's states transitions and DRM settings between the endpoint's circuit stream segments. This object is only used in a multi-circuit (audio composite) scenario.

## -parameters

### -param AcxCircuit

A pointer to a location that receives a handle to the associated ACXCIRCUIT Object. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object's values: cleanup and destroy callbacks, context type, and to specify its parent object. For more information, see [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure and the remarks section of this topic.

### -param Config

An [ACX_STREAM_BRIDGE_CONFIG](ns-acxstreams-acx_stream_bridge_config.md) structure that defines the configuration.

### -param StreamBridge

A pointer to a location that receives a handle to the new ACXSTREAMBRIDGE Object.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An audio endpoint is a collection of one or more audio circuits (ACXCIRCUIT objects) which are assembled to create a complete audio path. An ACX driver normally creates audio circuits for different audio endpoints, although ACX doesn't prohibit circuits created by the same driver to be part of the same audio endpoint's collection, as long as they belong to a different device stack. An audio endpoint is a collection of audio circuits created by the same or different audio drivers.

By default, the new ACXSTREAMBRIDGE object's parent is the specified ACXCIRCUIT. You can use the ParentObject member of the WDF_OBJECT_ATTRIBUTES structure to specify a different parent with ACXCIRCUIT as ancestor. The framework deletes the ACXSTREAMBRIDGE object when it deletes the parent object.

Your driver can delete the ACXSTREAMBRIDGE object when it has finished using the object; otherwise, the object will remain until the parent is deleted, which is the case when it is created during the ACXCIRCUIT initialization/creation.

A pin can be associated with zero, one or more ACXSTREAMBRIDGEs. ACX searches the associated ACXPIN's signal processing mode list for a stream signal processing mode match. The search stops at the first match.

ACX creates a default ACXSTREAMBRIDGE for a ACXCIRCUIT to ACXCIRCUIT bridge if the driver doesn't create one, and the driver didn't disable the default stream bridge handling with the AcxCircuitInitDisableDefaultStreamBridgeHandling function.

### Example

Example usage is shown below.

```cpp
    ACX_STREAM_BRIDGE_CONFIG bridgeCfg;
    ACXSTREAMBRIDGE          bridge = NULL;
    
    ACX_STREAM_BRIDGE_CONFIG_INIT(&bridgeCfg);
    bridgeCfg.InModesCount = 1;
    bridgeCfg.InModes      = inModes; 
    bridgeCfg.OutMode      = &AUDIO_SIGNALPROCESSINGMODE_DEFAULT;

    status = AcxStreamBridgeCreate(circuit, &attributes, &bridgeCfg, &bridge);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
