---
UID: NF:dbgmodel.IRawEnumerator.GetNext
title: IRawEnumerator::GetNext
author: windows-driver-content
description: TBD
ms.assetid: 64162d89-113d-4383-ba11-d984a16c801b
ms.author: windowsdriverdev
ms.date: 08/13/2018  
ms.topic: method
ms.keywords: IRawEnumerator::GetNext, GetNext, IRawEnumerator.GetNext, IRawEnumerator::GetNext, IRawEnumerator.GetNext
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IRawEnumerator.GetNext
product: Windows
targetos: Windows


tech.root: debugger
---

# IRawEnumerator::GetNext


## -description

Moves the iterator forward and fetches the name of the raw element and, optionally, its value (or a reference to it) and what kind of element it is. Note that depending on how this enumerator was acquired, the object returned in the value field may be the value of the raw element (EnumerateRawValues) or a reference to the raw element (EnumerateRawReferences).
    
If there was an error in reading the value of the raw element (for EnumerateRawValues, for instance), the method may return an error *AND* fill value with an error object. When the enumerator hits the end of the sequence, E_BOUNDS will be returned.

## -parameters

### -param name

### -param kind

### -param value


## -returns
This method returns HRESULT.
## -remarks

## -see-also

[IRawEnumerator interface](nn-dbgmodel-irawenumerator.md)
