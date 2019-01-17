---
UID: NF:dbgmodel.IModelObject.GetRawValue
title: IModelObject::GetRawValue
description: The GetRawValue method finds a native construct within the given object. Such a construct may be a field, a base class, a field in a base class, a member function, etc.
ms.assetid: 2750984d-5639-40ce-aa42-c8624f9775ca
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetRawValue, GetRawValue, IModelObject.GetRawValue, IModelObject::GetRawValue, IModelObject.GetRawValue
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
-	IModelObject.GetRawValue
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetRawValue


## -description

The GetRawValue method finds a native construct within the given object. Such a construct may be a field, a base class, a field in a base class, a member function, etc. 

## -parameters

### -param kind
Indicates the kind of native symbol to fetch (e.g.: a base class or a data member)

### -param name
The name of the native construct to fetch.

### -param searchFlags
An optional set of flags specifying the behavior of the search for the native construct.

### -param object
An IModelObject representing the fetched native construct will be returned here. Note that in some circumstances, extended error information may be returned in this argument even if the HRESULT indicates failure. 

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

The searchFlags argument is a set of bit flags specified by the RawSearchFlags enumeration. This enumeration presently defines the following values: 

**RawSearchNone** - No special semantics to the search. Do the default search action for the target language being debugged.

**RawSearchNoBases** - Indicates that the search should not recurse to base children (e.g.: base classes). Only names/types which are in the object itself should be returned.



**Code Sample**

```cpp
ComPtr<IModelObject> spMessage; /* get a tagMSG */

// Get the 'message' field of the tagMSG structure:
ComPtr<IModelObject> spMsgId;
if (SUCCEEDED(spMessage->GetRawValue(SymbolField, L"message", RawSearchNone, &spMsgId)))
{
    // spMsgId contains the boxed form of the 'message' field of the tagMSG object.
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
