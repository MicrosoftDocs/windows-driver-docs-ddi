---
UID: NF:dbgmodel.IDataModelManager.CreateNoValue
title: IDataModelManager::CreateNoValue (dbgmodel.h)
description: The CreateNoValue method creates a "no value" object, boxes it into an IModelObject, and returns it. The returned model object has a kind of ObjectNoValue. 
ms.assetid: efc55ed1-d0c7-4da7-86a8-9ebc88dd6d33
ms.date: 07/20/2018
keywords: ["IDataModelManager::CreateNoValue"]
f1_keywords:
 - "dbgmodel/IDataModelManager.CreateNoValue"
ms.keywords: IDataModelManager::CreateNoValue, CreateNoValue, IDataModelManager.CreateNoValue, IDataModelManager::CreateNoValue, IDataModelManager.CreateNoValue
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
- IDataModelManager.CreateNoValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateNoValue


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
This method returns HRESULT that indicates success or failure.

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

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
