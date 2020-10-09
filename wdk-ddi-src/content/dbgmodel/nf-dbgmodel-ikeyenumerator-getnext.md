---
UID: NF:dbgmodel.IKeyEnumerator.GetNext
title: IKeyEnumerator::GetNext (dbgmodel.h)
description: Moves the iterator forward and fetches the name of the next key and, optionally, its value (or a reference to it) and associated metadata.
ms.assetid: 0a6a1109-c97f-4335-ac2d-434e9bd57f40
ms.date: 12/21/2018
keywords: ["IKeyEnumerator::GetNext"]
ms.keywords: IKeyEnumerator::GetNext, GetNext, IKeyEnumerator.GetNext, IKeyEnumerator::GetNext, IKeyEnumerator.GetNext
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
 - IKeyEnumerator::GetNext
 - dbgmodel/IKeyEnumerator::GetNext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IKeyEnumerator.GetNext
---

# IKeyEnumerator::GetNext


## -description

 Moves the iterator forward and fetches the name of the next key and, optionally, its value (or a reference to it) and associated metadata.
    
 Note that depending on how this enumerator was acquired, the object returned in the value field may be the value associated with the key (EnumerateKeys), the resolved value of any property that the key refers to (EnumerateKeyValues), or a reference to the key (EnumerateKeyReferences).
    
 If there was an error in resolving the value of the key (for EnumerateKeyValues, for instance), the method may return an error *AND* fill value with an error object. When the enumerator hits the end of the sequence, E_BOUNDS will be returned.

## -parameters

### -param key

The name of the key being enumerated is returned here.  The caller is responsible for freeing this string with the SysFreeString method.

### -param value

The value of the key being enumerated is returned here.  Depending on how the enumerator was acquired, this value may be the value associated with the key (EnumerateKeys), the resolved value of any property that the key refers to (EnumerateKeyValues), or a reference to the key (EnumerateKeyReferences).

### -param metadata

Any metadata associated with the key is optionally returned in this argument.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IKeyEnumerator interface](nn-dbgmodel-ikeyenumerator.md)

