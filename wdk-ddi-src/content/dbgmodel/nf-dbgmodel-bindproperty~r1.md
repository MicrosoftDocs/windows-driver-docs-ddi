---
UID: NF:dbgmodel.BindProperty~r1
title: BindProperty function (dbgmodel.h)
description: A binder which converts two lambdas to a read/write property accessor.
ms.assetid: 5bb97697-3462-4fcc-9306-e8741fc6003e
ms.date: 09/28/2018
keywords: ["BindProperty function"]
ms.keywords: BindProperty
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
 - BindProperty
 - dbgmodel/BindProperty
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - BindProperty
---

# BindProperty function


## -description

 A binder which converts two lambdas to a read/write property accessor.  The lambdas must hold reference on outer objects they
reference through a by value capture.

Usage: BindProperty(get_lambda, set_lambda)

## -parameters

### -param getFunctor

A functor of signature (PCWSTR, [IModelObject](nn-dbgmodel-imodelobject.md) *, [IModelObject](nn-dbgmodel-imodelobject.md) **) which will act as the getter for the newly created property accessor.

### -param setFunctor

A functor of signature (PCWSTR, [IModelObject](nn-dbgmodel-imodelobject.md) *, [IModelObject](nn-dbgmodel-imodelobject.md) *) which will act as the setter for the newly created property accessor.

## -returns

This function returns Microsoft::WRL::ComPtr<[IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md)>.

## -remarks

This sample code shows usage.

```cpp
// Define a native type that we wish to project into the data model
struct MyNativeType
{
    std::wstring Name;
    int Id;
    int WriteableValue;
};

// Declare a type factory for the type
class MyNativeTypeFactory : public TypedInstanceModel<MyNativeType>
{
public:
    MyNativeTypeFactory()
    {
        BindReadOnlyProperty(L"Name", &MyNativeType::Name);
        BindReadOnlyProperty(L"Id", &MyNativeType::Id);
        BindProperty(L"WriteableValue", &MyNativeType::WriteableValue);
    }
};

// Create the type factory and make an instance
MyNativeTypeFactory factory;
Object instance = factory.CreateInstance(MyNativeType { L"Foo", 42, 37 });

// There are "Name/Id" read-only properties on instance and a "WriteableValue" property.
```

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

