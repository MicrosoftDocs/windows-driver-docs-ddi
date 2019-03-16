---
UID: NF:dbgmodel.IModelPropertyAccessor.GetValue
title: IModelPropertyAccessor::GetValue (dbgmodel.h)
description: The GetValue method is the getter for the property accessor. It is called whenever a client wishes to fetch the underlying value of the property.
ms.assetid: ac405c3d-b005-4173-8b29-dedc048db1b3
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelPropertyAccessor::GetValue, GetValue, IModelPropertyAccessor.GetValue, IModelPropertyAccessor::GetValue, IModelPropertyAccessor.GetValue
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
- IModelPropertyAccessor.GetValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelPropertyAccessor::GetValue


## -description

The GetValue method is the getter for the property accessor. It is called whenever a client wishes to fetch the underlying value of the property. Note that any caller which directly gets a property accessor is responsible for passing the key name and accurate instance object (this pointer) to the property accessor's GetValue method. 

## -parameters

### -param key
The name of the key to get a value for. A caller which fetches a property accessor directly is responsible for passing this accurately.


### -param contextObject
The context object (instance this pointer) from which the property accessor was fetched.

### -param value
The underlying value of the property is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
// The full implementation class is shown for clarity.
class MyReadOnlyProperty :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IModelPropertyAccessor
        >
{
public:

    IFACEMETHOD(GetValue)(_In_ PCWSTR /*pwszKey*/, 
                          _In_ IModelObject * /*pContextObject*/, 
                          _COM_Errorptr_ IModelObject **ppValue)
    {
        HRESULT hr = S_OK;
        *ppValue = nullptr;

        VARIANT vtValue;
        vtValue.vt = VT_I4;
        vtValue.lVal = m_value;
        
        ComPtr<IModelObject> spValue;
        hr = GetManager()->CreateIntrinsicObject(ObjectIntrinsic, &vtValue, &spValue);
        if (SUCCEEDED(hr))
        {
            *ppValue = spValue.Detach();
        }

        return hr;
    }

    IFACEMETHOD(SetValue)(_In_ PCWSTR /*pwszKey*/, 
                          _In_ IModelObject * /*pContextObject*/, 
                          _In_ IModelObject * /*pValue*/)
    {
        // We are a read only property.
        return E_NOTIMPL;
    }

    HRESULT RuntimeClassInitialize(_In_ int value)
    {
        m_value = value;
        return S_OK;
    }

private:

    int m_value;
};
```

## -see-also

[IModelPropertyAcessor interface](nn-dbgmodel-imodelpropertyaccessor.md)
