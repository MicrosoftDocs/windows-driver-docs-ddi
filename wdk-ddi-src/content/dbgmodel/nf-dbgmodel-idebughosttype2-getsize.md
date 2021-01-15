---
UID: NF:dbgmodel.IDebugHostType2.GetSize
title: IDebugHostType2::GetSize (dbgmodel.h)
description: The GetSize method returns the size of the type (as if one had done sizeof(type) in C++).
ms.date: 10/04/2018
keywords: ["IDebugHostType2::GetSize"]
ms.keywords: IDebugHostType2::GetSize, GetSize, IDebugHostType2.GetSize, IDebugHostType2::GetSize, IDebugHostType2.GetSize
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
ms.custom: RS5
f1_keywords:
 - IDebugHostType2::GetSize
 - dbgmodel/IDebugHostType2::GetSize
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetSize
---

# IDebugHostType2::GetSize


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
ComPtr<IDebugHostType2> spType; /* get a type (see FindTypeByName) */

ULONG64 size;
if (SUCCEEDED(spType->GetSize(&size)))
{
    // size is equivalent to sizeof( <type> )
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

