---
UID: NF:dbgmodel.IIndexableConcept.SetAt
title: IIndexableConcept::SetAt (dbgmodel.h)
description: The SetAt method attempts to set the value at a particular N-dimensional index from within the indexed object.
ms.date: 09/19/2018
keywords: ["IIndexableConcept::SetAt"]
ms.keywords: IIndexableConcept::SetAt, SetAt, IIndexableConcept.SetAt, IIndexableConcept::SetAt, IIndexableConcept.SetAt
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
 - IIndexableConcept::SetAt
 - dbgmodel/IIndexableConcept::SetAt
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IIndexableConcept::SetAt
---

# IIndexableConcept::SetAt


## -description

The SetAt method attempts to set the value at a particular N-dimensional index from within the indexed object. An indexer of N-dimensions where N is the value returned from GetDimensionality must be supported. Note that an object may be indexable in different domains by different types (e.g.: indexable via both ordinals and strings). Some indexers are read-only. In such cases, E_NOTIMPL will be returned from any call to the SetAt method.

## -parameters

### -param contextObject

The instance object (this pointer) which is being indexed is passed here.

### -param indexerCount

The number of dimensions that the object is being indexed in.

### -param indexers

An array (sized according to the indexerCount) of indicies indicating where inside the instance object to access.

### -param value

The value of the element to assign at the specified indicies.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Example Implementation:** 

```cpp
IFACEMETHOD(SetAt)(_In_ IModelObject * /*pContextObject*/, 
                   _In_ ULONG64 indexerCount, 
                   _In_reads_(indexerCount) IModelObject ** /*ppIndexers*/, 
                   _In_ IModelObject * /*pValue*/)
{
    // We are read-only.  Do not allow Set.  An implementation would be very 
    // close to the implementation of GetAt (only setting some underlying 
    // value instead of fetching it)
    return E_NOTIMPL;
}
```

## -see-also

[IIndexableConcept interface](nn-dbgmodel-iindexableconcept.md)

