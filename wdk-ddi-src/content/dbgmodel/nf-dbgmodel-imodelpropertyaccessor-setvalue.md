---
UID: NF:dbgmodel.IModelPropertyAccessor.SetValue
title: IModelPropertyAccessor::SetValue (dbgmodel.h)
description: The SetValue method is the setter for the property accessor. It is called whenever a client wishes to assign a value to the underlying property.
ms.date: 08/13/2018
keywords: ["IModelPropertyAccessor::SetValue"]
ms.keywords: IModelPropertyAccessor::SetValue, SetValue, IModelPropertyAccessor.SetValue, IModelPropertyAccessor::SetValue, IModelPropertyAccessor.SetValue
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
 - IModelPropertyAccessor::SetValue
 - dbgmodel/IModelPropertyAccessor::SetValue
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelPropertyAccessor.SetValue
---

# IModelPropertyAccessor::SetValue


## -description

The SetValue method is the setter for the property accessor. It is called whenever a client wishes to assign a value to the underlying property. Many properties are read-only. In such cases, calling the SetValue method will return E_NOTIMPL. Note that any caller which directly gets a property accessor is responsible for passing the key name and accurate instance object (this pointer) to the property accessor's SetValue method.

## -parameters

### -param key

The name of the key to get a value for. A caller which fetches a property accessor directly is responsible for passing this accurately.

### -param contextObject

The context object (instance this pointer) from which the property accessor was fetched.

### -param value

The value to assign to the property.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
class MyReadWriteProperty :
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
                          _In_ IModelObject *pValue)
    {
        VARIANT vtValue;
        HRESULT hr = pValue->GetIntrinsicValueAs(VT_I4, &vtValue);
        if (SUCCEEDED(hr))
        {
            m_value = vtValue.lVal;
        }
        return S_OK;
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

