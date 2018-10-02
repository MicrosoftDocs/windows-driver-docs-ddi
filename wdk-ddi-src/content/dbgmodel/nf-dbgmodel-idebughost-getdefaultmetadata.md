---
UID: NF:dbgmodel.IDebugHost.GetDefaultMetadata
title: IDebugHost::GetDefaultMetadata
author: windows-driver-content
description: TBD
ms.assetid: e624b7fe-b691-4e1a-93d5-f62747d929ac
ms.author: windowsdriverdev
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IDebugHost::GetDefaultMetadata, GetDefaultMetadata, IDebugHost.GetDefaultMetadata, IDebugHost::GetDefaultMetadata, IDebugHost.GetDefaultMetadata
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
-	IDebugHost.GetDefaultMetadata
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHost::GetDefaultMetadata


## -description

The GetDefaultMetadata method returns a default metadata store that may be used for certain operations (e.g.: string conversion) when no explicit metadata has been passed. This allows the debug host to have some control over the way some data is presented. For example, the default metadata may include a PreferredRadix key, allowing the host to indicate whether ordinals should be displayed in decimal or hexadecimal if not otherwise specified.

Note that property values on the default metadata store must be manually resolved and must pass the object for which the default metadata is being queried. The GetKey method should be used in lieu of GetKeyValue. 


## -parameters

### -param defaultMetadataStore
The debug host's default metadata store is returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

Usage Example (typically called by the data model itself): 

```cpp
ComPtr<IDebugHost> spHost;     /* get the debug host */
ComPtr<IModelObject> spObject; /* find some object that we want default metadata for */

ComPtr<IKeyStore> spDefaultMetadata;
if (SUCCEEDED(spHost->GetDefaultMetadata(&spDefaultMetadata)))
{
    // Query the preferred display radix for spObject.  We must resolve the 
    // property manually and pass spObject as the context object.
    // This allows the default store to do things like say "radix is 10 for 
    // signed types and 16 for unsigned types"
    ComPtr<IModelObject> spRadixKey;
    if (SUCCEEDED(spDefaultMetadata->GetKey(L"PreferredRadix", &spRadixKey, nullptr)))
    {
        // There is a default radix in which to display spObject.  Resolve 
        // the property manually.
        ModelObjectKind kind;
        if (SUCCEEDED(spRadixKey->GetKind(&kind)))
        {
            if (kind == ObjectPropertyAccessor)
            {
                VARIANT vtProp;
                if (SUCCEEDED(spRadixKey->GetIntrinsicValue(&vtProp)))
                {
                    // There is an *in process* guarantee that the IUnknown 
                    // is IModelPropertyAccessor because of ObjectPropertyAccessor
                    IModelPropertyAccessor *pProperty =
                       static_cast<IModelPropertyAccessor *>(vtProp.punkVal);

                    ComPtr<IModelObject> spRadix;
                    if (SUCCEEDED(pProperty->GetValue(L"PreferredRadix",
                                                      spObject.Get(), 
                                                      &spRadix)))
                    {
                        // spRadix contains the display radix.  Unbox
                        // with GetIntrinsicValueAs.
                    }

                    VariantClear(&vtProp);
                }
            }
            else
            {
                // spRadixKey contains the display radix.  Unbox 
                // with GetIntrinsicValueAs.
            }
        }
    }
}
```


Implementation Example (a host would normally do this): 

```cpp
// Define a property which returns a radix of 16 for unsigned values and 10 
// for signed values
class RadixProperty :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IModelPropertyAccessor
        >
{
public:

    IFACEMETHOD(GetValue)(_In_ PCWSTR /*pwszKeyName*/, 
                          _In_opt_ IModelObject *pContextObject, 
                          _Out_ IModelObject **ppValue)
    {
        HRESULT hr = S_OK;
        *ppValue = nullptr;

        unsigned int radix = 0;
        if (pContextObject != nullptr)
        {
            ModelObjectKind kind;
            hr = pContextObject->GetKind(&kind);
            if (SUCCEEDED(hr) && kind == ObjectIntrinsic)
            {
                VARIANT vtValue;
                if (SUCCEEDED(pContextObject->GetIntrinsicValue(&vtValue)))
                {
                    switch(vtValue.vt)
                    {
                        case VT_I1: case VT_I2: case VT_I4: case VT_I8:
                            radix = 10;
                            break;
                        case VT_UI1: case VT_UI2: case VT_UI4: case VT_UI8:
                            radix = 16;
                            break;
                    }
                    VariantClear(&vtValue);
                }
            }
        }

        ComPtr<IModelObject> spResultRadix;
        if (SUCCEEDED(hr) && radix != 0)
        {
            VARIANT vtRadix;
            vtRadix.vt = VT_UI4;
            vtRadix.ulVal = radix;
            hr = GetManager()->CreateIntrinsicObject(ObjectIntrinsic, 
                                                     &vtRadix, 
                                                     &spResultRadix);
        }
        else if (SUCCEEDED(hr) && radix == 0)
        {
            // We succeeded but don't have a defined radix.  Return no value.
            hr = GetManager()->CreateNoValue(&spResultRadix);
        }

        if (SUCCEEDED(hr))
        {
            *ppValue = spResultRadix.Detach();
        }

        return hr;
    }

    IFACEMETHOD(SetValue)(_In_ PCWSTR /*pwszKeyName*/, 
                          _In_opt_ IModelObject * /*pContextObject*/, 
                          _In_ IModelObject * /*pValue*/)
    {
        return E_NOTIMPL;
    }
};

// Implementation on the implementation class for IDebugHost:
IFACEMETHOD(GetDefaultMetadata)(_Out_ IKeyStore **ppMetadata)
{
    HRESULT hr = S_OK;
    *ppMetadata = nullptr;

    ComPtr<IKeyStore> spMetadata;
    hr = GetManager()->CreateMetadataStore(&spMetadata));
    if (SUCCEEDED(hr))
    {
        ComPtr<RadixProperty> spProperty = Microsoft::WRL::Make<RadixProperty>();
        if (spProperty == nullptr)
        {
             hr = E_OUTOFMEMORY;
        }
        else
        {
            VARIANT vtProp;
            vtProp.vt = VT_UNKNOWN;
            vtProp.punkVal = static_cast<IModelPropertyAccessor *>(spProperty.Get());

            ComPtr<IModelObject> spPropertyObject;
            hr = GetManager()->CreateIntrinsicObject(ObjectPropertyAccessor, 
                                                     &vtProp, 
                                                     &spPropertyObject));
            if (SUCCEEDED(hr))
            {
                hr = spDefaultMetadata->SetKey(L"PreferredRadix",
                                               spPropertyObject.Get(), 
                                               nullptr));
            }
        }
    }

    if (SUCCEEDED(hr))
    {
        *ppMetaData = spMetadata.Detach();
    }

    return hr;
}
```

## -see-also

[IDebugHost interface](nn-dbgmodel-idebughost.md)
