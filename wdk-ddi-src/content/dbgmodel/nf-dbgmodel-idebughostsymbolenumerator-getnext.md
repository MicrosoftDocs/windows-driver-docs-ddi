---
UID: NF:dbgmodel.IDebugHostSymbolEnumerator.GetNext
title: IDebugHostSymbolEnumerator::GetNext (dbgmodel.h)
description: Moves the iterator forward and fetches the next symbol in the set.
ms.date: 12/21/2018
keywords: ["IDebugHostSymbolEnumerator::GetNext"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostSymbolEnumerator::GetNext
 - dbgmodel/IDebugHostSymbolEnumerator::GetNext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbolEnumerator.GetNext
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

