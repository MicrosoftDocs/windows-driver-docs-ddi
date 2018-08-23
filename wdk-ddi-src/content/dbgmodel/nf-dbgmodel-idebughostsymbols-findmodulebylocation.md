---
UID: NF:dbgmodel.IDebugHostSymbols.FindModuleByLocation
title: IDebugHostSymbols::FindModuleByLocation
author: windows-driver-content
description: TBD
ms.assetid: 255a026b-6114-44ca-8cdf-9543f1c0cd77
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::FindModuleByLocation, FindModuleByLocation, IDebugHostSymbols.FindModuleByLocation, IDebugHostSymbols::FindModuleByLocation, IDebugHostSymbols.FindModuleByLocation
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
-	IDebugHostSymbols.FindModuleByLocation
product: Windows
targetos: Windows


---

# IDebugHostSymbols::FindModuleByLocation


## -description

The FindModuleByName method will look through the given host context and locate a module which has the specified name and return an interface to it. It is legal to search for the module by name with or without the file extension. 

## -parameters

### -param context
This host context will be searched for a loaded module matching the given name.

### -param moduleLocation
The name of the module to search for. The name may be specified with or without a file extension.

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
    // Find the "notepad.exe" module in the current UI context (process) 
    // of the debug host:
    ComPtr<IDebugHostModule> spModule;
    if (SUCCEEDED(spSym->FindModuleByName(USE_CURRENT_HOST_CONTEXT, 
                                          L"notepad.exe", 
                                          &spModule)))
    {
        // spModule is the module "notepad.exe"
    }
}
```

## -see-also
[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
