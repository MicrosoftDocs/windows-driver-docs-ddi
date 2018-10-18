---
UID: NF:dbgmodel.IDebugHostData.GetContext
title: IDebugHostData::GetContext
author: windows-driver-content
description: The GetContext method returns the context where the symbol is valid. 
ms.assetid: bd2056cb-5ae8-4ef8-aab2-b1e2241cde78
ms.date: 09/12/2018 
ms.topic: method
ms.keywords: IDebugHostData::GetContext, GetContext, IDebugHostData.GetContext, IDebugHostData::GetContext, IDebugHostData.GetContext
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
-	IDebugHostData.GetContext
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostData::GetContext


## -description

The GetContext method returns the context where the symbol is valid. While this will represent things such as the debug target and process/address space in which the symbol exists, it may not be as specific as a context retrieved from other means (e.g.: from an IModelObject). 

## -parameters

### -param context
The host context in which the symbol is located will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostSymbol> spSymbol; /* get a symbol */

ComPtr<IDebugHostContext> spContext;
if (SUCCEEDED(spSymbol->GetContext(&spContext)))
{
    // spContext will contain the context that the symbol is within 
    // (e.g.: session, process)
}
```


## -see-also
[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)
