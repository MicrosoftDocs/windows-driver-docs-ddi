---
UID: NF:acxtargets.AcxTargetPinFlushModeDataFormatListCache
tech.root: audio
title: AcxTargetPinFlushModeDataFormatListCache
ms.date: 11/09/2022
targetos: Windows
description: The AcxTargetPinFlushModeDataFormatListCache function flushes the mode data format list cache for the specified target pin.
prerelease: false
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
 - AcxTargetPinFlushModeDataFormatListCache
f1_keywords:
 - AcxTargetPinFlushModeDataFormatListCache
 - acxtargets/AcxTargetPinFlushModeDataFormatListCache
dev_langs:
 - c++
helpviewer_keywords:
 - AcxTargetPinFlushModeDataFormatListCache
---

## -description

The **AcxTargetPinFlushModeDataFormatListCache** function flushes the mode data format list cache for the specified target pin.

## -parameters

### -param TargetPin [in]

The target pin for which to flush the mode data format list cache.

### -param SignalProcessingMode [in, optional]

The optional signal processing mode of the TargetPin.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
...
    _In_    ACXTARGETCIRCUIT TargetCircuit,
    _In_    ULONG            TargetPinId
    )

...

    //
    // Flush the target data-format cache.
    //
    AcxTargetPinFlushModeDataFormatListCache(
        AcxTargetCircuitGetTargetPin(TargetCircuit, TargetPinId),
        NULL);
```

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
