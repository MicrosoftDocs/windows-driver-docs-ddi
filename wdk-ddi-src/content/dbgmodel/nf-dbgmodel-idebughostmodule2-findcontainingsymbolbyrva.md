---
UID: NF:dbgmodel.IDebugHostModule2.FindContainingSymbolByRVA
title: IDebugHostModule2::FindContainingSymbolByRVA (dbgmodel.h)
description: The FindSymbolByRVA method will find a single matching symbol at the given relative virtual address within the module. 
ms.assetid: 1c0fb339-0086-4ab4-987f-d6fc673c37cf
ms.date: 09/18/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostModule2.FindContainingSymbolByRVA"
ms.keywords: IDebugHostModule2::FindContainingSymbolByRVA, FindContainingSymbolByRVA, IDebugHostModule2.FindContainingSymbolByRVA, IDebugHostModule2::FindContainingSymbolByRVA, IDebugHostModule2.FindContainingSymbolByRVA
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostModule2.FindContainingSymbolByRVA
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule2::FindContainingSymbolByRVA


## -description
The FindSymbolByRVA method will find a single matching symbol at the given relative virtual address within the module. If there is not a single symbol at the supplied RVA (e.g.: there are multiple matches), an error will be returned by this method. Note that this method will prefer returning a private symbol over a symbol in the publics table. 

## -parameters

### -param rva
The relative virtual address (offset) within the module for which to locate a matching symbol in the symbolic information for the module.

### -param symbol
The found symbol will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule> spModule;

// Find the symbol which is at 0x100000 within the module
ComPtr<IDebugHostSymbol> spSymbol;
if (SUCCEEDED(spModule->FindSymbolByRVA(0x100000, &spSymbol)))
{
    // spSymbol contains the symbol which is at RVA 0x100000 within the
    // module.  Note that it may be any kind of symbol
}
```

## -see-also
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
