---
UID: NE:dbgmodel.SymbolKind
title: SymbolKind
author: windows-driver-content
description: Defines the kind of a symbol.
ms.assetid: 6c1562a7-d1fb-4418-99dd-a6391cb4163d
ms.author: windowsdriverdev
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: SymbolKind, , 
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	SymbolKind
product: Windows
targetos: Windows
tech.root: debugger
---

# SymbolKind enumeration

## -description

Defines the kind of a symbol.


## -enum-fields

### -field Symbol 
Unspecified symbol type.

### -field SymbolModule 
The symbol is a module and can be queried for IDebugHostModule.

### -field SymbolType 
The symbol is a type and can be queried for IDebugHostType.

### -field SymbolField 
The symbol is a field (a data member within a structure or class) and can be queried for IDebugHostField.

### -field SymbolConstant 
The symbol is a constant value and can be queried for IDebugHostConstant.

### -field SymbolData 
The symbol is data which is not a member of a structure or class and is queryable for IDebugHostData.

### -field SymbolBaseClass 
The symbol is a base class and is queryable for IDebugHostBaseClass.

### -field SymbolPublic 
The symbol is an entry in a module's publics table (having no type information) and is queryable for IDebugHostPublic.

### -field SymbolFunction 
The symbol is a function and is queryable for IDebugHostData.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
