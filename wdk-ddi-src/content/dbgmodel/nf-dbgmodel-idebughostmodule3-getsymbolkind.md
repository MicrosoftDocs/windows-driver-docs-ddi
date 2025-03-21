---
UID: NF:dbgmodel.IDebugHostModule3.GetSymbolKind
tech.root: debugger
title: IDebugHostModule3::GetSymbolKind
ms.date: 02/22/2025
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
 - IDebugHostModule3::GetSymbolKind
f1_keywords:
 - IDebugHostModule3::GetSymbolKind
 - dbgmodel/IDebugHostModule3::GetSymbolKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetSymbolKind
---

## -description

Gets the kind of symbol that this is (e.g. a field, a base class, a type, etc...).

## -parameters

### -param kind

The kind of symbol (e.g.: a type, field, base class, etc…) will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostModule3 interface](nn-dbgmodel-idebughostmodule3.md)