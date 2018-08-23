---
UID: NF:dbgmodel.IDebugHostSymbols.FindModuleByName
title: IDebugHostSymbols::FindModuleByName
author: windows-driver-content
description: TBD
ms.assetid: 7ff45667-8b89-46a9-8167-d90976dae181
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::FindModuleByName, FindModuleByName, IDebugHostSymbols.FindModuleByName, IDebugHostSymbols::FindModuleByName, IDebugHostSymbols.FindModuleByName
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
-	IDebugHostSymbols.FindModuleByName
product: Windows
targetos: Windows


---

# IDebugHostSymbols::FindModuleByName


## -description

The FindModuleByLocation method will look through the given host context and determine what module contains the address given by the specified location. It will then return an interface to such module. 

## -parameters

### -param context
This host context will be searched for a loaded module containing the address given by the moduleLocation argument.

### -param moduleName
The module in the given context which contains the address specified by this argument will be returned (or the method will fail).

### -param module
If the module is found, an interface to the module will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Find the module which contains the address 0x7f638000 in the current 
    // UI context (process) of the debug host
    ComPtr<IDebugHostModule> spModule;
    if (SUCCEEDED(sySym->FindModuleByLocation(USE_CURRENT_HOST_CONTEXT, 
                                              0x7f638000, 
                                              &spModule)))
    {
        // spModule is the module which contains the VA 0x7f638000
    }
}
```

## -see-also
[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
