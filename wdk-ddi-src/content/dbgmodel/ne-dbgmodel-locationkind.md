---
UID: NE:dbgmodel.LocationKind
title: LocationKind (dbgmodel.h)
description: Defines the location of a field or other data.
ms.assetid: 31b989a5-1029-48b4-b4e7-c7de24615bc4
ms.date: 07/16/2018
keywords: ["LocationKind enumeration"]
f1_keywords:
 - "dbgmodel/LocationKind"
 - "LocationKind"
ms.keywords: LocationKind, , 
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- LocationKind
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# LocationKind enumeration

## -description

Defines the location of a field or other data.

## -enum-fields

### -field LocationMember
The field is a member and has an offset relative to the this pointer.
  
### -field LocationStatic 
The field is static and has an address.

### -field LocationConstant 
The field is constant and has a value.

### -field LocationNone 
The field has no location (e.g.: it has been optimized out or was a static which was defined but not declared).

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
