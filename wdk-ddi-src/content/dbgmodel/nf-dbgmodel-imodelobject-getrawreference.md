---
UID: NF:dbgmodel.IModelObject.GetRawReference
title: IModelObject::GetRawReference (dbgmodel.h)
description: The GetRawReference method finds a native construct within the given object and returns a reference to it. 
ms.assetid: 2a886a30-3403-4276-be7c-93348e2b9eea
ms.date: 08/09/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IModelObject.GetRawReference"
ms.keywords: IModelObject::GetRawReference, GetRawReference, IModelObject.GetRawReference, IModelObject::GetRawReference, IModelObject.GetRawReference
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
- IModelObject.GetRawReference
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetRawReference


## -description

The GetRawReference method finds a native construct within the given object and returns a reference to it. Such a construct may be a field, a base class, a field in a base class, a member function, etc... It is important to distinguish the reference returned here (an object of the type ObjectTargetObjectReference) from a language reference (e.g.: a C++ & or && style reference). 

## -parameters

### -param kind
Indicates the kind of native symbol to fetch (e.g.: a base class or a data member)

### -param name
The name of the native construct to fetch.

### -param searchFlags
An optional set of flags specifying the behavior of the search for the native construct.

### -param object
An [IModelObject](nn-dbgmodel-imodelobject.md) representing the fetched native construct will be returned here. Note that in some circumstances, extended error information may be returned in this argument even if the HRESULT indicates failure. 


## -returns
This method returns HRESULT that indicates success or failure. The return values E_BOUNDS (or E_NOT_SET in some cases) indicates the field could not be found.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spMessage; /* get a tagMSG */

ComPtr<IModelObject> spMsgIdRef;
if (SUCCEEDED(spMessage->GetRawReference(SymbolField, L"message", RawSearchNone, &spMsgIdRef)))
{
    // spMsgIdRef is an ObjectTargetObjectReference.  GetLocation/GetTypeInfo/GetTargetInfo 
    // will return as they would for the value. spMsgIdRef can be passed to Dereference or to 
    // the EE to assign a value, etc...
    ComPtr<IModelObject> spMsgId;
    if (SUCCEEDED(spMsgIdRef->Dereference(&spMsgId)))
    {
        // spMsgId contains the message number.  Unbox with GetIntrinsicValueAs.
    }
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
