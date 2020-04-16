---
UID: NF:dbgmodel.IIterableConcept.GetDefaultIndexDimensionality
title: IIterableConcept::GetDefaultIndexDimensionality (dbgmodel.h)
description: The GetDefaultIndexDimensionality method returns the number of dimensions to the default index. 
ms.assetid: 877b66bb-4b7a-4e4e-8199-d90a77eabda7
ms.date: 09/19/2018
keywords: ["IIterableConcept::GetDefaultIndexDimensionality"]
f1_keywords:
 - "dbgmodel/IIterableConcept.GetDefaultIndexDimensionality"
ms.keywords: IIterableConcept::GetDefaultIndexDimensionality, GetDefaultIndexDimensionality, IIterableConcept.GetDefaultIndexDimensionality, IIterableConcept::GetDefaultIndexDimensionality, IIterableConcept.GetDefaultIndexDimensionality
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
- IIterableConcept.GetDefaultIndexDimensionality
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IIterableConcept::GetDefaultIndexDimensionality


## -description

The GetDefaultIndexDimensionality method returns the number of dimensions to the default index. If an object is not indexable, this method should return 0 and succeed (S_OK). Any object which returns a non-zero value from this method is declaring support for a protocol contract which states: 

- The object supports the indexable concept via support of [IIndexableConcept](nn-dbgmodel-iindexableconcept.md)
- The GetNext method of the [IModelIterator](nn-dbgmodel-imodeliterator.md) returned from the GetIterator method of the iterable concept will return a unique default index for each produced element. Such index will have the number of dimensions as indicated here.
- Passing the indicies returned from the GetNext method of the [IModelIterator](nn-dbgmodel-imodeliterator.md) to the GetAt method on the indexable concept ([IIndexableConcept](nn-dbgmodel-iindexableconcept.md)) will refer to the same object that GetNext produced. The same value is returned.


## -parameters

### -param contextObject
The instance (this pointer) being queried.

### -param dimensionality
The number of dimensions of the default indexer is returned here. A return value of zero indicates that the object is not indexable.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Example Implementation:** 

```cpp
IFACEMETHOD(GetDefaultIndexDimensionality)(_In_ IModelObject * /*pContextObject*/,
                                           _Out_ ULONG64 *pDimensionality)
{
    // If the object is not indexable, pDimensionality should be 0 and the 
    // method should return S_OK.  Here, the object is indexable in one dimension.
    // Providing this information requires that our iterator return these 
    // 1D indexes and that we have an indexer which accepts them.
    *pDimensionality = 1;
    return S_OK;
}
```

## -see-also

[IIterableConcept interface](nn-dbgmodel-iiterableconcept.md)
