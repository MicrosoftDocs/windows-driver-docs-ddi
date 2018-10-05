---
UID: NF:dbgmodel.IDebugHostModule2.FindSymbolByName
title: IDebugHostModule2::FindSymbolByName
author: windows-driver-content
description: The FindSymbolByName method will find a single global symbol of the given name within the module.
ms.assetid: 74ce0a4b-7079-469d-b769-e47eae4123ed
ms.author: windowsdriverdev
ms.date: 09/18/2018 
ms.topic: method
ms.keywords: IDebugHostModule2::FindSymbolByName, FindSymbolByName, IDebugHostModule2.FindSymbolByName, IDebugHostModule2::FindSymbolByName, IDebugHostModule2.FindSymbolByName
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
-	IDebugHostModule2.FindSymbolByName
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostModule2::FindSymbolByName


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
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
