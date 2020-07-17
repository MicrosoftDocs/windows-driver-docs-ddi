---
UID: NF:dbgmodel.Location.operator-add(LONG64)
title: operator+ function (dbgmodel.h)
description: The addition operator for the location function.
ms.assetid: eb66b429-1dfa-4a52-a812-b1aeb45cc088
ms.date: 09/28/2018
keywords: ["operator+ function"]
f1_keywords:
 - "dbgmodel/operator+"
 - "operator+"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- operator+
product:
- Windows
targetos: Windows
tech.root: debugger
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
