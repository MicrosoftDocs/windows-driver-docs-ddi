---
UID: NF:dbgmodel.IDebugHostBaseClass2.GetSymbolKind
tech.root: debugger
title: IDebugHostBaseClass2::GetSymbolKind
ms.date: 12/16/2024
targetos: Windows
description: The GetSymbolKind method, when called on a symbol, gets the kind of symbol, such as field, base class, or type.
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
 - IDebugHostBaseClass2::GetSymbolKind
f1_keywords:
 - IDebugHostBaseClass2::GetSymbolKind
 - dbgmodel/IDebugHostBaseClass2::GetSymbolKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetSymbolKind
---

## -description

Gets the kind of symbol that this is, for example a field, a base class, a type, etc.

## -parameters

### -param kind

The kind of symbol (for example a type, field, base class, etc) will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)