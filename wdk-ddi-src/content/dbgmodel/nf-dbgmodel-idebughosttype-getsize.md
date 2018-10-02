---
UID: NF:dbgmodel.IDebugHostType.GetSize
title: IDebugHostType::GetSize
author: windows-driver-content
description: TBD
ms.assetid: 22a802d1-119b-42d5-9163-f2db9dedbc5c
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType::GetSize, GetSize, IDebugHostType.GetSize, IDebugHostType::GetSize, IDebugHostType.GetSize
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostType.GetSize
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostType::GetSize


## -description

The GetSize method returns the size of the type (as if one had done sizeof(type) in C++). 

## -parameters

### -param size
The size of the type will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type (see FindTypeByName) */

ULONG64 size;
if (SUCCEEDED(spType->GetSize(&size)))
{
    // size is equivalent to sizeof( <type> )
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
