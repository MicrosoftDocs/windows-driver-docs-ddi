---
UID: NF:dbgmodel.IDebugHostSymbol2.EnumerateChildrenEx
title: IDebugHostSymbol2::EnumerateChildrenEx (dbgmodel.h)
description: Enumerates all child symbols of the given type, name, and extended information which is present.
ms.assetid: 8479d24b-be5f-4c21-adea-699af64adeb2
ms.date: 09/28/2018
ms.topic: method
ms.keywords: IDebugHostSymbol2::EnumerateChildrenEx, EnumerateChildrenEx, IDebugHostSymbol2.EnumerateChildrenEx, IDebugHostSymbol2::EnumerateChildrenEx, IDebugHostSymbol2.EnumerateChildrenEx
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
- IDebugHostSymbol2.EnumerateChildrenEx
product:
- Windows
targetos: Windows


tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol2::EnumerateChildrenEx


## -description

Enumerates all child symbols of the given type, name, and extended information which is present.

This behaves identically to EnumerateChildren when searchInfo is nullptr.  SymbolType::Symbol 
can be used to search to search for any kind of child. Note that if name is nullptr, children of any name will be produced by the resulting enumerator.

## -parameters

### -param kind
Indicates what kinds of child symbols the caller wishes to enumerate. If the flat value Symbol is passed, all kinds of child symbols will be enumerated.

### -param name
If specified, only child symbols with a name as given in this argument will be enumerated.

### -param searchInfo
A pointer to a struct SymbolSearchInfo which describes attributes of how the symbol search should proceed.  The caller should ensure that the HeaderSize and InfoSize fields of the SymbolSearchInfo are filled out appropriately prior to passing the structure to this method.  For searches involving types, a TypeSearchInfo structure follows. 

### -param ppEnum
An enumerator which enumerates child symbols of the specified kind and name will be returned here.


## -returns
This method returns HRESULT which indicate success or failure.

## -remarks

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)
