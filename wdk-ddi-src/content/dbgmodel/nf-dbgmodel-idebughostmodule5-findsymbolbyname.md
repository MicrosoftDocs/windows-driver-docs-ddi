---
UID: NF:dbgmodel.IDebugHostModule5.FindSymbolByName
tech.root: debugger
title: IDebugHostModule5::FindSymbolByName
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule5::FindSymbolByName method, when called on a module, retrieves a global symbol by name from within the module.
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
 - IDebugHostModule5::FindSymbolByName
f1_keywords:
 - IDebugHostModule5::FindSymbolByName
 - dbgmodel/IDebugHostModule5::FindSymbolByName
dev_langs:
 - c++
helpviewer_keywords:
 - FindSymbolByName
---

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
ComPtr<IDebugHostModule5> spModule; /* get a module (see FindModuleByName) */

// Find the symbol for g_someGlobal;
ComPtr<IDebugHostSymbol> spSymbol;
if (SUCCEEDED(spModule->FindSymbolByName(L"g_someGlobal", &spSymbol)))
{
    // spSymbol contains the symbol for g_someGlobal.  It may be any kind of symbol.
}
```

## -see-also

[IDebugHostModule5 interface](nn-dbgmodel-idebughostmodule5.md)