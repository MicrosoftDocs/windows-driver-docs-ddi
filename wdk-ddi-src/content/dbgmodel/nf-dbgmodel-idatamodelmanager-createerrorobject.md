---
UID: NF:dbgmodel.IDataModelManager.CreateErrorObject
title: IDataModelManager::CreateErrorObject
author: windows-driver-content
description: The CreateErrorObject method creates an "error object". The data model does not have the notion of exceptions and exception flow. 
ms.assetid: a57fdf58-d8f5-4044-be00-5225670ec3ac
ms.date:  07/17/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateErrorObject, CreateErrorObject, IDataModelManager.CreateErrorObject, IDataModelManager::CreateErrorObject, IDataModelManager.CreateErrorObject
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
-	IDataModelManager.CreateErrorObject
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelManager::CreateErrorObject


## -description

The CreateErrorObject method creates an "error object". The data model does not have the notion of exceptions and exception flow. Failure comes out of a property/method in two ways: 

- A single failing HRESULT with no extended error information. Either there is no more information which can be given for the error or the error itself is self-explanatory from the returned HRESULT.

- A single failing HRESULT coupled with extended error information. The extended error information is an error object returned in the output argument of the property/method.


## -parameters

### -param hrError
The error code for which the extended error information is being created. If a given function is the entity creating an error object for a failure, this code must match the failing HRESULT returned by the function.

### -param pwszMessage
An optional message giving a deeper indication of what failed and why. This message will be the display string conversion of the created error object.

### -param object
The newly constructed/boxed error object will be returned here.

## -returns
This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IModelObject> spError;
if (SUCCEEDED(spManager->CreateErrorObject(
    E_INVALIDARG, 
    L"Calls to the Sum() method must pass at least one argument", 
    &spError)))
{
    // You can pass this back in places where you see 
    // _COM_Errorptr_ annotated.  Methods, for instance, may return 
    // E_INVALIDARG and an error object to channel out additional information.
    // Property accessor GetValue implementations can also do this.  
    // Indexers can do this.
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
