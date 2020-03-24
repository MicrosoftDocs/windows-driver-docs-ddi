---
UID: NE:dbgmodel.SymbolSearchOptions
title: SymbolSearchOptions (dbgmodel.h)
description: Symbols search options.
ms.assetid: b6a5df9d-42b8-4d3b-b9a7-84b89d8826be
ms.date: 07/16/2018
keywords: ["SymbolSearchOptions enumeration"]
f1_keywords:
 - "dbgmodel/SymbolSearchOptions"
ms.keywords: SymbolSearchOptions, , 
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- SymbolSearchOptions
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# SymbolSearchOptions enumeration

## -description

Symbols search options.

## -enum-fields

### -field SymbolSearchNone 
SymbolSearchNone: No options set

SymbolSearchNone = 0x00000000,


### -field SymbolSearchCompletion 
SymbolSearchCompletion: Search for symbols starting with the specified name rather than symbols of the exact specified name.

SymbolSearchCompletion = 0x00000001

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
