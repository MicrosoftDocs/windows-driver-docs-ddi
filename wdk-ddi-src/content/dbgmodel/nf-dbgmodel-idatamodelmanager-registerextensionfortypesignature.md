---
UID: NF:dbgmodel.IDataModelManager.RegisterExtensionForTypeSignature
title: IDataModelManager::RegisterExtensionForTypeSignature (dbgmodel.h)
description: The RegisterExtensionForTypeSignature method is similar to the RegisterModelForTypeSignature method with one key difference.
ms.assetid: 13839ae7-45c0-4e31-b7b7-7d0cb6f890b7
ms.date: 07/19/2018
keywords: ["IDataModelManager::RegisterExtensionForTypeSignature"]
ms.keywords: IDataModelManager::RegisterExtensionForTypeSignature, RegisterExtensionForTypeSignature, IDataModelManager.RegisterExtensionForTypeSignature, IDataModelManager::RegisterExtensionForTypeSignature, IDataModelManager.RegisterExtensionForTypeSignature
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelManager::RegisterExtensionForTypeSignature
 - dbgmodel/IDataModelManager::RegisterExtensionForTypeSignature
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager.RegisterExtensionForTypeSignature
---

# IDataModelManager::RegisterExtensionForTypeSignature


## -description

The RegisterExtensionForTypeSignature method is similar to the RegisterModelForTypeSignature method with one key difference. The data model which is passed to this method is not the canonical visualizer for any type and it will not take over the display of the native/language view of that type. The data model which is passed to this method will automatically be added as a parent to any concrete type which matches the supplied type signature. 

Unlike the RegisterModelForTypeSignature method, there is no limit on identical or ambiguous type signatures being registered as extensions to a given type (or set of types). Every extension whose type signature matches a given concrete type instance will cause the data model registered via this method to automatically be attached to newly created objects as parent models. This, in effect, allows an arbitrary number of clients to extend a type (or set of types) with new fields or functionality.

## -parameters

### -param typeSignature

The type signature against which the supplied data model will be registered as an extension. Every native/language object whose concrete type matches this signature will have the given data model attached as a parent model automatically.

### -param dataModel

The data model which will automatically be added as a parent model to every native/language object with a concrete type which matches the supplied type signature.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IDebugHost> spHost;           /* get the debug host */

ComPtr<IModelObject> spDataModel;    /* create a data model (see 
                                        CreateDataModelObject) */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Create a signature to match MyType<*>
    ComPtr<IDebugHostTypeSignature> spTypeSignature;
    if (SUCCEEDED(spSym->CreateTypeSignature(L"MyType<*>", nullptr, &spTypeSignature)))
    {
        // Register the model for std::vector<*>
        if (SUCCEEDED(spManager->RegisterExtensionForTypeSignature(
            spTypeSignature.Get(), 
            spDataModel.Get())
            )
        {
            // Every instance matching MyType<*> will now have spDataModel 
            // attached as the parent.  This data model is considered an "extension"
            // (adding properties).  It will not be counted as a visualizer and 
            // will not "take over" the display of the type
        }
    }
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

