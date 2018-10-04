---
UID: NF:dbgmodel.IModelObject.GetConcept
title: IModelObject::GetConcept
author: windows-driver-content
description: The GetConcept method will search for a concept on the object (or its parent model chain) and return an interface pointer to the concept interface.
ms.assetid: eab33f82-a73f-46d8-9c12-d06c28869290
ms.author: windowsdriverdev
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetConcept, GetConcept, IModelObject.GetConcept, IModelObject::GetConcept, IModelObject.GetConcept
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
-	IModelObject.GetConcept
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::GetConcept


## -description

The GetConcept method will search for a concept on the object (or its parent model chain) and return an interface pointer to the concept interface. The behavior and methods on a concept interface are specific to each concept. It is important to note, however, that many of the concept interfaces require the caller to explicitly pass the context object (or what one might traditionally call the this pointer). It is important to ensure that the correct context object is passed to every concept interface.

## -parameters

### -param conceptId
The unique identifier of the concept being queried. This is also the IID of the core interface of the concept.


### -param conceptInterface
The interface defined by conceptId will be returned in this argument.

### -param conceptMetadata
The metadata store associated with this concept will be optionally returned in this argument

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get some object */

// Get the string conversion of spObject through the string displayable concept:
ComPtr<IStringDisplayableConcept> spStringDisplayable;
if (SUCCEEDED(spObject->GetConcept(__uuidof(IStringDisplayableConcept), 
                                   &spStringDisplayable, 
                                   nullptr)))
{
    BSTR stringConversion;
    if (SUCCEEDED(spStringDisplayable->ToDisplayString(spObject.Get(), 
                                                       nullptr, 
                                                       &stringConversion)))
    {
        // stringConversion contains the display string conversion for the object
        SysFreeString(stringConversion);
    }
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
