---
UID: NF:dbgmodel.IModelKeyReference2.GetKey
title: IModelKeyReference2::GetKey
author: windows-driver-content
description: TBD
ms.assetid: edcad7fa-c729-4d9b-b083-c350e346ac50
ms.author: windowsdriverdev
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference2::GetKey, GetKey, IModelKeyReference2.GetKey, IModelKeyReference2::GetKey, IModelKeyReference2.GetKey
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
-	IModelKeyReference2.GetKey
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelKeyReference2::GetKey


## -description

The GetKey method on a key reference behaves as the GetKey method on IModelObject would. It returns the value of the underlying key and any metadata associated with the key. If the value of the key happens to be a property accessor, this will return the property accessor (IModelPropertyAccessor) boxed into an IModelObject. This method will not call the underlying GetValue or SetValue methods on the property accessor. 

## -parameters

### -param object
The value of the key will be returned here.

### -param metadata
Optional metadata which is associated with the key will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    ComPtr<IModelObject> spKey;
    if (SUCCEEDED(spKeyRef->GetKey(&spKey, nullptr)))
    {
        // spKey contains the equivalent of spObject->GetKey(L"Id", &spKey, nullptr)
        // This may be a property accessor since this was not a GetKeyValue.  
        // Check and fetch.  Note that GetKeyValue would do this for you.
        ModelObjectKind kind;
        if (SUCCEEDED(spKey->GetKind(&kind)))
        {
            if (kind == ObjectPropertyAccessor)
            {
                VARIANT vtProp;
                if (SUCCEEDED(spKey->GetIntrinsicValue(&vtProp)))
                {
                    // We are guaranteed *in-process* that the IUnknown is 
                    // an IModelPropertyAccessor via the ObjectPropertyAccessor
                    IModelPropertyAccessor *pProperty =
                        static_cast<IModelPropertyAccessor *>(vtProp.punkVal);
                    
                    // In order to fetch, we need to know the context object and 
                    // the key name.  Fetch it from the key reference.
                    ComPtr<IModelObject> spContextObject;
                    if (SUCCEEDED(spKeyRef->GetContextObject(&spContextObject)))
                    {
                        BSTR keyName;
                        if (SUCCEEDED(spKeyRef->GetName(&keyName)))
                        {
                            ComPtr<IModelObject> spKeyValue; 
                            if (SUCCEEDED(pProperty->GetValue(keyName,
                                                              spContextObject.Get(),
                                                              &spKeyValue)))
                            {
                                // spKeyValue contains the value of the "Id" key.
                            }

                            SysFreeString(keyName);
                        }
                    }

                    VariantFree(&vtProp);
                }
            }
            else
            {
                // spKey contains the value of the "Id" key.
            }
        }
    }
}
```

## -see-also

[IModelKeyReference2 interface](nn-dbgmodel-imodelkeyreference2.md)
