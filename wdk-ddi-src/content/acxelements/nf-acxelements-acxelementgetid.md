---
UID: NF:acxelements.AcxElementGetId
tech.root: audio
title: AcxElementGetId
ms.date: 12/15/2022
targetos: Windows
description: The AcxElementGetId function retrieves the number that represents the element ID for a given ACX element object.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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
 - AcxElementGetId
f1_keywords:
 - AcxElementGetId
 - acxelements/AcxElementGetId
dev_langs:
 - c++
---

## -description

The **AcxElementGetId** function retrieves the number that represents the element ID for a given ACX element object.

## -parameters

### -param Element

An existing, initialized, ACXELEMENT object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the ULONG value that represents the element ID for the specified ACXELEMENT object. Will return AcxElementIdNone if the object has no element ID.

## -remarks

### Example

Example usage is shown below.

```cpp
 ULONG id = AcxElementGetId((ACXELEMENT)Mute);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
