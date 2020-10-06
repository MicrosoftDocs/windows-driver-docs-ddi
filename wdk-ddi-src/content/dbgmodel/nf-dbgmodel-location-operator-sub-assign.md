---
UID: NF:dbgmodel.Location.operator-sub-assign
title: operator-= function (dbgmodel.h)
description: The subtraction assignment operator for the location function.
ms.assetid: 77948015-8e09-4f07-b04a-85a868bb8359
ms.date: 09/28/2018
keywords: ["operator-= function"]
ms.keywords: operator-=
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
 - Location::operator-=
 - dbgmodel/Location::operator-=
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - operator-=
---

# operator-= function


## -description

The subtraction assignment operator for the location function.

## -parameters

### -param offset

Subtracts this value from the location’s offset into its address space.  The location will then refer ‘offset’ bytes prior to where it previously did.

## -returns

This function returns Location &.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)