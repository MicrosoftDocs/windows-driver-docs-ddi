---
UID: NF:dbgmodel.IDataModelManager3.UnregisterModelForTypeSignature
tech.root: debugger
title: IDataModelManager3::UnregisterModelForTypeSignature
ms.date: 11/20/2024
targetos: Windows
description: The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager3::UnregisterModelForTypeSignature
f1_keywords:
 - IDataModelManager3::UnregisterModelForTypeSignature
 - dbgmodel/IDataModelManager3::UnregisterModelForTypeSignature
dev_langs:
 - c++
helpviewer_keywords:
 - UnregisterModelForTypeSignature
---

## -description

The UnregisterModelForTypeSignature method undoes a prior call to the RegisterModelForTypeSignature method. This method can either remove a given data model as the canonical visualizer for types matching a particular type signature or it can remove a given data model as the canonical visualizer for every type signature under which that data model is registered.

## -parameters

### -param dataModel

The data model to be unregistered as the canonical visualizer for one or more type signatures. If the typeSignature argument is nullptr, this data model will be unregistered from all type signatures it was registered against; otherwise, it will only be unregistered against the particular type signature indicated.

### -param typeSignature

The type signature against which the data model given by the dataModel argument will be unregistered. This argument is optional and hence, nullptr can be passed. If nullptr is passed, the data model given by the dataModel argument will be unregistered from all type signatures it was registered against.

## -returns

This method returns HRESULT that indicates success or failure.


## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager3> spManager;             /* get the data model manager */
ComPtr<IDebugHostTypeSignature> spTypeSignature; /* get a type signature (see
                                                    RegisterModelForTypeSignature) */
ComPtr<IModelObject> spDataModelObject;          /* get a data model object (see
                                                    CreateDataModelObject) */

if (SUCCEEDED(spManager->UnregisterModelForTypeSignature(spDataModelObject.Get(),
                                                         spTypeSignature.Get())))
{
    // spDataModelObject is no longer registered as the canonical visualizer
    // for types matching the signature.  Note that if the second argument were 
    // passed as 'nullptr', spDataModelObject would no longer be registered 
    // as the canonical visualizer for *ANY* types.
}
```

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)