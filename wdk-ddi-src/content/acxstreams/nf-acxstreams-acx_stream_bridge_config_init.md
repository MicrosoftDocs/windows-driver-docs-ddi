---
UID: NF:acxstreams.ACX_STREAM_BRIDGE_CONFIG_INIT
tech.root: audio
title: ACX_STREAM_BRIDGE_CONFIG_INIT
ms.date: 07/21/2021
targetos: Windows
description: The ACX_STREAM_BRIDGE_CONFIG_INIT function initializes an ACX stream bridge config structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - ACX_STREAM_BRIDGE_CONFIG_INIT
f1_keywords:
 - ACX_STREAM_BRIDGE_CONFIG_INIT
 - acxstreams/ACX_STREAM_BRIDGE_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The ACX_STREAM_BRIDGE_CONFIG_INIT function initializes an [ACX_STREAM_BRIDGE_CONFIG](ns-acxstreams-acx_stream_bridge_config.md) structure.

## -parameters

### -param Config

A pointer to the [ACX_STREAM_BRIDGE_CONFIG](ns-acxstreams-acx_stream_bridge_config.md) structure.

## -remarks

Drivers should call ACX_STREAM_BRIDGE_CONFIG_INIT when creating an ACXSTREAMBRIDGE.
This function resets the [ACX_STREAM_BRIDGE_CONFIG structure](ns-acxstreams-acx_stream_bridge_config.md) and initializes the Type field to AcxStreamBridgeDefaultType. 

### Example

```cpp
    ACX_STREAM_BRIDGE_CONFIG bridgeCfg;

    ACX_STREAM_BRIDGE_CONFIG_INIT(&bridgeCfg);
    streamCfg.InModesCount = 1;
    streamCfg.InModes      = inModes; 
    streamCfg.OutMode      = &AUDIO_SIGNALPROCESSINGMODE_DEFAULT;
```

## -see-also

[acxstreams.h header](index.md)

READY2GO

EDITCOMPLETE