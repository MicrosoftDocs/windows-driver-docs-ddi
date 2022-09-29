---
UID: NF:acxtargets.AcxTargetElementGetNameTag
tech.root: audio
title: AcxTargetElementGetNameTag
ms.date: 07/22/2022
targetos: Windows
description: The AcxTargetElementGetNameTag given an existing ACXTARGETELEMENT object, returns its name-tag in the form of a GUID.
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
 - AcxTargetElementGetNameTag
f1_keywords:
 - AcxTargetElementGetNameTag
 - acxtargets/AcxTargetElementGetNameTag
dev_langs:
 - c++
---

## -description

The **AcxTargetElementGetNameTag** function given an existing ACXTARGETELEMENT object returns, returns its name-tag in the form of a GUID.

## -parameters

### -param TargetElement

An existing ACXTARGETELEMENT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

A name-tag in the form of a GUID.

## -remarks

### Example

```cpp

    GUID elementNameTag;
...

    elementNameTag = AcxTargetElementGetNameTag(targetElement);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
 
