---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION
ms.date: 08/27/2021
targetos: Windows
description: 
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
 - LibDef
api_location:
 - acxelements.h
api_name:
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_LINEAR_BUFFER_POSITION
dev_langs:
 - c++
---

## -description

## -parameters

### -param StreamAudioEngine

An ACXSTREAMAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Position

The stream position in bytes (TBD??). This is a (0/1) based on location.

TBD - Need to better describe if this is relative to the stream, etc. And if still applies [Audio Position Property](/windows-hardware/drivers/audio/audio-position-property)

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxelements.h header](index.md)

