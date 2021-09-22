---
UID: NF:acxelements.AcxStreamAudioEngineCreate
tech.root: audio 
title: AcxStreamAudioEngineCreate
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

## -parameters

### -param Stream



### -param AudioEngine

An ACXAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the AcxFactory with the parent WDF device object (TBD???).

TBD - What would be useful to set for the driver?

### -param Config

An initialized [ACX_ACXAUDIOENGINE_CONFIG structure](ns-acxelements-acx_audioengine_config.md) that describes the configuration of the audio engine.

### -param StreamAudioEngine

A pointer to a location that receives the handle to the newly created ACXSTREAMAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxelements.h header](index.md)

