---
UID: NF:dbgmodel.IDataModelManager3.CreateNoValue
tech.root: debugger
title: IDataModelManager3::CreateNoValue
ms.date: 11/20/2024
targetos: Windows
description: The CreateNoValue method creates a "no value" object, boxes it into an IModelObject, and returns it.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager3::CreateNoValue
f1_keywords:
 - IDataModelManager3::CreateNoValue
 - dbgmodel/IDataModelManager3::CreateNoValue
dev_langs:
 - c++
helpviewer_keywords:
 - CreateNoValue
---

## -description

The CreateNoValue method creates a "no value" object, boxes it into an [IModelObject](nn-dbgmodel-imodelobject.md), and returns it. The returned model object has a kind of ObjectNoValue. 

A "no value" object has several semantic meanings: 

- (Depending on language), it can be considered the semantic equivalent of void, null, or undefined
- Any property accessor's GetValue method which returns success and a resulting "no value" object is indicating that the particular property has no value for the given instance and should be treated as if the property did not exist for that particular instance.
- Data model methods which do not semantically have a return value use this as a sentinel to indicate such (as a method must return a valid [IModelObject](nn-dbgmodel-imodelobject.md)).

## -parameters

### -param object

The newly created/boxed "no value" object will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager3> spManager; /* get the data model manager */

ComPtr<IModelObject> spNoValue;
if (SUCCEEDED(spManager->CreateNoValue(&spNoValue)))
{
    // spNoValue contains a "no value" object.  This can be 
    // returned from IModelMethod::Call (an indication of no return value).  
    // It can be returned from a property accessor to indicate that the 
    // property has "no value" for the given instance.
}
```

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
