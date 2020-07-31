---
UID: NF:dbgmodel.IModelObject.EnumerateKeyValues
title: IModelObject::EnumerateKeyValues (dbgmodel.h)
description: The EnumerateKeyValues method is the first method a client will turn to in order to enumerate all of the keys on an object.
ms.assetid: e1452944-0567-4b3d-a892-fc3e45ae34af
ms.date: 07/20/2018
keywords: ["IModelObject::EnumerateKeyValues"]
f1_keywords:
 - "dbgmodel/IModelObject.EnumerateKeyValues"
 - "IModelObject.EnumerateKeyValues"
ms.keywords: IModelObject::EnumerateKeyValues, EnumerateKeyValues, IModelObject.EnumerateKeyValues, IModelObject::EnumerateKeyValues, IModelObject.EnumerateKeyValues
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
- IModelObject.EnumerateKeyValues
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::EnumerateKeyValues


## -description

The EnumerateKeyValues method is the first method a client will turn to in order to enumerate all of the keys on an object (this includes all keys implemented anywhere in the tree of parent models). It is important to note that EnumerateKeyValues will enumerate any keys defined by duplicate names in the object tree; however -- methods like GetKeyValue and SetKeyValue will only manipulate the first instance of a key with the given name as discovered by the depth-first-traversal. 

## -parameters

### -param enumerator
An enumerator for all keys on the object (and all of its parent models) and their values and metadata is returned in this argument as an [IKeyEnumerator](nn-dbgmodel-ikeyenumerator.md).

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get the object you want to enumerate */

ComPtr<IKeyEnumerator> spEnum;
if (SUCCEEDED(spObject->EnumerateKeyValues(&spEnum)))
{
    HRESULT hr = S_OK;
    while (SUCCEEDED(hr))
    {
        BSTR keyName;
        ComPtr<IModelObject> spKeyValue;
        hr = spEnum->GetNext(&keyName, &spKeyValue, nullptr);
        if (SUCCEEDED(hr))
        {
            // keyName contains the name of the key
            // spKeyValue contains the value of the key

            SysFreeString(keyName);
        }
    }

    // hr == E_BOUNDS  : We hit the end of the enumerator
    // hr == E_ABORT   : User is requesting interruption of the 
    // operation / stop immediately and flow the error
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
