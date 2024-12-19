---
UID: NF:dbgmodel.IDebugHostBaseClass.GetSymbolKind
title: IDebugHostBaseClass::GetSymbolKind (dbgmodel.h)
description: "The IDebugHostBaseClass::GetSymbolKind method, when called on a symbol, gets the kind of symbol, such as field, base class, or type."
ms.date: 09/21/2018
keywords: ["IDebugHostBaseClass::GetSymbolKind"]
ms.keywords: IDebugHostBaseClass::GetSymbolKind, GetSymbolKind, IDebugHostBaseClass.GetSymbolKind, IDebugHostBaseClass::GetSymbolKind, IDebugHostBaseClass.GetSymbolKind
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
 - IDebugHostBaseClass::GetSymbolKind
 - dbgmodel/IDebugHostBaseClass::GetSymbolKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass::GetSymbolKind
---

# IDebugHostBaseClass::GetSymbolKind


## -description

Gets the kind of symbol that this is, for example, a field, a base class, a type, etc.

## -parameters

### -param kind

The kind of symbol, for example, a type, field, base class, etc,  will be returned here.


## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostBaseClass interface](nn-dbgmodel-idebughostbaseclass.md)

