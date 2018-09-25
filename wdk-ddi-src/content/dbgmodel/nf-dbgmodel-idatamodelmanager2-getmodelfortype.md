---
UID: NF:dbgmodel.IDataModelManager2.GetModelForType
title: IDataModelManager2::GetModelForType
author: windows-driver-content
description: TBD
ms.assetid: feaec7e1-6dda-43c6-95c9-7ccbca6472fb
ms.author: windowsdriverdev
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelManager2::GetModelForType, GetModelForType, IDataModelManager2.GetModelForType, IDataModelManager2::GetModelForType, IDataModelManager2.GetModelForType
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
-	IDataModelManager2.GetModelForType
product: Windows
targetos: Windows


---

# IDataModelManager2::GetModelForType


## -description

The GetModelForType method returns the data model which is the canonical visualizer for a given type instance. In effect, this method finds the best matching type signature which was registered with a prior call to the RegisterModelForTypeSignature method and returns the associated data model. 

## -parameters

### -param type
The concrete type instance for which to find the best matching canonical visualizer registered via a prior call to the RegisterModelForTypeSignature method.

### -param dataModel
The data model which is the canonical visualizer for the given type instance as determined by the best matching type signature registered via a prior call to RegisterModelForTypeSignature will be returned here. This data model will automatically be attached to any native/language object created with the type specified by the type argument.

### -param typeSignature
The type signature whose match against type caused us to return the data model registered from a prior call to RegisterModelForTypeSignature with the returned type signature. 

### -param wildcardMatches
If there are wildcards in the signature returned in the typeSignature argument, an enumerator of all matches between the wildcards and the concrete type instance given in the type argument is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IDebugHostModule> spModule;   /* get a module */

// Find the type of "MyType<int>" within the module
ComPtr<IDebugHostType> spType;
if (SUCCEEDED(spModule->FindTypeByName(L"MyType<int>", &spType)))
{
    // Find the canonical visualizer which would be applied to MyType<int>
    ComPtr<IModelObject> spDataModel;
    ComPtr<IDebugHostTypeSignature> spSignature;
    ComPtr<IDebugHostSymbolEnumerator> spWildcardMatches;

    if (SUCCEEDED(spManager->GetModelForType(spType.Get(), 
                                             &spDataModel, 
                                             &spSignature, 
                                             &spWildcardMatches)))
    {
        // There is a visualizer which matched.
        // spDataModel is the data model object which was registered as 
        //     the canonical visualizer (RegisterModelForTypeSignature)
        // spSignature is the signature which that data model was registered 
        //     against (e.g.: created for MyType<*> via
        //     CreateTypeSignature/RegisterModelForTypeSignature)
        // spWildcardMatches is an enumerator of the wildcard matches between 
        //     the specific type spType and the signature spSignature (here 
        //     int matched *, so there will be one item -- the type 'int' in
        //     the enumerator)
    }
```
## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)