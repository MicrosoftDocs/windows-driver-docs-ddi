---
UID: NF:dbgmodel.IModelObject.EnumerateRawValues
title: IModelObject::EnumerateRawValues (dbgmodel.h)
description: The EnumerateRawValues method enumerates all native children (fields, base classes, etc...) of the given object. 
ms.assetid: 950019c9-1e39-46bd-be75-fa7fbf52d7da
ms.date: 07/20/2018
keywords: ["IModelObject::EnumerateRawValues"]
f1_keywords:
 - "dbgmodel/IModelObject.EnumerateRawValues"
 - "IModelObject.EnumerateRawValues"
ms.keywords: IModelObject::EnumerateRawValues, EnumerateRawValues, IModelObject.EnumerateRawValues, IModelObject::EnumerateRawValues, IModelObject.EnumerateRawValues
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
- IModelObject.EnumerateRawValues
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::EnumerateRawValues


## -description

The EnumerateRawValues method enumerates all native children (e.g.: fields, base classes, etc...) of the given object. 

## -parameters

### -param kind
Indicates the kind of native symbol to fetch (e.g.: a base class or a data member)

### -param searchFlags
An optional set of flags specifying the behavior of the search for the native construct.

### -param enumerator
An enumerator which will enumerate every native child of the kind specified by the kind argument as an [IRawEnumerator](nn-dbgmodel-irawenumerator.md) interface. 


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spMessage; /* get a tagMSG */

ComPtr<IRawEnumerator> spEnum;
if (SUCCEEDED(spMessage->EnumerateRawValues(SymbolField, RawSearchNone, &spEnum)))
{
    HRESULT hr = S_OK;
    while (SUCCEEDED(hr))
    {
        BSTR fieldName;
        SymbolKind symKind;
        ComPtr<IModelObject> spFieldValue;
        hr = spEnum->GetNext(&fieldName, &symbolKind, &spFieldValue);
        if (SUCCEEDED(hr))
        {
            // fieldName contains the name of the field, symKind contains the kind of 
            // symbol matched (SymbolField in this case), spFieldValue contains the value
            // For tagMSG (with symbols), the enumerator should produce field names and 
            // values for 'hwnd', 'message', 'wParam', 'lParam', 'time', and 'pt'
            SysFreeString(fieldName);
        }
    }

    // hr == E_BOUNDS : We hit the end of the enumerator
    // hr == E_ABORT  : There was a user request for an interrupt / propagate that upward immediately
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
