---
UID: NE:dbgmodel.SymbolSearchOptions
title: SymbolSearchOptions (dbgmodel.h)
description: Symbols search options.
ms.date: 08/10/2023
keywords: ["SymbolSearchOptions enumeration"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - SymbolSearchOptions
 - dbgmodel/SymbolSearchOptions
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - SymbolSearchOptions
---

# SymbolSearchOptions enumeration

## -description

Symbols search options.

## -enum-fields

### -field SymbolSearchNone

No options set

SymbolSearchNone = 0x00000000,

### -field SymbolSearchCompletion

Search for symbols starting with the specified name rather than symbols of the exact specified name.

SymbolSearchCompletion = 0x00000001

### -field SymbolSearchCaseInsensitive

Search for symbols using case-insensitive rules.

SymbolSearchCaseInsensitive = 0x00000002

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
