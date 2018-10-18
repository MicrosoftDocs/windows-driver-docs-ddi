---
UID: NE:dbgmodel.RawSearchFlags
title: RawSearchFlags
author: windows-driver-content
description: Flags to GetRawValue/EnumerateRawValues.
ms.assetid: 1f876ef9-9130-45f0-8c00-33f5f0e41344
ms.date: 07/16/2018
ms.topic: enum
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	RawSearchFlags
product: Windows
targetos: Windows
tech.root: debugger
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

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
