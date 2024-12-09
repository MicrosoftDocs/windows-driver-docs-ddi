---
UID: NF:dbgmodel.IDataModelManager4.RegisterModelForTypeSignature
tech.root: debugger
title: IDataModelManager4::RegisterModelForTypeSignature
ms.date: 12/03/2024
targetos: Windows
description: The RegisterModelForTypeSignature method registers a canonical visualizer for a given type signature.
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
 - IDataModelManager4::RegisterModelForTypeSignature
f1_keywords:
 - IDataModelManager4::RegisterModelForTypeSignature
 - dbgmodel/IDataModelManager4::RegisterModelForTypeSignature
dev_langs:
 - c++
helpviewer_keywords:
 - RegisterModelForTypeSignature
---

## -description

The RegisterModelForTypeSignature method is the primary method that a caller utilizes to register a canonical visualizer for a given type (or set of types). A canonical visualizer is a data model which, in effect, takes over the display of a given type (or set of types). Instead of the native/language view of the type being displayed in any debugger user interface, the view of the type as presented by the registered data model is displayed (along with a means of getting back to the native/language view for a user who desires it). 
The type signature which is passed to this method may match multiple concrete types. If there are multiple matches for a given type instance, only the best match will be returned. One type signature is considered a better match than another if it more specifically refers to a given concrete type. As examples: 

```
A) std::pair<*, *>
B) std::pair<int, *>
C) std::pair<int, float>
```

If the three type signatures above (A, B, and C) are registered and checked against a concrete type: 

```
std::pair<int, float>
```

Alltype signatures match this type instance. The second is a better match than the first because int (the first template argument of B) is a better match than a wildcard (the first template argument of A). Likewise, the third is a better match than the second (it is a total match with no wildcards). 
The RegisterModelForTypeSignature method will not allow duplicate type signatures to be registered. Only one data model can be registered as the canonical visualizer for a given type signature. An attempt to register the same type signature twice will fail. Likewise, the RegisterModelForTypeSignature method will not allow type signatures which can ambiguously match any type instance to be registered. As an example:

```
D) std::pair<int, *>
E) std::pair<*, int>
```

The two type signatures above (D and E) cannot both be registered. For some types, it is clear which signature applies and is best. For instance, 

```
std::pair<int, float>
```

Only matches the first of these (D) since float and int do not match. However, it is completely ambiguous when considering the following: 

```
std::pair<int, int>
```

Either of these signatures is equally good (both have one concrete and one wildcard match). These type signatures are ambiguous. Hence, a call to register the second of them will fail for this reason.

## -parameters

### -param typeSignature

The type signature being registered. Any native/language object of a concrete type which best matches this type signature will have the data model given by the dataModel argument automatically attached.

### -param dataModel

The data model which is to become the canonical visualizer for types matching the given type signature.

## -returns

This method returns HRESULT that indicates success or failure. This method will fail to register identical or ambiguous type signatures.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager4> spManager; /* get the data model manager */
ComPtr<IDebugHost> spHost;           /* get the debug host */

ComPtr<IModelObject> spDataModel;    /* create a data model (see 
                                        CreateDataModelObject) */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Create a signature to match MyType<*>
    ComPtr<IDebugHostTypeSignature> spTypeSignature;
    if (SUCCEEDED(spSym->CreateTypeSignature(L"MyType<*>", 
                                             nullptr, 
                                             &spTypeSignature)))
    {
        // Register the model for std::vector<*>
        if (SUCCEEDED(spManager->RegisterModelForTypeSignature(spTypeSignature.Get(),
                                                               spDataModel.Get()))
        {
            // Every instance matching MyType<*> will now have spDataModel 
            // attached as the parent.  Further, such parent is considered 
            // the canonical visualizer for all types matching MyType<*> since 
            // it was registered via RegisterModelForTypeSignature instead of
            // RegisterExtensionForTypeSignature.
        }
    }
}
```

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)