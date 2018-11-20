---
UID: NF:dbgmodel.IDebugHostExtensibility.DestroyFunctionAlias
title: IDebugHostExtensibility::DestroyFunctionAlias
author: windows-driver-content
description: The DestroyFunctionAlias method undoes a prior call to the CreateFunctionAlias method. 
ms.assetid: 804810be-bb3a-41e8-b239-919625eb6f0c
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDebugHostExtensibility::DestroyFunctionAlias, DestroyFunctionAlias, IDebugHostExtensibility.DestroyFunctionAlias, IDebugHostExtensibility::DestroyFunctionAlias, IDebugHostExtensibility.DestroyFunctionAlias
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
-	IDebugHostExtensibility.DestroyFunctionAlias
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostExtensibility::DestroyFunctionAlias


## -description

The DestroyFunctionAlias method undoes a prior call to the CreateFunctionAlias method. The function will no longer be available under the quick alias name. 

## -parameters

### -param aliasName
The (quick) name of the alias being destroyed.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks
**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the debug host */

ComPtr<IDebugHostExtensibility> spHostExtensibility;
if (SUCCEEDED(spHost.As(&spHostExtensibility)))
{
    if (SUCCEEDED(spHostExtensibility->DestroyFunctionAlias(L"sumit")))
    {
        // The alias sumit is now gone.
    }
}
```

## -see-also

[IDebugHostExtensibility interface](nn-dbgmodel-idebughostextensibility.md)
