---
UID: NF:dbgmodel.BindProperty~r1
title: BindProperty function
author: windows-driver-content
description: TBD
ms.assetid: 5bb97697-3462-4fcc-9306-e8741fc6003e
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
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
topic_type: 
-	apiref
api_type: 
-	
api_location: 
-	
api_name: 
-	BindProperty
product: Windows
targetos: Windows


---

# BindProperty function


## -description

 A binder which converts two lambdas to a read/write property accessor.  The lambdas must hold reference on outer objects they
reference through a by value capture.


## -parameters

### -param getFunctor
TBD

### -param setFunctor
TBD

### -param 
TBD

## -returns
This function returns Microsoft::WRL::ComPtr<IModelPropertyAccessor>.

## -remarks

This sample code shows usage.

```
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

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)