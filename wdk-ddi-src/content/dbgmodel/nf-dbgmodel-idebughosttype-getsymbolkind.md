---
UID: NF:dbgmodel.IDebugHostType.GetSymbolKind
title: IDebugHostType::GetSymbolKind (dbgmodel.h)
description: Gets the kind of symbol that this is (e.g. a field, a base class, a type, etc...).
ms.assetid: b2ba41f6-57ee-498f-965d-512ae0ed3946
ms.date: 06/10/2019
keywords: ["IDebugHostType::GetSymbolKind"]
ms.keywords: IDebugHostType::GetSymbolKind, GetSymbolKind, IDebugHostType.GetSymbolKind, IDebugHostType::GetSymbolKind, IDebugHostType.GetSymbolKind
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
 - IDebugHostType::GetSymbolKind
 - dbgmodel/IDebugHostType::GetSymbolKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType.GetSymbolKind
---

# IDebugHostType::GetSymbolKind


## -description

Gets the kind of symbol that this is (e.g.: a field, a base class, a type, etc...). See the [SymbolKind Enumeration](ne-dbgmodel-symbolkind.md) for more information.

## -parameters

### -param kind

The kind of symbol (e.g.: a type, field, base class, etc…) will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)

