---
UID: NF:acxtargets.AcxTargetStreamGetWdfIoTarget
tech.root: audio
title: AcxTargetStreamGetWdfIoTarget
ms.date: 07/22/2022
targetos: Windows
description: The AcxTargetStreamGetWdfIoTarget function returns a WDFIOTARGET WDF object that is associated with the specified stream. 
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
 - AcxTargetStreamGetWdfIoTarget
f1_keywords:
 - AcxTargetStreamGetWdfIoTarget
 - acxtargets/AcxTargetStreamGetWdfIoTarget
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamGetWdfIoTarget** function will return a WDFIOTARGET WDF object that is associated with the specified stream.

## -parameters

### -param TargetStream

An existing ACXTARGETSTREAM Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the WDFIOTARGET WDF object that is associated with the specified target stream.

## -remarks

### Example

```cpp
WDFIOTARGET
Aggregator_GetTarget(
    _In_ ACXTARGETSTREAM Stream
)
{
    PAGED_CODE();
    return AcxTargetStreamGetWdfIoTarget(Stream);
}
```

## -see-also

- [acxtargets.h header](index.md)

