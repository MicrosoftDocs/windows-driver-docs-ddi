---
UID: NF:dbgmodel.BindReadOnlyProperty
title: BindReadOnlyProperty function
description: A binder which converts an instance methods on a class to a read only property accessor. 
ms.assetid: f63a6f51-8676-4db0-9ac7-dd82414c75f0
ms.date: 09/28/2018
ms.topic: function
ms.keywords: BindReadOnlyProperty
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
-	BindReadOnlyProperty
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# BindReadOnlyProperty function

## -description

A binder which converts an instance methods on a class to a read only property accessor.  The class must be IUnknown derived.
The returned binder will hold reference on the class object.

Usage: BindProperty(this, &MyClass::GetMyProperty, &MyClass::SetMyProperty)

## -parameters

### -param classObject
The instance of a given class to which the newly created read-only property accessor will be bound.

### -param getMethod
A pointer-to-member function pointer of signature (PCWSTR, IModelObject *, IModelObject**) which will act as the getter for the newly created read-only property accessor.

## -returns
This function returns Microsoft::WRL::ComPtr<IModelPropertyAccessor>.
## -remarks

## -see-also
