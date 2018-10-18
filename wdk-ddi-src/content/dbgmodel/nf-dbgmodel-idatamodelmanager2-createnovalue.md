---
UID: NF:dbgmodel.IDataModelManager2.CreateNoValue
title: IDataModelManager2::CreateNoValue
author: windows-driver-content
description: The CreateNoValue method creates a "no value" object, boxes it into an IModelObject, and returns it.
ms.assetid: 2533e73e-a094-4e55-8c33-b52384037932
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelManager2::CreateNoValue, CreateNoValue, IDataModelManager2.CreateNoValue, IDataModelManager2::CreateNoValue, IDataModelManager2.CreateNoValue
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
-	IDataModelManager2.CreateNoValue
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelManager2::CreateNoValue


## -description

The CreateNoValue method creates a "no value" object, boxes it into an IModelObject, and returns it. The returned model object has a kind of ObjectNoValue. 

A "no value" object has several semantic meanings: 

- (Depending on language), it can be considered the semantic equivalent of void, null, or undefined
- Any property accessor's GetValue method which returns success and a resulting "no value" object is indicating that the particular property has no value for the given instance and should be treated as if the property did not exist for that particular instance.
- Data model methods which do not semantically have a return value use this as a sentinel to indicate such (as a method must return a valid IModelObject).


## -parameters

### -param object
The newly created/boxed "no value" object will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

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

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
