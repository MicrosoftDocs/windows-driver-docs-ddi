---
UID: NF:dbgmodel.BindReadOnlyProperty~r1
title: BindReadOnlyProperty function (dbgmodel.h)
description: TA binder which converts one instance method on a class to a read-only property accessor.
ms.assetid: c59ee365-d2da-4352-8311-a4a1d27fabdc
ms.date: 09/28/2018
keywords: ["BindReadOnlyProperty function"]
f1_keywords:
 - "dbgmodel/BindReadOnlyProperty"
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
- apiref
api_type: 
- HeaderDef
api_location: 
- dbgmodel.h
api_name: 
- BindReadOnlyProperty
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# BindReadOnlyProperty function


## -description

A binder which converts one instance method on a class to a read-only property accessor.  The class must be IUnknown derived.

The returned binder will hold reference on the class object.

A binder which converts one lambda to a read-only property accessor.  The lambda must hold reference on outer objects through  a by value capture.

Usage: BindProperty(get_lambda)

## -parameters

### -param getFunctor
A functor of signature (PCWSTR, [IModelObject](nn-dbgmodel-imodelobject.md) *, [IModelObject](nn-dbgmodel-imodelobject.md) **) which will act as the getter for the newly created read-only property accessor.


## -returns
This function returns Microsoft::WRL::ComPtr<[IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md)>.
## -remarks

## -see-also
