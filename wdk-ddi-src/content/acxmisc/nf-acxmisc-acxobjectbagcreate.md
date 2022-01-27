---
UID: NF:acxmisc.AcxObjectBagCreate
tech.root: audio
title: AcxObjectBagCreate
ms.date: 01/10/2022
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
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
 - LibDef
api_location:
 - acxmisc.h
api_name:
 - AcxObjectBagCreate
f1_keywords:
 - AcxObjectBagCreate
 - acxmisc/AcxObjectBagCreate
dev_langs:
 - c++
---

## -description

The function adds to and exisisting intialized AcxObjectBag. 
## -parameters

### -param Attributes

### -param Config

### -param ObjectBag

An intialized ObjectBag ACX object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - Example pending.

```cpp

```

## -see-also

[acxmisc.h header](index.md)

