---
UID: NF:dbgmodel.IModelIterator.Reset
title: IModelIterator::Reset
author: windows-driver-content
description: The Reset method on an iterator returned from the iterable concept will restore the position of the iterator to where it was when the iterator was first created (before the first element). 
ms.assetid: 53ee9efd-4581-4e1e-8fbe-385e7b137f64
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelIterator::Reset, Reset, IModelIterator.Reset, IModelIterator::Reset, IModelIterator.Reset
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
-	IModelIterator.Reset
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelIterator::Reset


## -description

The Reset method on an iterator returned from the iterable concept will restore the position of the iterator to where it was when the iterator was first created (before the first element). While it is strongly recommended that iterator's support the Reset method, it is not required. An iterator can be the equivalent of a C++ input iterator and only allow a single pass of forward iteration. In such case, the Reset method may fail with E_NOTIMPL. 

## -parameters


## -returns
This method returns HRESULT.

## -remarks

**Code Sample**

```cpp
IFACEMETHOD(Reset)()
{
    // It is legal for an iterator to be unable to Reset().  E_NOTIMPL can 
    // be returned in that case.  If an iterator is capable of a reset, it
    // should always prefer to implement such.
    m_position = 0;
    return S_OK;
}
```


## -see-also

[IModelIterator interface](nn-dbgmodel-imodeliterator.md)
