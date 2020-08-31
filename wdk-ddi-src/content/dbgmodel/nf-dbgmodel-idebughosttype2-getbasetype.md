---
UID: NF:dbgmodel.IDebugHostType2.GetBaseType
title: IDebugHostType2::GetBaseType (dbgmodel.h)
description: If the type is a derivative of another single type (e.g. as MyStruct * is derived from MyStruct'), the GetBaseType method returns the base type of the derivation.
ms.assetid: 8d74a4b7-78d4-42e6-8435-dd0993f7fbb3
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetBaseType"]
ms.keywords: IDebugHostType2::GetBaseType, GetBaseType, IDebugHostType2.GetBaseType, IDebugHostType2::GetBaseType, IDebugHostType2.GetBaseType
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
 - IDebugHostType2::GetBaseType
 - dbgmodel/IDebugHostType2::GetBaseType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetBaseType
---

# IDebugHostType2::GetBaseType


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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

