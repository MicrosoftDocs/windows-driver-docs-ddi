---
UID: NF:dbgmodel.IDebugHostType3.GetTypedefFinalBaseType
tech.root: debugger
title: IDebugHostType3::GetTypedefFinalBaseType
ms.date: 01/26/2025
targetos: Windows
description: The GetTypedefFinalBaseType method will return the final type that the typedef is a definition for.
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
 - IDebugHostType3::GetTypedefFinalBaseType
f1_keywords:
 - IDebugHostType3::GetTypedefFinalBaseType
 - dbgmodel/IDebugHostType3::GetTypedefFinalBaseType
dev_langs:
 - c++
helpviewer_keywords:
 - GetTypedefFinalBaseType
---

## -description

The GetTypedefFinalBaseType method will return the final type that the typedef is a definition for. If the typedef is a definition of another typedef, this will continue to follow the definition chain until it reaches a type which is not a typedef and that type will be returned. In this example: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

this method will return MYSTRUCT * when called on either PMYSTRUCT or PTRMYSTRUCT. For more information, see [IDebugHostType3::IsTypedef](nf-dbgmodel-idebughosttype3-istypedef.md).

## -parameters

### -param finalBaseType

Returns the final type that the typedef is a definition for. If the typedef is a definition of another typedef, this will continue to follow the definition chain until it reaches a type which is not a typedef. Such type will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a typedef type (only FindTypeByName since 
                                  the compiler usually emits base types for data) */

ComPtr<IDebugHostType2> spType2;
if (SUCCEEDED(spType.As(&spType2)))
{
    ComPtr<IDebugHostType> spFinalBaseType;
    if (SUCCEEDED(spType2->GetTypedefFinalBaseType(&spFinalBaseType)))
    {
        // Returns the final base type of the typedef.  This will follow the 
        // typedef chain until it reaches a base type that is *NOT* a typedef.
    }
}
```

## -see-also

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)