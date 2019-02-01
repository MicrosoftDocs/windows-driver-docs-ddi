---
UID: NF:dbgmodel.IDataModelManager2.GetModelForTypeSignature
title: IDataModelManager2::GetModelForTypeSignature (dbgmodel.h)
description: The GetModelForTypeSignature method returns the data model that was registered against a particular type signature via a prior call to the RegisterModelForTypeSignature method.
ms.assetid: 5985c645-52b4-4a40-a5c9-6f7495eb38ec
ms.date: 09/11/2018
ms.topic: method
ms.keywords: IDataModelManager2::GetModelForTypeSignature, GetModelForTypeSignature, IDataModelManager2.GetModelForTypeSignature, IDataModelManager2::GetModelForTypeSignature, IDataModelManager2.GetModelForTypeSignature
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
-	IDataModelManager2.GetModelForTypeSignature
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager2::GetModelForTypeSignature


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

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
