---
UID: NF:dbgmodel.IModelObject.GetKey
title: IModelObject::GetKey (dbgmodel.h)
description: The GetKey method will get the value of (and the metadata associated with) a given key by name.
ms.assetid: 533111d9-50cd-4bd3-8807-6c9be2374fba
ms.date: 08/09/2018
keywords: ["IModelObject::GetKey"]
f1_keywords:
 - "dbgmodel/IModelObject.GetKey"
 - "IModelObject.GetKey"
ms.keywords: IModelObject::GetKey, GetKey, IModelObject.GetKey, IModelObject::GetKey, IModelObject.GetKey
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
- IModelObject.GetKey
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetKey


## -description

The GetKey method will get the value of (and the metadata associated with) a given key by name. Most clients should utilize the GetKeyValue method instead. If the key is a property accessor, calling this method will return the property accessor (an [IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md) interface) boxed into an [IModelObject](nn-dbgmodel-imodelobject.md). Unlike, GetKeyValue, this method will not automatically resolve the underlying value of the key by calling the GetValue method. That responsibility is the caller's. 

## -parameters

### -param key
The name of the key to get a value for.

### -param object
The value of the key will be returned in this argument. In some error cases, extended error information may be passed out in this argument even though the method returns a failing HRESULT.

### -param metadata
The metadata store associated with this key will be optionally returned in this argument.

## -returns
This method returns HRESULT that indicates success or failure.  The return values E_BOUNDS (or E_NOT_SET in some cases) indicates the key could not be found.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spProcess; /* get a process object */

ComPtr<IModelObject> spIdKey;
if (SUCCEEDED(spProcess->GetKey(L"Id", &spIdKey, nullptr)))
{
    // Unlike GetKeyValue(), spIdKey may contain a value or it may be a 
    // *property* that needs to be fetched.  Check!
    ModelObjectKind kind;
    if (SUCCEEDED(spIdKey->GetKind(&kind)))
    {
        if (kind == ObjectPropertyAccessor)
        {
            VARIANT vtProp; 
            if (SUCCEEDED(spIdKey->GetIntrinsicValue(&vtProp)))
            {
                // There is an *in-process* guarantee because of 
                // ObjectPropertyAccessor that the IUnknown is an IModelPropertyAccessor
                IModelPropertyAccessor *pPropertyAccessor = 
                    static_cast<IModelPropertyAccessor *>(vtProp.punkVal);

                // Fetch the value underneath the property accessor.  GetKeyValue 
                // would have done this for us.
                ComPtr<IModelObject> spId;
                if (SUCCEEDED(pPropertyAccessor->GetValue(L"Id", spProcess.Get(), &spId)))
                {
                    // spId now contains the value of the id.  Unbox with GetIntrinsicValueAs.
                }

                VariantClear(&vtProp);
            }
        }
        else
        {
            // spIdKey contains the value.  Unbox with GetIntrinsicValueAs.
        }
    }
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
