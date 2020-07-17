---
UID: NF:dbgmodel.IDebugHostModule2.FindSymbolByRVA
title: IDebugHostModule2::FindSymbolByRVA (dbgmodel.h)
description: The FindSymbolByRVA method will find a single matching symbol at the given relative virtual address within the module. 
ms.assetid: 55e87b33-8392-4391-970c-690d5a1934e9
ms.date: 10/04/2018
keywords: ["IDebugHostModule2::FindSymbolByRVA"]
f1_keywords:
 - "dbgmodel/IDebugHostModule2.FindSymbolByRVA"
 - "IDebugHostModule2.FindSymbolByRVA"
ms.keywords: IDebugHostModule2::FindSymbolByRVA, FindSymbolByRVA, IDebugHostModule2.FindSymbolByRVA, IDebugHostModule2::FindSymbolByRVA, IDebugHostModule2.FindSymbolByRVA
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
- IDebugHostModule2.FindSymbolByRVA
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule2::FindSymbolByRVA


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

## -see-also
[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)
