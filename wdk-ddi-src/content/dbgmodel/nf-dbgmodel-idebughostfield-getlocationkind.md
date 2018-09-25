---
UID: NF:dbgmodel.IDebugHostField.GetLocationKind
title: IDebugHostField::GetLocationKind
author: windows-driver-content
description: TBD
ms.assetid: 34e162cb-39d8-4d70-88f6-99fa71da87d5
ms.author: windowsdriverdev
ms.date: 09/12/2018 
ms.topic: method
ms.keywords: IDebugHostField::GetLocationKind, GetLocationKind, IDebugHostField.GetLocationKind, IDebugHostField::GetLocationKind, IDebugHostField.GetLocationKind
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostField.GetLocationKind
product: Windows
targetos: Windows


---

# IDebugHostField::GetLocationKind


## -description

The GetLocationKind method returns what kind of location the symbol is at according to the LocationKind enumeration. Such enumeration can be one of the following values: 

Enumerant	| Meaning
|-----------|----------|
LocationMember 	| The field is a regular data member of a class, structure, union, or other type construct. It has an offset which is relative to base address of the containing type construct. Such base address is typically represented by the this pointer. The offset of the field can be retrieved via the GetOffset method. The GetLocation and GetValue methods will fail for a field which is LocationMember.
LocationStatic	| The field is static and has its own address. The GetLocation method will return the abstract location (e.g.: address) of the static field. The GetOffset and GetValue methods will fail for a field which is LocationStatic.
LocationConstant	| The field is a constant and has a value. The GetValue method will return the value of the constant. The GetOffset and GetLocation methods will fail for a field which is LocationConstant
LocationNone	| The field has no location. It may have been optimized out by the compiler or it may be a static field which is declared but never defined. Regardless of how such a field came to be, it has no physical presence or value. It is only in the symbols. All acquisition methods (GetOffset, GetLocation, and GetValue) will fail for a field which is LocationNone.


## -parameters

### -param locationKind
The kind of location for this field will be returned here as a value of the LocationKind enumeration.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostField> spField; /* get a field symbol */

LocationKind kind;
if (SUCCEEDED(spField->GetLocationKind(&kind)))
{
    // kind indicates the kind of location (e.g.: static, constant, member, etc...)
}
```


## -see-also

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)