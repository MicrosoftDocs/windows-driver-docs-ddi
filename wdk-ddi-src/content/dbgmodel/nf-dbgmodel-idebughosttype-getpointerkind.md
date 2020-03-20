---
UID: NF:dbgmodel.IDebugHostType.GetPointerKind
title: IDebugHostType::GetPointerKind (dbgmodel.h)
description: For types which are pointers, the GetPointerKind method returns the kind of pointer. 
ms.assetid: cd03e7b1-769d-4316-a8f3-06467173ca70
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetPointerKind"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetPointerKind"
ms.keywords: IDebugHostType::GetPointerKind, GetPointerKind, IDebugHostType.GetPointerKind, IDebugHostType::GetPointerKind, IDebugHostType.GetPointerKind
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
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostType.GetPointerKind
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetPointerKind


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

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
