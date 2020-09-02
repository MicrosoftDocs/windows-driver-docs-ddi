---
UID: NF:dbgmodel.Location.operator-add
title: operator+ function (dbgmodel.h)
description: The addition operator for the location function.
ms.assetid: 1e19ed69-4afb-4e43-9dc7-912e7f89001d
ms.date: 09/28/2018
keywords: ["operator+ function"]
ms.keywords: operator+
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
 - Location::operator+
 - dbgmodel/Location::operator+
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - operator+
---

# operator+ function


## -description

The addition operator for the location function.

## -parameters

### -param offset

Adds this value from the location’s offset into its address space.

## -returns

This function returns a new Location which is ‘offset’ bytes after this location.

## -remarks

## -see-also

[dbgmodel.h header](https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgmodel/)

