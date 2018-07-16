---
UID: NE:dbgmodel.TypeKind
title: TypeKind
author: windows-driver-content
description: 
ms.assetid: 82d1212c-5997-4c81-aa2f-3b390c0b2aaa
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: TypeKind, , 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	TypeKind
product: Windows
targetos: Windows
---

# TypeKind enumeration

## -description

Defines the kind of a type.

## -enum-fields

### -field TypeUDT
A user defined type (a struct, class, union, etc...). A model object which has a native type whose kind is TypeUDT has a canonical representation of ObjectTargetObject where the type is always kept inside the corresponding IModelObject.


### -field TypePointer 
A pointer. A model object which has a native type whose kind is TypePointer has a canonical representation of ObjectIntrinsic where the pointer's value is zero extended to VT_UI8 and kept as intrinsic data in this 64-bit form. Any type symbol of TypePointer has a base type (as returned by the GetBaseType method) of the type that the pointer points to.


### -field TypeMemberPointer 
A pointer to class member. A model object which has a native type whose kind is TypeMemberPointer has a canonical representation which is intrinsic (the value being the same as the pointer value). The exact meaning of this value is compiler/debug host specific.


### -field TypeArray 
An array. A model object which has a native type whose kind is TypeArray has a canonical representation of ObjectTargetObject. The base address of the array is the object's location (retrieved via the GetLocation method) and the type of the array is always kept. Any type symbol of TypeArray has a base type (as returned by the GetBaseType method) of the type that the array is an array of.


### -field TypeFunction 
A function.


### -field TypeTypedef 
A typedef. A model object which has a native type whose kind would otherwise be TypeTypedef has a canonical representation identical to the canonical representation of the final type underlying the typedef. This appears completely transparent to the end user of the object and the type information unless the explicit typedef methods of IDebugHostType2 are utilized to query typedef information or there is an explicit data model registered against the typedef. Note that the GetTypeKind method will never return TypeTypedef. Every method will return what the final type underlying the typedef would return. There are typedef specific methods on IDebugHostType2 which can be used to get the typedef specific information.


### -field TypeEnum 
An enum. A model object which has a native type whose kind is TypeEnum has a canonical representation of ObjectIntrinsic where the value and type of the intrinsic is identical to the enum value. 


### -field TypeIntrinsic 
An intrinsic (base type). A model object which has a native type whose kind is TypeIntrinsic has a canonical representation of ObjectIntrinsic. The type information may or may not be kept -- particularly if the underlying type is fully described by the variant data type (VT_*) of the intrinsic data stored in the IModelObject

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)