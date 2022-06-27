---
UID: NF:dbgmodel.SymbolSearchInfo.SymbolSearchInfo
title: SymbolSearchInfo ULONG function (dbgmodel.h)
description: The SymbolSearchInfo function (dbgmodel.h) constructs a SymbolSearchInfo, a search record passed to EnumerateChildrenEx to restrict symbol searches. Does not take any parameters.
ms.date: 05/25/2022
keywords: ["SymbolSearchInfo function"]
ms.keywords: SymbolSearchInfo
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - SymbolSearchInfo::SymbolSearchInfo
 - dbgmodel/SymbolSearchInfo::SymbolSearchInfo
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - SymbolSearchInfo::SymbolSearchInfo
---

# SymbolSearchInfo ULONG function (dbgmodel.h)


## -description

The search record passed to EnumerateChildrenEx in order to restrict symbol searches. This form of the function does not take any parameters.

A given kind of symbol (as indicated by the SymbolKind enumeration) searched may have its own derived type.

## -parameters

### -param derivedSize

The derived size.

## -returns

This function is a constructor and does not return a value.

## -remarks

## -see-also

[dbgmodel.h header](./index.md)

