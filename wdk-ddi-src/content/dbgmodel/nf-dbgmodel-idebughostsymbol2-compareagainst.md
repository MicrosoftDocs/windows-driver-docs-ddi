---
UID: NF:dbgmodel.IDebugHostSymbol2.CompareAgainst
title: IDebugHostSymbol2::CompareAgainst (dbgmodel.h)
description: Compares two symbols for equality. 
ms.assetid: abdc73ad-ae24-43cd-9b66-9f063a554cda
ms.date: 09/20/2018
ms.topic: method
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostSymbol2.CompareAgainst
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
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
