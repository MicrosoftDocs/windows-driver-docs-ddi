---
UID: NF:acxtargets.AcxTargetStreamGetTargetElement
tech.root: audio
title: AcxTargetStreamGetTargetElement
ms.date: 07/22/2022
targetos: Windows
description: The AcxTargetStreamGetTargetElement function, given a valid element index value, returns the corresponding ACXTARGETELEMENT ACX object that is associated with the specified stream.
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
 - AcxTargetStreamGetTargetElement
f1_keywords:
 - AcxTargetStreamGetTargetElement
 - acxtargets/AcxTargetStreamGetTargetElement
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamGetTargetElement** function, given a valid element index value, returns the corresponding ACXTARGETELEMENT ACX object that is associated with the specified stream.

## -parameters

### -param TargetStream

An existing ACXTARGETSTREAM object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ElementIndex

The numeric index value for the specified element.

## -returns

Returns an ACXTARGETELEMENT ACX object that is associated with the specified stream.

## -remarks

Sample Pending

### Example

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)

