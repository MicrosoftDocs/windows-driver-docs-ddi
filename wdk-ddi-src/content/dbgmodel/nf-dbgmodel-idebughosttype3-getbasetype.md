---
UID: NF:dbgmodel.IDebugHostType3.GetBaseType
tech.root: debugger
title: IDebugHostType3::GetBaseType
ms.date: 01/26/2025
targetos: Windows
description: The GetBaseType method, when called on a type, gets the base type. The base type is the target type for a pointer or element type for an array.
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
 - IDebugHostType3::GetBaseType
f1_keywords:
 - IDebugHostType3::GetBaseType
 - dbgmodel/IDebugHostType3::GetBaseType
dev_langs:
 - c++
helpviewer_keywords:
 - GetBaseType
---

## -description

If the type is a derivative of another single type (e.g.: as MyStruct * is derived from MyStruct'), the GetBaseType method returns the base type of the derivation. For pointers, this returns the type pointed to. For arrays, this returns what the array is an array of. If the type is not such a derivative type, an error is returned. 

Note that this method has nothing to do with C++ (or other linguistic) base classes. Such are symbols ([IDebugHostBaseClass](nn-dbgmodel-idebughostbaseclass.md)) which can be enumerated from the derived class via a call to the EnumerateChildren method.

## -parameters

### -param baseType

The type that this type is derived from is returned here. This is the type pointed to, the type an array contains, etc...

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)