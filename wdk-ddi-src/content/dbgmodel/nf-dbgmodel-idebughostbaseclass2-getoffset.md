---
UID: NF:dbgmodel.IDebugHostBaseClass2.GetOffset
tech.root: debugger
title: IDebugHostBaseClass2::GetOffset
ms.date: 12/16/2024
targetos: Windows
description: The GetOffset method returns the offset of the base class from the base address of the derived class.
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
 - IDebugHostBaseClass2::GetOffset
f1_keywords:
 - IDebugHostBaseClass2::GetOffset
 - dbgmodel/IDebugHostBaseClass2::GetOffset
dev_langs:
 - c++
helpviewer_keywords:
 - GetOffset
---

## -description

The GetOffset method returns the offset of the base class from the base address of the derived class. Such offset may be zero or may be a positive unsigned 64-bit value.

## -parameters

### -param offset

The offset of the base class from the base address of the derived class is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostBaseClass2> spBaseClass; /* get a base class symbol (see
                                            EnumerateChildren) */

ULONG64 offset;
if (SUCCEEDED(spBaseClass->GetOffset(&offset)))
{
    // offset indicates the position of the base class relative to the 
    // start of its parent class.
}
```

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)