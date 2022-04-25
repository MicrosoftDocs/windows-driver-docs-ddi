---
UID: NS:acxtargets._ACX_TARGET_STREAM_CONFIG
tech.root: audio
title: ACX_TARGET_STREAM_CONFIG
ms.date: 01/05/2022
targetos: Windows
description: The ACX_TARGET_STREAM_CONFIG structure is used to define the target stream configuration. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_TARGET_STREAM_CONFIG, *PACX_TARGET_STREAM_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxtargets.h
api_name:
 - _ACX_TARGET_STREAM_CONFIG
 - PACX_TARGET_STREAM_CONFIG
 - ACX_TARGET_STREAM_CONFIG
f1_keywords:
 - _ACX_TARGET_STREAM_CONFIG
 - acxtargets/_ACX_TARGET_STREAM_CONFIG
 - PACX_TARGET_STREAM_CONFIG
 - acxtargets/PACX_TARGET_STREAM_CONFIG
 - ACX_TARGET_STREAM_CONFIG
 - acxtargets/ACX_TARGET_STREAM_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_TARGET_STREAM_CONFIG** structure is used to define the target stream configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Flags

Target stream configuration flags defined by the [ACX_TARGET_STREAM_CONFIG_FLAGS enum](ne-acxtargets-acx_target_stream_config_flags.md). 

No flag bits are currently defined. Set this member to zero - AcxTargetStreamConfigNoFlags

### -field TargetCircuit

An ACXTARGETCIRCUIT object representing the target circuit.

### -field PinId

The Pin ID number.

### -field DataFormat

An ACXDATAFORMAT ACX object that defines the target stream data format.

### -field SignalProcessingMode

A GUID identifying the audio signal processing mode of the new stream circuit.For more information about
audio modes, see [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

### -field OptionalParameters

TBD - An ACXOBJECTBAG ACX object describing optional parameters.

Use this for TBD. 

## -remarks

### Example

```cpp
    ACX_TARGET_STREAM_CONFIG            targetStreamCfg;

    ACX_TARGET_STREAM_CONFIG_INIT(&targetStreamCfg);
```

## -see-also

- [acxtargets.h header](index.md)