---
UID: NE:acxstreams._ACX_STREAM_BRIDGE_TYPE
tech.root: audio
title: ACX_STREAM_BRIDGE_TYPE
ms.date: 07/28/2022
targetos: Windows
description: The ACX_STREAM_BRIDGE_TYPE enumeration describes the Acx Stream Bridge Type.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxstreams.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - _ACX_STREAM_BRIDGE_TYPE
 - ACX_STREAM_BRIDGE_TYPE
f1_keywords:
 - _ACX_STREAM_BRIDGE_TYPE
 - acxstreams/_ACX_STREAM_BRIDGE_TYPE
 - ACX_STREAM_BRIDGE_TYPE
 - acxstreams/ACX_STREAM_BRIDGE_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_STREAM_BRIDGE_TYPE** enumeration describes the Acx Stream Bridge Type.

## -enum-fields

### -field AcxStreamBridgeInvalidType

The Acx Stream Bridge is an InvalidType.

### -field AcxStreamBridgeMux

The Acx Stream Bridge is an Mux. This bridge type accepts multiple input streams and allows only one output stream.

### -field AcxStreamBridgeMaximumType

The AcxStreamBridgeMaximumType is used internally for validation. Do not use.

### -field AcxStreamBridgeDefaultType

The default type is associated with one of the valid types for this field. This is the type used if the driver does not override this value.

## -remarks

AcxStreamBridge is used by a circuit to propagate stream creation, the stream’s states transitions and DRM settings between the endpoint's circuit stream segments. This object is only used in a multi-circuit (audio composite) scenario.

### Example

Example usage is shown below.

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
