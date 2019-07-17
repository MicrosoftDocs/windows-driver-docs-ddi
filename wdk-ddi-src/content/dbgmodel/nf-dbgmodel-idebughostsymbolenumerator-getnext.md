---
UID: NF:dbgmodel.IDebugHostSymbolEnumerator.GetNext
title: IDebugHostSymbolEnumerator::GetNext (dbgmodel.h)
description: Moves the iterator forward and fetches the next symbol in the set.
ms.assetid: 906a53c9-af84-46c6-9b39-f55b85786641
ms.date: 12/21/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHostSymbolEnumerator.GetNext"
ms.keywords: IDebugHostSymbolEnumerator::GetNext, GetNext, IDebugHostSymbolEnumerator.GetNext, IDebugHostSymbolEnumerator::GetNext, IDebugHostSymbolEnumerator.GetNext
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
- IDebugHostSymbolEnumerator.GetNext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbolEnumerator::GetNext


## -description

Moves the iterator forward and fetches the next symbol in the set.

E_BOUNDS will be returned when the enumerator hits the end of the set.

## -parameters

### -param symbol

The next enumerated symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostSymbolEnumerator interface](nn-dbgmodel-idebughostsymbolenumerator.md)
