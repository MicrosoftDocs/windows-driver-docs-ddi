---
UID: NF:dbgmodel.Location.operator-add-assign(LONG64)
title: operator+= function (dbgmodel.h)
description: The addition assignment operator for the location function.
ms.assetid: 18523fa0-dc61-4830-8b66-919d9e754a36
ms.date: 09/28/2018
ms.topic: function
ms.keywords: operator+=
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
- operator+=
product:
- Windows
targetos: Windows
tech.root: debugger
---

# operator+= function


## -description
The addition assignment operator for the location function.

## -parameters

### -param offset
Subtracts this value from the location’s offset into its address space.  The location will then refer ‘offset’ bytes prior to where it previously did.


## -returns
This function returns Location &.
## -remarks

## -see-also

[dbgmodel.h header](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgmodel/)

