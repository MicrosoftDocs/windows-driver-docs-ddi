---
UID: NF:dbgmodel.IDebugHostSymbol2.CompareAgainst
title: IDebugHostSymbol2::CompareAgainst (dbgmodel.h)
description: "The IDebugHostSymbol2::CompareAgainst method, when called on a symbol, compares the symbol against another specified symbol for interface pointer equality."
ms.date: 09/20/2018
keywords: ["IDebugHostSymbol2::CompareAgainst"]
ms.keywords: IDebugHostSymbol2::CompareAgainst, CompareAgainst, IDebugHostSymbol2.CompareAgainst, IDebugHostSymbol2::CompareAgainst, IDebugHostSymbol2.CompareAgainst
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
 - IDebugHostSymbol2::CompareAgainst
 - dbgmodel/IDebugHostSymbol2::CompareAgainst
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbol2::CompareAgainst
---

# IDebugHostSymbol2::CompareAgainst


## -description

Compares two symbols for equality.  A host is under no obligation to ensure that there is interface pointer equality for two identical symbols.  This can be used to check for equality. 

Note that presently, "comparisonFlags" is reserved.

## -parameters

### -param pComparisonSymbol

The symbol to compare against.

### -param comparisonFlags

Reserved.  Must be set to 0.

### -param pMatches

An indication of whether the symbols are equal will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostSymbol2 interface](nn-dbgmodel-idebughostsymbol2.md)

