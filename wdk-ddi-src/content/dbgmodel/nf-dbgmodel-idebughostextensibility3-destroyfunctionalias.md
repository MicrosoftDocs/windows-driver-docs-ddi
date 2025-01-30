---
UID: NF:dbgmodel.IDebugHostExtensibility3.DestroyFunctionAlias
tech.root: debugger
title: IDebugHostExtensibility3::DestroyFunctionAlias
ms.date: 01/29/2025
targetos: Windows
description: The DestroyFunctionAlias method undoes a prior call to the CreateFunctionAlias method. The function will no longer be available under the quick alias name.
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
 - IDebugHostExtensibility3::DestroyFunctionAlias
f1_keywords:
 - IDebugHostExtensibility3::DestroyFunctionAlias
 - dbgmodel/IDebugHostExtensibility3::DestroyFunctionAlias
dev_langs:
 - c++
helpviewer_keywords:
 - DestroyFunctionAlias
---

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

[IDebugHostExtensibility3 interface](nn-dbgmodel-idebughostextensibility3.md)