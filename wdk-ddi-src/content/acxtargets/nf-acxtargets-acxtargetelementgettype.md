---
UID: NF:acxtargets.AcxTargetElementGetType
tech.root: audio
title: AcxTargetElementGetType
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetElementGetType function given an existing ACXTARGETELEMENT object, returns its corresponding element type in the form of a GUID.
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
 - AcxTargetElementGetType
f1_keywords:
 - AcxTargetElementGetType
 - acxtargets/AcxTargetElementGetType
dev_langs:
 - c++
---

## -description

The **AcxTargetElementGetType** function given an existing ACXTARGETELEMENT object, returns its corresponding element type  in the form of a GUID.

## -parameters

### -param TargetElement

An existing ACXTARGETELEMENT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

An element type as a GUID.

## -remarks

### Example

```cpp

    ACXTARGETELEMENT targetElement = AcxTargetCircuitGetTargetElement(TargetCircuit, elementIndex);
    GUID elementType = AcxTargetElementGetType(targetElement);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
