---
UID: NF:dbgmodel.IDebugHostSymbol.GetSymbolKind
title: IDebugHostSymbol::GetSymbolKind (dbgmodel.h)
description: "The IDebugHostSymbol::GetSymbolKind method, when called on a symbol, gets the kind of symbol, such as field, base class, or type."
ms.date: 06/10/2019
keywords: ["IDebugHostSymbol::GetSymbolKind"]
ms.keywords: IDebugHostSymbol::GetSymbolKind, GetSymbolKind, IDebugHostSymbol.GetSymbolKind, IDebugHostSymbol::GetSymbolKind, IDebugHostSymbol.GetSymbolKind
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
 - IDebugHostSymbol::GetSymbolKind
 - dbgmodel/IDebugHostSymbol::GetSymbolKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbol::GetSymbolKind
---

# IDebugHostSymbol::GetSymbolKind


## -description

Gets the kind of symbol that this is (e.g.: a field, a base class, a type, etc...).

## -parameters

### -param kind

The kind of symbol (e.g.: a type, field, base class, etc…) will be returned here. For more information, see [SymbolKind Enumeration](ne-dbgmodel-symbolkind.md).

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostSymbol interface](nn-dbgmodel-idebughostsymbol.md)

