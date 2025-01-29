---
UID: NF:dbgmodel.IDebugHostType3.IsTypedef
tech.root: debugger
title: IDebugHostType3::IsTypedef
ms.date: 01/24/2025
targetos: Windows
description: The IsTypedef method is the only method capable of seeing whether a type is a typedef.
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
 - IDebugHostType3::IsTypedef
f1_keywords:
 - IDebugHostType3::IsTypedef
 - dbgmodel/IDebugHostType3::IsTypedef
dev_langs:
 - c++
helpviewer_keywords:
 - IsTypedef
---

## -description

The IsTypedef method is the only method capable of seeing whether a type is a typedef. The [GetTypeKind method](nf-dbgmodel-idebughosttype3-gettypekind.md) will behave as if called on the underlying type.

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

Any type which is a typedef will behave as if the type is the final type underlying the typedef. This means that methods such as GetTypeKind will not indicate that the type is a typedef. Likewise, the [GetBaseType method](nf-dbgmodel-idebughosttype3-getbasetype.md) will not return the type the definition refers to. They will instead indicate behave as if they were called on the final definition underlying the typedef. As an example: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

An [IDebugHostType](nn-dbgmodel-idebughosttype.md) for 'either PMYSTRUCT or PTRMYSTRUCT will report the following information: 

- The GetTypeKind method will return TypePointer. The final underlying type MYSTRUCT * is indeed a pointer.

- The GetBaseType method will return a type for MYSTRUCT. The underlying type of MYSTRUCT * is MYSTRUCT.

The only difference here is how the typedef specific methods on [IDebugHostType3](nn-dbgmodel-idebughosttype3.md) behave. Those methods are: 

```cpp
STDMETHOD(IsTypedef)(_Out_ bool* isTypedef) PURE;

STDMETHOD(GetTypedefBaseType)(_Out_ IDebugHostType3** baseType) PURE;

STDMETHOD(GetTypedefFinalBaseType)(_Out_ IDebugHostType3** finalBaseType) PURE;
```

In this example: 

- The IsTypedef method will return true for both PMYSTRUCT and PTRMYSTRUCT
- The GetTypedefBaseType method will return MYSTRUCT * for PMYSTRUCT and PMYSTRUCT for PTRMYSTRUCT
- The GetTypedefFinalBaseType method will return MYSTRUCT * for both types

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
