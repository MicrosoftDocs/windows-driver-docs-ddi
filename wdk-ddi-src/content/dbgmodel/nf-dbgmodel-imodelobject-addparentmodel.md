---
UID: NF:dbgmodel.IModelObject.AddParentModel
title: IModelObject::AddParentModel
author: windows-driver-content
description: TBD
ms.assetid: 9e84b804-6d72-41e1-a548-edf726c669fc
ms.author: windowsdriverdev
ms.date: 08/08/2018
ms.topic: method
ms.keywords: IModelObject::AddParentModel, AddParentModel, IModelObject.AddParentModel, IModelObject::AddParentModel, IModelObject.AddParentModel
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
-	IModelObject.AddParentModel
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::AddParentModel


## -description

The AddParentModel method adds a new parent model to the given object. Such a model may be added at the end of the search chain (the override argument is specified as false) or at the front of the search chain (the override argument is specified as true). In addition, each parent model may optionally adjust the context (the semantic this pointer) for any property or concept on the given parent (or anyone in its parent hierarchy). Context adjustment is seldom used but allows for some powerful concepts like object embedding, constructing namespaces, etc... 

When a parent model has a context adjustment, the core data model will perform this adjustment automatically on behalf of the caller. In effect, for an object instance with a parent model parent having a context adjustor to newContext, a call of 

```cpp
instance->GetKeyValue("someKey", &pValue, nullptr);
```

will end up changing the context/this pointer from instance to newContext before calling someKey's GetValue method since the access to someKey passed through the context adjustor. 

Any IModelObject which is added as a parent model to another object must individually support the IDataModelConcept concept. Failure to implement this concept may result in the AddParentModel method call failing. 

## -parameters

### -param model
An IModelObject which will be added to the parent model chain of the given object. This IModelObject must individually support the IDataModelConcept concept.

### -param contextObject
If the data model has a context adjustment associated with it, the adjusted context (or a property accessor which returns the adjusted context) may be passed here.

### -param override
An indication of whether the parent model specified by the model argument is placed at the front or the end of the linear chain of parent models. A value of false (normally supplied) indicates the end of the chain. A value of true indicates the front of the chain.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

** Code Sample**

```cpp


ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IModelObject> spObject;       /* get an object */

// A data model *MUST* implement IDataModelConcept.  Create an implementation of this and a string conversion.
class MyDataModel :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<Microsoft::WRL::RuntimeClassType::ClassicCom>,
        IDataModelConcept,
        IStringDisplayableConcept
        >
{
public:
 
    IFACEMETHOD(InitializeObject)(_In_ IModelObject * /*pModelObject*/, 
                                  _In_opt_ IDebugHostTypeSignature * /*pMatchingSignature*/,
                                  _In_opt_ IDebugHostSymbolEnumerator * /*pWildcardMatches*/)
    {
        return S_OK;
    }

    IFACEMETHOD(GetName)(_Out_ BSTR *pModelName)
    { 
        return E_NOTIMPL;
    }

    IFACEMETHOD(ToDisplayString)(_In_ IModelObject * /*pContextObject*/, 
                                 _In_opt_ IKeyStore * /*pMetadata */, 
                                 _Out_ BSTR *pDisplayString)
    {
        *pDisplayString = SysAllocString(L"Hello World");
        return *pDisplayString == nullptr ? E_OUTOFMEMORY : S_OK;
    }
};

// Create the data model, an object for it, set concepts, and add it as a parent to spObject.
ComPtr<MyDataModel> spDataModel = Microsoft::WRL::Make<MyDataModel>();
ComPtr<IModelObject> spDataModelObject;
if (spDataModel != nullptr &&
    SUCCEEDED(spManager->CreateDataModelObject(spDataModel.Get(), &spDataModelObject)) &&
    SUCCEEDED(spDataModelObject->SetConcept(__uuidof(IStringDisplayableConcept),
                                            static_cast<IStringDisplayableConcept *>
                                                (spDataModel.Get()), 
                                            nullptr)))
{
    if (SUCCEEDED(spObject->AddParentModel(spDataModelObject.Get(), nullptr, false)))
    {
        // spObject has been *EXTENDED* to have a display string.  It has a parent model 
        // which has that concept.  That extension (and whatever else was added 
        // on spDataModelObject) can be removed with a single RemoveParentModel call.
    }
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
