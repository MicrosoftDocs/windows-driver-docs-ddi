---
UID: NF:dbgmodel.IModelIterator.GetNext
title: IModelIterator::GetNext
author: windows-driver-content
description: TBD
ms.assetid: 27a21fcb-dc5e-4551-a48d-321db2715aec
ms.author: windowsdriverdev
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelIterator::GetNext, GetNext, IModelIterator.GetNext, IModelIterator::GetNext, IModelIterator.GetNext
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
-	IModelIterator.GetNext
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelIterator::GetNext


## -description

The GetNext method moves the iterator forward and fetches the next iterated element. If the object is indexable in addition to being iterable and this is indicated by the GetDefaultIndexDimensionality argument returning a non-zero value, this method may optionally return the default indicies to get back to the produced value from the indexer. Note that a caller may choose to pass 0/nullptr and not retrieve any indicies. It is considered illegal for the caller to request partial indicies (e.g.: less than the number produced by GetDefaultIndexDimensionality). 

If the iterator moved forward successfully but there was an error in reading the value of the iterated element, the method may return an error *AND* fill "object" with an error object. 
At the end of iteration of the contained elements, the iterator will return E_BOUNDS from the GetNext method. Any subsequent call (unless there has been an intervening Reset call) will also return E_BOUNDS. 


## -parameters

### -param object
The object produced from the iterator is returned here.

### -param dimensions
The number of dimensions of the default index that the caller is requesting. If this is zero, the caller does not wish the default index returned. If it is non-zero, it should be at least as high as the default index's dimensionality.

### -param indexers
A buffer of size dimensions which will be filled in with the default indicies to get back to the returned element from the indexer.

### -param metadata
If there is any metadata associated with the iterated element, it is returned (optionally) in this argument.


## -returns
This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
// The full class is shown here for clarity on the iterator!  For the sake 
// of example, this iterator produces integers from 10 to 
// 10 + <value of 'NumElements' key> which are indexed by a linear 0-based index.
class MyObjectIterator :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IModelIterator
        >
{
public:

    IFACEMETHOD(Reset)()
    {
        m_position = m_numElements = 0;

        ComPtr<IModelObject> spNumElements;
        HRESULT hr = m_spContextObject->GetKeyValue(L"NumElements", 
                                                    &spNumElements, 
                                                    nullptr);
        if (SUCCEEDED(hr))
        {
            VARIANT vtVal;
            if (SUCCEEDED(spNumElements->GetIntrinsicValueAs(VT_UI8, &vtVal)))
            {
                m_numElements = vtVal.ullVal;
            }
        }
    
        return hr;
    }

    IFACEMETHOD(GetNext)(_COM_Errorptr_ IModelObject **ppValue, 
                         _In_ ULONG64 dimensions, 
                         _Out_writes_(dimensions) IModelObject **ppIndexers,
                         _COM_Outptr_opt_result_maybe_null_ IKeyStore *ppMetadata)
    {
        HRESULT hr = S_OK;
        *ppMetadata = nullptr;
        for (ULONG64 i = 0; i < dimensions; ++i)
        {
            ppIndexers[i] = nullptr;
        }

        // We are indexable in one dimension.  Verify the call is valid.  
        // The caller either doesn't care (dimensions == 0) or passes the number 
         // of dimensions we indicate (dimensions == 1)
        if (dimensions != 0 && dimensions != 1)
        {
            return E_INVALIDARG; 
        }

        // E_BOUNDS indicates the end of the iteration
        if (m_position >= m_numElements)
        {
            return E_BOUNDS;
        }

        ComPtr<IModelObject> spValue; 
        ComPtr<IModelObject> spIndex;

        VARAINT vtValue;
        vtValue.vt = VT_UI8;
        vtValue.ullVal = m_position + 10; // Just as example.  We produce 
                                          // values from 10 -> 10 + 'NumElements'
        hr = GetManager()->CreateIntrinsicObject(ObjectIntrinsic, &vtValue, &spValue);
        if (SUCCEEDED(hr))
        {
            if (dimensions == 1)
            {
                VARIANT vtIdx;
                vtIdx.vt = VT_UI8;
                vtIdx.ullVal = m_position;
                hr = GetManager()->CreateIntrinsicObject(ObjectIntrinsic, 
                                                         &vtIdx, 
                                                         &spIndex);
            }
        }

        if (SUCCEEDED(hr))
        {
            *ppValue = spValue.Detach();
            if (dimensions == 1)
            {
                ppIndexers[0] = spIndex.Detach();
            }

            ++m_position;
        }

        return hr;
    }

    HRESULT RuntimeClassInitialize(_In_ IModelObject *pContextObject)
    {
        m_spContextObject = pContextObject;
        return Reset();
    }

private:

    ULONG64 m_position;
    ULONG64 m_numElements;
    ComPtr<IModelObject> m_spContextObject;

};
```


## -see-also

[IModelIterator interface](nn-dbgmodel-imodeliterator.md)
