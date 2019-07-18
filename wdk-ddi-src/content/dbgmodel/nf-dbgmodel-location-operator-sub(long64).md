---
UID: NF:dbgmodel.Location.operator-sub(LONG64)
title: operator- function (dbgmodel.h)
description: Subtraction operator for the location function.
ms.assetid: f4d60b2f-ee20-4d11-ac28-1d50fe5e8bfd
ms.date: 09/28/2018
ms.topic: function
f1_keywords:
 - "dbgmodel/operator-"
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
product:
- Windows
targetos: Windows
tech.root: debugger
---

# operator- function


## -description
Subtraction operator for the location function.


## -parameters

### -param offset
Subtracts this value from the location’s offset into its address space.  The location will then refer ‘offset’ bytes prior to where it previously did.

## -returns
This function returns a new Location which is ‘offset’ bytes prior to this location.

## -remarks

## -see-also

[dbgmodel.h header](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/)

