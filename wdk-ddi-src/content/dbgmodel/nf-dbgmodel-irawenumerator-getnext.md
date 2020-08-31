---
UID: NF:dbgmodel.IRawEnumerator.GetNext
title: IRawEnumerator::GetNext (dbgmodel.h)
description: Moves the iterator forward and fetches the name of the raw element and, optionally, its value (or a reference to it) and what kind of element it is.
ms.assetid: 64162d89-113d-4383-ba11-d984a16c801b
ms.date: 12/21/2018
keywords: ["IRawEnumerator::GetNext"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IRawEnumerator::GetNext
 - dbgmodel/IRawEnumerator::GetNext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IRawEnumerator.GetNext
---

# IRawEnumerator::GetNext


## -description

Moves the iterator forward and fetches the name of the raw element and, optionally, its value (or a reference to it) and what kind of element it is. Note that depending on how this enumerator was acquired, the object returned in the value field may be the value of the raw element (EnumerateRawValues) or a reference to the raw element (EnumerateRawReferences).
    
If there was an error in reading the value of the raw element (for EnumerateRawValues, for instance), the method may return an error *AND* fill value with an error object. When the enumerator hits the end of the sequence, E_BOUNDS will be returned.

## -parameters

### -param name

The name of the raw element (e.g.: field) being enumerated is returned here.  The caller is responsible for freeing this string with the SysFreeString method.

### -param kind

The kind of symbol being enumerated (e.g.: a type, field, base class, etc…) is returned here.

### -param value

The value of the raw element (e.g.: field) being enumerated is optionally returned here.  Depending on how the enumerator was acquired, this value may be the actual value of the raw element (EnumerateRawValues) or a reference to it (EnumerateRawReferences).

## -returns

This method returns HRESULT.

## -remarks

## -see-also

[IRawEnumerator interface](nn-dbgmodel-irawenumerator.md)

