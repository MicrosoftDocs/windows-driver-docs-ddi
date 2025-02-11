---
UID: NF:dbgmodel.IDebugHostType3.GetPointerKind
tech.root: debugger
title: IDebugHostType3::GetPointerKind
ms.date: 01/26/2025
targetos: Windows
description: The GetPointerKind method, when called on a type for a pointer, gets the kind of pointer specified by the PointerKind enumeration.
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
 - IDebugHostType3::GetPointerKind
f1_keywords:
 - IDebugHostType3::GetPointerKind
 - dbgmodel/IDebugHostType3::GetPointerKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetPointerKind
---

## -description

For types which are pointers, the GetPointerKind method returns the kind of pointer. This is defined by the PointerKind enumeration and is one of the following values: 

|Enumerant |	Meaning|
|----------|---------|
|PointerStandard	| Indicates a standard C/C++ pointer -- a *|
|PointerReference |	Indicates a C/C++ reference (whether const or not) -- a &|
|PointerRValueReference	| Indicates a C/C++ rvalue reference (whether const or not) -- a &&|
|PointerCXHat | Indicates a C++/CX hat managed pointer (whether const or not) -- a ^|

## -parameters

### -param pointerKind

The kind of pointer will be returned here as a value from the PointerKind enumeration.

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
