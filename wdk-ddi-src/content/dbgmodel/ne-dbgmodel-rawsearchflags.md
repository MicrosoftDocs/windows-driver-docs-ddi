---
UID: NE:dbgmodel.RawSearchFlags
title: RawSearchFlags (dbgmodel.h)
description: Flags to GetRawValue/EnumerateRawValues.
ms.date: 07/16/2018
keywords: ["RawSearchFlags enumeration"]
ms.keywords: RawSearchFlags, ,
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - RawSearchFlags
 - dbgmodel/RawSearchFlags
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - RawSearchFlags
---

# RawSearchFlags enumeration


## -description

Flags to GetRawValue/EnumerateRawValues.

## -enum-fields

### -field RawSearchNone 

There are no search flags. 

RawSearchNone = 0x00000000,

### -field RawSearchNoBases 

Indicates that the search should not recurse to base children (e.g.: base classes).  Only names/typeswhich are in the object itself should be returned.

RawSearchNoBases = 0x00000001,

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
