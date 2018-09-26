---
UID: NF:dbgmodel.IDebugHostType2.GetFunctionReturnType
title: IDebugHostType2::GetFunctionReturnType
author: windows-driver-content
description: TBD
ms.assetid: 5372dfd6-015f-41d8-ba2a-ee6f283ebab7
ms.author: windowsdriverdev
ms.date: 09/20/2018 
ms.topic: method
ms.keywords: IDebugHostType2::GetFunctionReturnType, GetFunctionReturnType, IDebugHostType2.GetFunctionReturnType, IDebugHostType2::GetFunctionReturnType, IDebugHostType2.GetFunctionReturnType
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
-	IDebugHostType2.GetFunctionReturnType
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostType2::GetFunctionReturnType


## -description

The GetFunctionReturnType method returns the return type of the function. 

## -parameters

### -param returnType
A type symbol indicating the return type of the function is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type for a function (see FindTypeByName) */

ComPtr<IDebugHostType> spReturnType;
if (SUCCEEDED(spType->GetFunctionReturnType(&spReturnType)))
{
    // spReturnType is the type symbol for the return type of the function.
}
```


## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
