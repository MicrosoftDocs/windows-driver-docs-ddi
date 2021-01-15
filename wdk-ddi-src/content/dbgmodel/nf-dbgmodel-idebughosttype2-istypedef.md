---
UID: NF:dbgmodel.IDebugHostType2.IsTypedef
title: IDebugHostType2::IsTypedef (dbgmodel.h)
description: The IsTypedef method is the only method capable of seeing whether a type is a typedef.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::IsTypedef"]
ms.keywords: IDebugHostType2::IsTypedef, IsTypedef, IDebugHostType2.IsTypedef, IDebugHostType2::IsTypedef, IDebugHostType2.IsTypedef
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
 - IDebugHostType2::IsTypedef
 - dbgmodel/IDebugHostType2::IsTypedef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::IsTypedef
---

# IDebugHostType2::IsTypedef


## -description

The IsTypedef method is the only method capable of seeing whether a type is a typedef. The GetTypeKind method will behave as if called on the underlying type.

## -parameters

### -param isTypedef

Will return true if the type symbol is a typedef and false if it is not.

## -returns

This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a typedef (only FindTypeByName 
                                  since the compiler usually only emits base types 
                                  in the symbols for data) */

ComPtr<IDebugHostType2> spType2;
if (SUCCEEDED(spType.As(&spType2)))
{
    bool isTypeDef;
    if (SUCCEEDED(spType2->IsTypedef(&isTypeDef)))
    {
        // isTypeDef indicates whether the type is a typedef.
    }
}
```


Any type which is a typedef will behave as if the type is the final type underlying the typedef. This means that methods such as GetTypeKind will not indicate that the type is a typedef. Likewise, GetBaseType will not return the type the definition refers to. They will instead indicate behave as if they were called on the final definition underlying the typedef. As an example: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

An [IDebugHostType](nn-dbgmodel-idebughosttype.md) for 'either PMYSTRUCT or PTRMYSTRUCT will report the following information: 

- The GetTypeKind method will return TypePointer. The final underlying type MYSTRUCT * is indeed a pointer.

- The 'GetBaseType method will return a type for MYSTRUCT. The underlying type of MYSTRUCT * is MYSTRUCT.

The only difference here is how the typedef specific methods on [IDebugHostType2](nn-dbgmodel-idebughosttype2.md) behave. Those methods are: 

```cpp
STDMETHOD(IsTypedef)(_Out_ bool* isTypedef) PURE;

STDMETHOD(GetTypedefBaseType)(_Out_ IDebugHostType2** baseType) PURE;

STDMETHOD(GetTypedefFinalBaseType)(_Out_ IDebugHostType2** finalBaseType) PURE;
```
In this example: 

- The IsTypedef method will return true for both PMYSTRUCT and PTRMYSTRUCT
- The GetTypedefBaseType method will return MYSTRUCT * for PMYSTRUCT and PMYSTRUCT for PTRMYSTRUCT
- The GetTypedefFinalBaseType method will return MYSTRUCT * for both types

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

