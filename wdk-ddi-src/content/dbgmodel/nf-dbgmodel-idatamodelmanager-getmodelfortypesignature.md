---
UID: NF:dbgmodel.IDataModelManager.GetModelForTypeSignature
title: IDataModelManager::GetModelForTypeSignature (dbgmodel.h)
description: The GetModelForTypeSignature method returns the data model that was registered against a particular type signature via a prior call to the RegisterModelForTypeSignature method.
ms.assetid: 4e1d21b1-2a56-444a-b727-7e7e7e9ed871
ms.date: 07/19/2018
keywords: ["IDataModelManager::GetModelForTypeSignature"]
ms.keywords: IDataModelManager::GetModelForTypeSignature, GetModelForTypeSignature, IDataModelManager.GetModelForTypeSignature, IDataModelManager::GetModelForTypeSignature, IDataModelManager.GetModelForTypeSignature
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
 - IDataModelManager::GetModelForTypeSignature
 - dbgmodel/IDataModelManager::GetModelForTypeSignature
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager.GetModelForTypeSignature
---

# IDataModelManager::GetModelForTypeSignature


## -description

The GetModelForTypeSignature method returns the data model that was registered against a particular type signature via a prior call to the RegisterModelForTypeSignature method. The data model returned from this method is considered the canonical visualizer for any type which matches the passed type signature. As a canonical visualizer, that data model takes over the display of the type. Display engines will, by default, hide native/language constructs of the object in favor of the view of the object presented by the data model.

## -parameters

### -param typeSignature

A type signature for which dataModel will be registered as the canonical visualizer. Any object created with a native/language type which matches the signature (and for which there is no better matching type signature) will automatically have the returned data model attached as a parent.

### -param dataModel

The data model which is registered as the canonical visualizer for all type instances which match the given type signature (and for which there is no better matching type signature.

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
        if (SUCCEEDED(spManager->RegisterModelForTypeSignature(spTypeSignature.Get(),
                                                               spDataModel.Get()))
        {
            // Every instance matching MyType<*> will now have spDataModel 
            // attached as the parent.  Further, such parent is considered 
            // the canonical visualizer for all types matching MyType<*> since it 
            // was registered via RegisterModelForTypeSignature instead of
            // RegisterExtensionForTypeSignature.
            //
            // Demonstrate that we can find the canonical visualizer under 
            // this registration.
            ComPtr<IModelObject> spCanonicalVisualizerModel;
            if (SUCCEEDED(spManager->GetModelForTypeSignature(
                spTypeSignature.Get(), 
                &spCanonicalVisualizerModel)))
            {
                // spCanonicalVisualizerModel is the same as spDataModel since 
                // it was registered as such.
            }
        }
    }
}
```

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

