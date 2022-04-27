---
UID: NF:acxtargets.AcxTargetPinGetId
tech.root: audio
title: AcxTargetPinGetId
ms.date: 04/26/2022
targetos: Windows
description: The AcxTargetPinGetId given an existing ACXTARGETPIN object returns an Id value.
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
 - AcxTargetPinGetId
f1_keywords:
 - AcxTargetPinGetId
 - acxtargets/AcxTargetPinGetId
dev_langs:
 - c++
---

## -description

The **AcxTargetPinGetId** function given an existing ACXTARGETPIN object returns an Id value.

## -parameters

### -param TargetPin

A pointer to the location of an existing ACXTARGETPIN Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).
## -remarks

### Example

```cpp
     ACXTARGETPIN targetPin = AcxTargetCircuitGetTargetPin(TargetCircuit, pinIndex);
     ULONG PinId = AcxTargetPinGetId(targetPin);
```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic