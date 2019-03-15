---
UID: NF:dbgmodel.IDebugHostType2.GetTypedefFinalBaseType
title: IDebugHostType2::GetTypedefFinalBaseType (dbgmodel.h)
description: The GetTypedefFinalBaseType method will return the final type that the typedef is a definition for. 
ms.assetid: 20ba8d09-b4a6-4ede-aac3-8d95a5d079b2
ms.date: 09/20/2018
ms.topic: method
ms.keywords: IDebugHostType2::GetTypedefFinalBaseType, GetTypedefFinalBaseType, IDebugHostType2.GetTypedefFinalBaseType, IDebugHostType2::GetTypedefFinalBaseType, IDebugHostType2.GetTypedefFinalBaseType
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
- IDebugHostType2.GetTypedefFinalBaseType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType2::GetTypedefFinalBaseType


## -description

The GetTypedefFinalBaseType method will return the final type that the typedef is a definition for. If the typedef is a definition of another typedef, this will continue to follow the definition chain until it reaches a type which is not a typedef and that type will be returned. In this example: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

this method will return MYSTRUCT * when called on either PMYSTRUCT or PTRMYSTRUCT. For more information, see [IDebugHostType2::IsTypedef](nf-dbgmodel-idebughosttype2-istypedef.md). 

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

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
