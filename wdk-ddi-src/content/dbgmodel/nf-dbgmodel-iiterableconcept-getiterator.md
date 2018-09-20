---
UID: NF:dbgmodel.IIterableConcept.GetIterator
title: IIterableConcept::GetIterator
author: windows-driver-content
description: TBD
ms.assetid: 1060b1b8-8a7c-4548-8e87-0449275bd071
ms.author: windowsdriverdev
ms.date: 09/19/2018
ms.topic: method
ms.keywords: IIterableConcept::GetIterator, GetIterator, IIterableConcept.GetIterator, IIterableConcept::GetIterator, IIterableConcept.GetIterator
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
-	IIterableConcept.GetIterator
product: Windows
targetos: Windows


---

# IIterableConcept::GetIterator


## -description

The GetIterator method on the iterable concept returns an iterator interface which can be used to iterate the object. The returned iterator must remember the context object that was passed to the GetIterator method. It will not be passed to methods on the iterator itself. 

## -parameters

### -param contextObject
The instance (this pointer) for which to acquire an iterator.

### -param iterator
An implementation of IModelIterator which iterates the instance object is returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Example Implementation:** 

```cpp
IFACEMETHOD(GetIterator)(_In_ IModelObject *pContextObject, 
                         _COM_Outptr_ IModelIterator **ppIterator)
{
    HRESULT hr = S_OK:
    *ppIterator = nullptr;

    // The iterator is not going to be passed the context object any more.  
    // If it needs this (to access fields for iteration, etc...), it must
    // capture that in its own state.
    ComPtr<MyObjectIterator> spIter;
    hr = Microsoft::WRL::MakeAndInitialize<MyObjectIterator>(&spIter, pContextObject);
    if (SUCCEEDED(hr))
    {
        *ppIterator = spIter.Detach();
    }
    return hr;
}
```


## -see-also

[IIterableConcept interface](nn-dbgmodel-iiterableconcept.md)