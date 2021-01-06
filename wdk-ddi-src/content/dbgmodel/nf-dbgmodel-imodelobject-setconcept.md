---
UID: NF:dbgmodel.IModelObject.SetConcept
title: IModelObject::SetConcept (dbgmodel.h)
description: The SetConcept method will place a specified concept on the object instance specified by the this pointer.
ms.date: 06/10/2019
keywords: ["IModelObject::SetConcept"]
ms.keywords: IModelObject::SetConcept, SetConcept, IModelObject.SetConcept, IModelObject::SetConcept, IModelObject.SetConcept
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
 - IModelObject::SetConcept
 - dbgmodel/IModelObject::SetConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject.SetConcept
---

# IModelObject::SetConcept


## -description

The SetConcept method will place a specified concept on the object instance specified by the this pointer. If a parent model attached to the object instance specified by this also supports the concept, the implementation in the instance will override that in the parent model.

For the set of concepts (interfaces) that are supported by the data model, see [Debugger Data Model C++ Concepts](/windows-hardware/drivers/debugger/data-model-cpp-concepts).

For information on the [IKeyStore](nn-dbgmodel-ikeystore.md) interface, see [IKeyStore interface](nn-dbgmodel-ikeystore.md).

## -parameters

### -param conceptId

The unique identifier of the concept being assigned. This is also the IID of the core interface of the concept.

### -param conceptInterface

The concept interface being assigned (defined by conceptId).

### -param conceptMetadata

Optional metadata to be associated with this concept.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object: say a new one from CreateSyntheticObject */

// Implement IStringDisplayableConcept for the object.  Return a static "Hello World" string.
class MyStringConversion :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<Microsoft::WRL::RuntimeClassType::ClassicCom>,
        IStringDisplayableConcept
        >
{
public:

    IFACEMETHOD(ToDisplayString)(_In_ IModelObject * /*pContextObject*/, 
                                 _In_opt_ IKeyStore * /*pMetadata*/, 
                                 _Out_ BSTR *pDisplayString)
    {
        *pDisplayString = SysAllocString(L"Hello World");
        return *pDisplayString == nullptr ? E_OUTOFMEMORY : S_OK;
    }
};

// Add the implementation as a concept
ComPtr<MyStringConversion> spStringConverter = Microsoft::WRL::Make<MyStringConversion>();
if (spStringConverter != nullptr)
{
    if (SUCCEEDED(spObject->SetConcept(__uuidof(IStringDisplayableConcept),
                                       static_cast<IStringDisplayableConcept *>
                                           (spStringConverter.Get()), nullptr)))
    {
        // The new object can be converted to a string! 
    }
}
```

## -see-also

[Debugger Data Model C++ Concepts](/windows-hardware/drivers/debugger/data-model-cpp-concepts)

[IKeyStore interface](nn-dbgmodel-ikeystore.md)

[IModelObject interface](nn-dbgmodel-imodelobject.md)
