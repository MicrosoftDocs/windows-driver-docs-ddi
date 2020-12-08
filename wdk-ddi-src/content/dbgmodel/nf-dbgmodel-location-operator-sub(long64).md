---
UID: NF:dbgmodel.Location.operator-sub(LONG64)
title: operator-(LONG64) function (dbgmodel.h)
description: Subtraction operator for the location function.
ms.date: 09/28/2018
keywords: ["operator- function"]
f1_keywords:
 - "dbgmodel/operator-"
 - "operator-"
ms.keywords: operator-
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- operator-
targetos: Windows
tech.root: debugger
---

# operator-(LONG64) function


## -description
Subtraction operator for the location function.


## -parameters

### -param offset
Subtracts this value from the location’s offset into its address space.  The location will then refer ‘offset’ bytes prior to where it previously did.

## -returns
This function returns a new Location which is ‘offset’ bytes prior to this location.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)
