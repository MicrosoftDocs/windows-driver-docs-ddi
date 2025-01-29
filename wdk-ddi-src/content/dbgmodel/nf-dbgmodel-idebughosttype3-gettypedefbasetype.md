---
UID: NF:dbgmodel.IDebugHostType3.GetTypedefBaseType
tech.root: debugger
title: IDebugHostType3::GetTypedefBaseType
ms.date: 01/26/2025
targetos: Windows
description: The GetTypedefBaseType method will return what the immediate definition of the typedef.
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
 - IDebugHostType3::GetTypedefBaseType
f1_keywords:
 - IDebugHostType3::GetTypedefBaseType
 - dbgmodel/IDebugHostType3::GetTypedefBaseType
dev_langs:
 - c++
helpviewer_keywords:
 - GetTypedefBaseType
---

## -description

The GetTypedefBaseType method will return what the immediate definition of the typedef. In this examples: 

```cpp
typedef MYSTRUCT *PMYSTRUCT;
typedef PMYSTRUCT PTRMYSTRUCT;
```

this method will return MYSTRUCT * for PMYSTRUCT and PMYSTRUCT for PTRMYSTRUCT. For more information, see [IDebugHostType3::IsTypedef](nf-dbgmodel-idebughosttype3-istypedef.md).

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)