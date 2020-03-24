---
UID: NF:dbgmodel.IDebugHostType.GetBaseType
title: IDebugHostType::GetBaseType (dbgmodel.h)
description: If the type is a derivative of another single type (e.g. as MyStruct * is derived from MyStruct'), the GetBaseType method returns the base type of the derivation. 
ms.assetid: b3dab0db-f36f-49b0-80e7-0848fc49b13c
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetBaseType"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetBaseType"
ms.keywords: IDebugHostType::GetBaseType, GetBaseType, IDebugHostType.GetBaseType, IDebugHostType::GetBaseType, IDebugHostType.GetBaseType
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
- IDebugHostType.GetBaseType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetBaseType


## -description

If the type is a derivative of another single type (e.g.: as MyStruct * is derived from MyStruct'), the GetBaseType method returns the base type of the derivation. For pointers, this returns the type pointed to. For arrays, this returns what the array is an array of. If the type is not such a derivative type, an error is returned. 

Note that this method has nothing to do with C++ (or other linguistic) base classes. Such are symbols ([IDebugHostBaseClass](nn-dbgmodel-idebughostbaseclass.md)) which can be enumerated from the derived class via a call to the EnumerateChildren method. 

## -parameters

### -param baseType
The type that this type is derived from is returned here. This is the type pointed to, the type an array contains, etc...


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type (see FindTypeByName) */

ComPtr<IDebugHostType> spBaseType;
if (SUCCEEDED(spType->GetBaseType(&spBaseType)))
{
    // spBaseType is the base type.
    //     For a pointer, this is the type pointed to
    //     For an array, this is the type which the array contains
    //     etc...
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
