---
UID: NF:dbgmodel.Location.operator-sub
title: operator- function (dbgmodel.h)
description: Subtraction operator for the location function.
ms.date: 09/28/2018
keywords: ["operator- function"]
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
targetos: Windows
tech.root: debugger
f1_keywords:
 - Location::operator-
 - dbgmodel/Location::operator-
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - operator-
---

# operator- function


## -description

Subtraction operator for the location function.

## -parameters

### -param offset

Subtracts this value from the location’s offset into its address space.

## -returns

This function returns a new Location which is ‘offset’ bytes prior to this location.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)
