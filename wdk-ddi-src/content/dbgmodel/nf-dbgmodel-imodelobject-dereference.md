---
UID: NF:dbgmodel.IModelObject.Dereference
title: IModelObject::Dereference (dbgmodel.h)
description: The Dereference method dereferences an object.
ms.assetid: c6eb77c2-b901-40c5-b558-f48d33a174de
ms.date: 07/20/2018
ms.topic: method
ms.keywords: IModelObject::Dereference, Dereference, IModelObject.Dereference, IModelObject::Dereference, IModelObject.Dereference
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
-	IModelObject.Dereference
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::Dereference


## -description

The Dereference method dereferences an object. This method can be used to dereference a data model based reference (ObjectTargetObjectReference, ObjectKeyReference) or a native language reference (a pointer or a language reference). It is important to note that this method removes a single level of reference semantics on the object. It is entirely possible to, for instance, have a data model reference to a language reference. In such a case, calling the Dereference method the first time would remove the data model reference and leave the language reference. Calling Dereference on that resulting object would subsequently remove the language reference and return the native value under that reference. 

## -parameters

### -param object
The result of dereferencing the object will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spPointer; /* get a pointer */

ComPtr<IModelObject> spPointedTo;
if (SUCCEEDED(spPointer->Dereference(&spPointedTo)))
{
    // spPointedTo is a dereference of the pointer (or other applicable type of reference)
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
