---
UID: NF:acxtargets.AcxTargetPinGetId
tech.root: audio
title: AcxTargetPinGetId
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetPinGetId given an existing ACXTARGETPIN object returns its associated ID value.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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

The **AcxTargetPinGetId** function given an existing ACXTARGETPIN object returns its associated ID value.

## -parameters

### -param TargetPin

An existing ACXTARGETPIN Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the ID associated with the specified target pin.

## -remarks

### Example

```cpp

     ACXTARGETPIN targetPin = AcxTargetCircuitGetTargetPin(TargetCircuit, pinIndex);
     ULONG pinId = AcxTargetPinGetId(targetPin);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
