---
UID: NE:acxrequest._ACX_ITEM_TYPE
tech.root: audio
title: ACX_ITEM_TYPE
ms.date: 07/26/2022
targetos: Windows
description: The ACX_ITEM_TYPE enumeration describes the possible types of items.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_ITEM_TYPE
 - PACX_ITEM_TYPE
 - ACX_ITEM_TYPE
f1_keywords:
 - _ACX_ITEM_TYPE
 - acxrequest/_ACX_ITEM_TYPE
 - PACX_ITEM_TYPE
 - acxrequest/PACX_ITEM_TYPE
 - ACX_ITEM_TYPE
 - acxrequest/ACX_ITEM_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_ITEM_TYPE** enumeration describes the possible types of items.

## -enum-fields

### -field AcxItemTypeDefault

The default type.

### -field AcxItemTypeCircuit

A Circuit type.

### -field AcxItemTypeStream

A Stream type.

### -field AcxItemTypeFactoryCircuit

A FactoryCircuit type.

### -field AcxItemTypePin

A Pin type.

### -field AcxItemTypeElement

An Element type.

### -field AcxItemTypeMax

For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

Sample pending

```cpp

```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)

