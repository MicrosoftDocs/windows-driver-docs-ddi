---
UID: NF:dbgmodel.IDataModelManager.CreateDataModelObject
title: IDataModelManager::CreateDataModelObject
author: windows-driver-content
description: TBD
ms.assetid: f1c18662-fe30-45ad-b71d-6776f64d3dc9
ms.author: windowsdriverdev
ms.date:  07/17/2018
ms.topic: method
ms.keywords: IDataModelManager::CreateDataModelObject, CreateDataModelObject, IDataModelManager.CreateDataModelObject, IDataModelManager::CreateDataModelObject, IDataModelManager.CreateDataModelObject
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
-	IDataModelManager.CreateDataModelObject
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelManager::CreateDataModelObject


## -description

The CreateDataModelObject method is a simple helper wrapper to create objects which are data models -- that is objects which are going to be attached as parent models to other objects. All such objects must support the data model concept via IDataModelConcept. This method creates a new blank synthetic object with no explicit context and adds the inpassed IDataModelConcept as the newly created object's implementation of the data model concept. This can similarly be accomplished with calls to CreateSyntheticObject and SetConcept. 

## -parameters

### -param dataModel
The implementation of IDataModelConcept which will be automatically added to the newly created object as its implementation of the data model concept.


### -param object
The newly created synthetic object (with the data model concept set) will be returned here.


## -returns
This method returns HRESULT.

## -remarks
**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

// We need some IDataModelConcept implementation.  Provide a 
// minimal one for example purposes.
class MyDataModel :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IDataModelConcept
        >
{
public:

    IFACEMETHOD(InitializeObject)(
        _In_ IModelObject * /*pContextObject*/, 
        _In_opt_ IDebugHostTypeSignature * /*pMatchingSignature*/, 
        _In_opt_ IDebugHostSymbolEnumerator * /*pWildcardMatches*/
        )
    {
        return S_OK;
    }

    IFACEMETHOD(GetName)(_Out_ BSTR *pModelName)
    {
        *pModelName = nullptr;
        return E_NOTIMPL;
    }
};

ComPtr<MyDataModel> spMyModel = Microsoft::WRL::Make<MyDataModel>();
if (spMyModel != nullptr)
{
    ComPtr<IModelObject> spDataModelObject;
    if (SUCCEEDED(spManager->CreateDataModelObject(spMyModel.Get(),
                                                   &spDataModelObject)))
    {
        // spDataModelObject is now a data model object and can be attached
        // as a parent to any other object via AddParentModel().
    }
}

```


## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
