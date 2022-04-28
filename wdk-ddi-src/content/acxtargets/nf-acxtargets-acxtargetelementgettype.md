---
UID: NF:acxtargets.AcxTargetElementGetType
tech.root: audio
title: AcxTargetElementGetType
ms.date: 04/27/2022
targetos: Windows
description: The AcxTargetElementGetType function given an existing ACXTARGETELEMENT object returns an element type in the form of a GUID.
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
 - AcxTargetElementGetType
f1_keywords:
 - AcxTargetElementGetType
 - acxtargets/AcxTargetElementGetType
dev_langs:
 - c++
---

## -description

The **AcxTargetElementGetType** function given an existing ACXTARGETELEMENT object returns an element type in the form of a GUID.

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

## -see-also

- [acxtargets.h header](index.md)

