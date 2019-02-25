---
UID: NF:dbgmodel.IDebugHostType2.GetTypedefBaseType
title: IDebugHostType2::GetTypedefBaseType (dbgmodel.h)
description: The GetTypedefBaseType method will return what the immediate definition of the typedef.
ms.assetid: e0a0a7fb-6049-4e08-9e8b-c10629e4a5e9
ms.date: 09/20/2018
ms.topic: method
ms.keywords: IDebugHostType2::GetTypedefBaseType, GetTypedefBaseType, IDebugHostType2.GetTypedefBaseType, IDebugHostType2::GetTypedefBaseType, IDebugHostType2.GetTypedefBaseType
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
-	IDebugHostType2.GetTypedefBaseType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType2::GetTypedefBaseType


## -description

The GetTypedefBaseType method will return what the immediate definition of the typedef. In this examples: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

this method will return MYSTRUCT * for PMYSTRUCT and PMYSTRUCT for PTRMYSTRUCT. For more information, see [IDebugHostType2::IsTypedef](nf-dbgmodel-idebughosttype2-istypedef.md). 


## -parameters

### -param baseType
Returns the immediate (first level) type that the typedef is a definition for. If the typedef is a definition of another typedef, this will return that typedef and not the final unwind of the definition chain.


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
    ComPtr<IDebugHostType> spBaseType;
    if (SUCCEEDED(spType2->GetTypedefBaseType(&spBaseType)))
    {
        // Returns the immediate base type of the typedef.  This may 
        // be another typedef.
    }
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
