---
UID: NF:dbgmodel.IDebugHostType2.GetSymbolKind
title: IDebugHostType2::GetSymbolKind (dbgmodel.h)
description: "The IDebugHostType2::GetSymbolKind method, when called on a symbol, gets the kind of symbol, such as field, base class, or type."
ms.date: 09/21/2018
keywords: ["IDebugHostType2::GetSymbolKind"]
ms.keywords: IDebugHostType2::GetSymbolKind, GetSymbolKind, IDebugHostType2.GetSymbolKind, IDebugHostType2::GetSymbolKind, IDebugHostType2.GetSymbolKind
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
 - IDebugHostType2::GetSymbolKind
 - dbgmodel/IDebugHostType2::GetSymbolKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetSymbolKind
---

# IDebugHostType2::GetSymbolKind


## -description

Gets the kind of symbol that this is (e.g.: a field, a base class, a type, etc...).

## -parameters

### -param kind

The kind of symbol (e.g.: a type, field, base class, etc…) will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

