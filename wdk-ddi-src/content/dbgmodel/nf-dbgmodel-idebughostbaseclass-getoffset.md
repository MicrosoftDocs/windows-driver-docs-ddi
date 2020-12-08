---
UID: NF:dbgmodel.IDebugHostBaseClass.GetOffset
title: IDebugHostBaseClass::GetOffset (dbgmodel.h)
description: The GetOffset method returns the offset of the base class from the base address of the derived class.
ms.date: 08/14/2018
keywords: ["IDebugHostBaseClass::GetOffset"]
ms.keywords: IDebugHostBaseClass::GetOffset, GetOffset, IDebugHostBaseClass.GetOffset, IDebugHostBaseClass::GetOffset, IDebugHostBaseClass.GetOffset
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
 - IDebugHostBaseClass::GetOffset
 - dbgmodel/IDebugHostBaseClass::GetOffset
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass.GetOffset
---

# IDebugHostBaseClass::GetOffset


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
ComPtr<IDebugHostBaseClass> spBaseClass; /* get a base class symbol (see
                                            EnumerateChildren) */

ULONG64 offset;
if (SUCCEEDED(spBaseClass->GetOffset(&offset)))
{
    // offset indicates the position of the base class relative to the 
    // start of its parent class.
}
```

## -see-also

[IDebugHostBaseClass interface](nn-dbgmodel-idebughostbaseclass.md)

