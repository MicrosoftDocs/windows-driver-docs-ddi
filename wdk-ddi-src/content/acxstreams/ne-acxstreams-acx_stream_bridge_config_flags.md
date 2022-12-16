---
UID: NE:acxstreams._ACX_STREAM_BRIDGE_CONFIG_FLAGS
tech.root:
title: ACX_STREAM_BRIDGE_CONFIG_FLAGS
ms.date: 07/28/2022
targetos: Windows
description: The ACX_STREAM_BRIDGE_CONFIG_FLAGS enumeration describes the Acx Stream Bridge config flags.
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
 - _ACX_STREAM_BRIDGE_CONFIG_FLAGS
 - ACX_STREAM_BRIDGE_CONFIG_FLAGS
f1_keywords:
 - _ACX_STREAM_BRIDGE_CONFIG_FLAGS
 - acxstreams/_ACX_STREAM_BRIDGE_CONFIG_FLAGS
 - ACX_STREAM_BRIDGE_CONFIG_FLAGS
 - acxstreams/ACX_STREAM_BRIDGE_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_STREAM_BRIDGE_CONFIG_FLAGS** enumeration describes the Acx Stream Bridge config flags.

## -enum-fields

### -field AcxStreamBridgeConfigNoFlags

The Acx Stream Bridge config has no flags.

### -field AcxStreamBridgeInvertChangeStateSequence

Use this flag to invert the stream state change notification sequence. 

**Default endpoint stream state change when going from STOP to RUN:**

- For a render endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the streaming circuit and ending with the stream of circuit with the device bring pin. 

- For a capture endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the circuit with the device bridge pin and ending with the stream of the streaming circuit.

**Default endpoint stream state change when going from RUN to STOP:**

- For a render endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the circuit with the device bridge pin and ending with the stream of the streaming circuit.

- For a capture endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the streaming circuit and ending with the stream of circuit with the device bring pin. 

**Inverted sequence when going from STOP to RUN:**

For a render endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the circuit with the device bridge pin and ending with the stream of the streaming circuit.

For a capture endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the streaming circuit and ending with the stream of circuit with the device bring pin.

**Inverted sequence when going from RUN to STOP:**

- For a render endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the streaming circuit and ending with the stream of circuit with the device bring pin. 

- For a capture endpoints, ACX notifies each circuit's stream of a multi-circuit endpoint, starting with the stream of the circuit with the device bridge pin and ending with the stream of the streaming circuit.

### -field AcxStreamBridgeForwardInStreamVarArguments

When this flag is set, ACX forwards the current stream's variable arguments *ACXOBJECTBAG* to the next stream of a multi-circuit endpoint. If there is no variable arguments object-bag associated with the current stream, ACX forwards the variable arguments object-bag specified at stream bridge creation time if present. For more information about ACX Objects, such as *ACXOBJECTBAG*, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -field AcxStreamBridgeConfigValidFlags

This is a bitwise OR of all the flags allowed to be set. This is used internally to validate the [ACX_STREAM_BRIDGE_CONFIG Structure](ns-acxstreams-acx_stream_bridge_config.md) fields.

## -remarks

You can specify a valid bitwise OR of the values on this page for the Flags member of the [ACX_STREAM_BRIDGE_CONFIG Structure](ns-acxstreams-acx_stream_bridge_config.md).

### Example

Example usage is shown below.

```cpp
    ACX_STREAM_BRIDGE_CONFIG_INIT(&streamCfg);
    streamCfg.InModesCount = SIZEOF_ARRAY(inModes);
    streamCfg.InModes      = inModes; 
    streamCfg.OutMode      = NULL;  // no mode, i.e., default (1st) and raw (2nd).
    streamCfg.OutStreamVarArguments = objBag;

    // Reverse the change-state sequence notifications. 
    streamCfg.Flags       |= AcxStreamBridgeInvertChangeStateSequence;

    status = AcxStreamBridgeCreate(circuit, &attributes, &streamCfg, &streamBridge);
```


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
