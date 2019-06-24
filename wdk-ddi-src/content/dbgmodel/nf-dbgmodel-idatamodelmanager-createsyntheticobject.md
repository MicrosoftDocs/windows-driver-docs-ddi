---
UID: NF:dbgmodel.IDataModelManager.CreateSyntheticObject
title: IDataModelManager::CreateSyntheticObject (dbgmodel.h)
description: The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts.
ms.assetid: 28363265-b92e-4dc2-92b8-47a2840c762f
ms.date: 07/17/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateSyntheticObject, CreateSyntheticObject, IDataModelManager.CreateSyntheticObject, IDataModelManager::CreateSyntheticObject, IDataModelManager.CreateSyntheticObject
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
- IDataModelManager.CreateSyntheticObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateSyntheticObject


## -description

The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts. At the time of creation, there are no keys nor concepts on the object. It is a clean slate for the caller to utilize. 

## -parameters

### -param context
The debug host context which will be associated with the newly created synthetic object. Not every object requires a context. If the object refers to things such as processes, threads, or memory in the address space of the host, it may need one (unless it encapsulates other objects which contain such).

### -param object
The newly created object will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IModelObject> spNewObject;
if (SUCCEEDED(spManager->CreateSyntheticObject(nullptr, &spNewObject)))
{
     // spNewObject is an empty object (a dictionary of key/value/metadata tuples)
}

```
## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
