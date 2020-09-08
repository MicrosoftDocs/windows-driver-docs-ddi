---
UID: NF:dbgmodel.BindProperty
title: BindProperty function (dbgmodel.h)
description: A binder which converts two instance methods on a class to a read/write property accessor.
ms.assetid: 9d2e671b-af82-49fb-ba13-8f780e931929
ms.date: 06/11/2019
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

# BindProperty function (dbgmodel.h)


## -description

 A binder which converts two instance methods on a class to a read/write property accessor.  The class must be IUnknown derived.
 The returned binder will hold reference on the class object.

 Usage: BindProperty(this, &MyClass::GetMyProperty, &MyClass::SetMyProperty)

## -parameters

### -param classObject

The instance of a given class to which the newly created property accessor will be bound.

### -param getMethod

A pointer-to-member function pointer of signature (PCWSTR, [IModelObject](nn-dbgmodel-imodelobject.md) *, [IModelObject](nn-dbgmodel-imodelobject.md)**) which will act as the getter for the newly created property accessor.

### -param setMethod

A pointer-to-member function of signature (PCWSTR, [IModelObject](nn-dbgmodel-imodelobject.md) *, [IModelObject](nn-dbgmodel-imodelobject.md) *) which will act as the setter for the newly created property accessor.

## -returns

This function returns Microsoft::WRL::ComPtr<[IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md)>.

## -remarks

This sample code shows usage of the BindProperty function.

> [!NOTE]
>The code sample uses the recommended DbgModelClientEx.h library header available from GitHub. For more information, see [Using the DbgModelClientEx Library](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview#-using-the-dbgmodelclientex-library).
>
> To see how the DbgModelClientEx library are used, for example, specifying the Debugger::DataModel namespaces, review the Data Model HelloWorld C++ sample:
> https://github.com/microsoft/WinDbg-Samples/tree/master/DataModelHelloWorld/Cpp


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

