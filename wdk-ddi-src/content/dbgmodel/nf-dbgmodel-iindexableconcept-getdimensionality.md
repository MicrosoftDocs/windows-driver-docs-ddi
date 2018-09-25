---
UID: NF:dbgmodel.IIndexableConcept.GetDimensionality
title: IIndexableConcept::GetDimensionality
author: windows-driver-content
description: TBD
ms.assetid: 6ae1e5d9-4b46-4129-a78a-aab2c60ba49c
ms.author: windowsdriverdev
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IIndexableConcept::GetDimensionality, GetDimensionality, IIndexableConcept.GetDimensionality, IIndexableConcept::GetDimensionality, IIndexableConcept.GetDimensionality
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
-	IIndexableConcept.GetDimensionality
product: Windows
targetos: Windows


---

# IIndexableConcept::GetDimensionality


## -description

The GetDimensionality method returns the number of dimensions that the object is indexed in. Note that if the object is both iterable and indexable, the implementation of GetDefaultIndexDimensionality must agree with the implementation of GetDimensionality as to how many dimensions the indexer has. 

## -parameters

### -param contextObject
The instance object (this pointer) which is being indexed is passed here.

### -param dimensionality
The number of dimensions that the object is indexed in is returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Example Implementation:** 

```cpp
IFACEMETHOD(GetDimensionality)(_In_ IModelObject * /*pContextObject*/, 
                               _Out_ ULONG64 *pDimensionality)
{
    // If the object is iterable, the value returned here **MUST** match 
    // what is returned from GetDefaultIndexDimensionality.
    *pDimensionality = 1;
    return S_OK;
}
```



## -see-also

[IIndexableConcept interface](nn-dbgmodel-iindexableconcept.md)