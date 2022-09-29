---
UID: NS:acxstreams._ACX_STREAM_BRIDGE_CONFIG
tech.root: audio
title: ACX_STREAM_BRIDGE_CONFIG
ms.date: 07/28/2022
targetos: Windows
description: The AcxStreamBridge structure is used by a circuit to propagate stream creation, states transitions and DRM settings between the endpoints circuit stream segments.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_STREAM_BRIDGE_CONFIG, *PACX_STREAM_BRIDGE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACX_STREAM_BRIDGE_CONFIG
 - PACX_STREAM_BRIDGE_CONFIG
 - ACX_STREAM_BRIDGE_CONFIG
f1_keywords:
 - _ACX_STREAM_BRIDGE_CONFIG
 - acxstreams/_ACX_STREAM_BRIDGE_CONFIG
 - PACX_STREAM_BRIDGE_CONFIG
 - acxstreams/PACX_STREAM_BRIDGE_CONFIG
 - ACX_STREAM_BRIDGE_CONFIG
 - acxstreams/ACX_STREAM_BRIDGE_CONFIG
dev_langs:
 - c++
---

## -description

The **AcxStreamBridge** structure is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.
  
### -field Flags

Bitwise OR of [ACX_STREAM_BRIDGE_CONFIG_FLAGS](ne-acxstreams-acx_stream_bridge_config_flags.md) enum.

### -field Type

The [ACX_STREAM_BRIDGE_TYPE](ne-acxstreams-acx_stream_bridge_type.md) enum that defines the type of bridge.

### -field InModesCount

The number of AUDIO_SIGNALPROCESSINGMODEs listed in InModes. These are the signal processing modes accepted as input by ACXSTREAMBRIDGE. For more information about audio modes, see [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

This field can be zero only if the InModes field is set to NULL. 

### -field InModes

A pointer to a list of AUDIO_SIGNALPROCESSINGMODE pointers supported by ACXSTREAMBRIDGE. 
This field can be NULL. A NULL GUID is a wild card value and it matches any AUDIO_SIGNALPROCESSINGMODEs.

If the input signal processing modes are not defined, the ACXSTREAMBRIDGE does not automatically match any mode. In this case, it is up to the driver to manually add the input stream to the stream bridge.

### -field OutMode

A pointer to an AUDIO_SIGNALPROCESSINGMODE that defines the audio signal processing mode of the output stream. If this field is NULL, the AUDIO_SIGNALPROCESSINGMODE_DEFAULT is used if supported by the associated ACXPIN, else the AUDIO_SIGNALPROCESSINGMODE_RAW is used. If also the latter is not supported, the output stream is created without specifying an audio signal processing mode.

### -field OutStreamVarArguments

And ACXOBJECTBAG object that is used to provide variable arguments for the output stream. This is an optional settings and can be NULL.  For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).


### -field TargetStreamAttributes

An [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that is used to define the ACXTARGETSTREAM object attributes.

## -remarks

AcxStreamBridge is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments.  This object is only used in a multi-circuit (audio composite) scenario.

A pin can be associated with zero, one or more ACXSTREAMBRIDGEs. ACX searches the associated ACXPIN's signal processing mode list for a stream signal processing mode match. The search stops at the first match.

ACX creates a default ACXSTREAMBRIDGE for a ACXCIRCUIT to ACXCIRCUIT bridge if the driver doesn't create one, and the driver didn't disable the default stream bridge handling with the AcxCircuitInitDisableDefaultStreamBridgeHandling function.

If the associated ACXPIN supports the specified audio signal processing mode, the default data-format for that audio signal processing mode is used when creating the output stream.

If the associated ACXPIN doesn't support the specified audio signal processing mode, the input stream's data format is used when creating the output stream.

The ACXSTREAMBRIDGE must be parented to an object that has ACXCIRCUIT as an ancestor.

Example usage is shown below.

```cpp
        ACXSTREAMBRIDGE             bridge          = NULL;
        ACX_STREAM_BRIDGE_CONFIG    bridgeCfg;
    
        ACX_STREAM_BRIDGE_CONFIG_INIT(&bridgeCfg);
        bridgeCfg.InModesCount = 0;     // no in-modes. this stream-bridge is manually managed. 
        bridgeCfg.InModes      = NULL; 
        bridgeCfg.OutMode      = NULL;  // no mode, i.e., default (1st), raw (2nd) or no mode (3rd).
        bridgeCfg.Flags       |= AcxStreamBridgeInvertChangeStateSequence;

        WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
        attributes.ParentObject = pin;

        status = AcxStreamBridgeCreate(Circuit, &attributes, &bridgeCfg, &bridge);
```

This example shows how to set a stream BRIDGE for RAW and DEFAULT modes.

```cpp
    //
    // Add a stream BRIDGE for RAW and DEFAULT modes.
    //
    PCGUID  inModes[] = 
    {
        &AUDIO_SIGNALPROCESSINGMODE_DEFAULT, 
        &AUDIO_SIGNALPROCESSINGMODE_RAW,
    };

    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = pin;

    ACXSTREAMBRIDGE bridge = NULL;
    ACX_STREAM_BRIDGE_CONFIG bridgeCfg;
 
    ACX_STREAM_BRIDGE_CONFIG_INIT(&bridgeCfg);
    streamCfg.InModesCount = 2;
    streamCfg.InModes      = inModes; 
    streamCfg.OutMode      = &AUDIO_SIGNALPROCESSINGMODE_DEFAULT;

    status = AcxStreamBridgeCreate(circuit, &attributes, &bridgeCfg, &bridge);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
