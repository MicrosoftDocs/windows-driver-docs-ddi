---
UID: NF:dbgmodel.IDebugHostType3.GetSize
tech.root: debugger
title: IDebugHostType3::GetSize
ms.date: 01/26/2025
targetos: Windows
description: The GetSize method, when called on a type, gets the size of the type. This method is equivalent to sizeof(type) in C++.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType3::GetSize
f1_keywords:
 - IDebugHostType3::GetSize
 - dbgmodel/IDebugHostType3::GetSize
dev_langs:
 - c++
helpviewer_keywords:
 - GetSize
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)