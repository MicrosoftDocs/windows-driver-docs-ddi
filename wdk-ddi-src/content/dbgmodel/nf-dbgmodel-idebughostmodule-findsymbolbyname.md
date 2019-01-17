---
UID: NF:dbgmodel.IDebugHostModule.FindSymbolByName
title: IDebugHostModule::FindSymbolByName
description: The FindSymbolByName method will find a single global symbol of the given name within the module. 
ms.assetid: 05e3a31b-cab3-43fe-b764-1610ba5ca981
ms.date: 09/18/2018
ms.topic: method
ms.keywords: IDebugHostModule::FindSymbolByName, FindSymbolByName, IDebugHostModule.FindSymbolByName, IDebugHostModule::FindSymbolByName, IDebugHostModule.FindSymbolByName
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
-	IDebugHostModule.FindSymbolByName
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule::FindSymbolByName


## -description

The FindSymbolByName method will find a single global symbol of the given name within the module. If there is not a single symbol matching the given name, an error will be returned by this method. Note that this method will prefer returning a private symbol over a symbol in the publics table. 

## -parameters

### -param symbolName
The name of the symbol to locate within the symbolic information for the module.

### -param symbol
The found symbol will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule> spModule; /* get a module (see FindModuleByName) */

// Find the symbol for g_someGlobal;
ComPtr<IDebugHostSymbol> spSymbol;
if (SUCCEEDED(spModule->FindSymbolByName(L"g_someGlobal", &spSymbol)))
{
    // spSymbol contains the symbol for g_someGlobal.  It may be any kind of symbol.
}
```

## -see-also

[IDebugHostModule interface](nn-dbgmodel-idebughostmodule.md)
