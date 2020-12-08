---
UID: NF:dbgmodel.IDebugHostType2.GetPointerKind
title: IDebugHostType2::GetPointerKind (dbgmodel.h)
description: For types which are pointers, the GetPointerKind method returns the kind of pointer.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetPointerKind"]
ms.keywords: IDebugHostType2::GetPointerKind, GetPointerKind, IDebugHostType2.GetPointerKind, IDebugHostType2::GetPointerKind, IDebugHostType2.GetPointerKind
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
 - IDebugHostType2::GetPointerKind
 - dbgmodel/IDebugHostType2::GetPointerKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetPointerKind
---

# IDebugHostType2::GetPointerKind


## -description

For types which are pointers, the GetPointerKind method returns the kind of pointer. This is defined by the PointerKind enumeration and is one of the following values: 

Enumerant |	Meaning
|----------|---------|
PointerStandard	| Indicates a standard C/C++ pointer -- a *
PointerReference |	Indicates a C/C++ reference (whether const or not) -- a &
PointerRValueReference	| Indicates a C/C++ rvalue reference (whether const or not) -- a &&
PointerCXHat | Indicates a C++/CX hat managed pointer (whether const or not) -- a ^

## -parameters

### -param pointerKind

The kind of pointer will be returned here (as a value from the PointerKind enumeration.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for something that's a pointer 
                                  or reference (see FindTypeByName) */

PointerKind pk;
if (SUCCEEDED(spType->GetPointerKind(&pk)))
{
    // pk indicates the kind of pointer:
    //      PointerStandard (it's a '*')
    //      PointerReference (it's a '&')
    //      etc...
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

