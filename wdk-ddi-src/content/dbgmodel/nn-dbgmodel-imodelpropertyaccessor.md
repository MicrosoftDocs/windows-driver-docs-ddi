---
UID: NN:dbgmodel.IModelPropertyAccessor
title: IModelPropertyAccessor (dbgmodel.h)
description: The data model representation of a  property accessor (get/set).
ms.assetid: 719a97dc-26eb-4b5a-9f68-50c4a9069bae
ms.date: 07/16/2018
ms.topic: interface
f1_keywords:
 - "dbgmodel/IModelPropertyAccessor"
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
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
- COM
api_location: 
- dbgmodel.h
api_name: 
- IModelPropertyAccessor
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelPropertyAccessor interface

## -description

The data model representation of a  property accessor (get/set).


## -inheritance
IModelPropertyAccessor interits from IUnknown. 
## -remarks

A property accessor in the data model is an implementation of the IModelPropertyAccessor interface which is boxed into an [IModelObject](nn-dbgmodel-imodelobject.md). The model object will return a kind of ObjectPropertyAccessor when queried and the intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for IModelPropertyAccessor. In process, it is guaranteed to be statically castable to IModelPropertyAccessor. 

A property accessor is an indirect way to get a method call for getting and setting a key value in the data model. If a given key's value is a property accessor, the GetKeyValue and SetKeyValue methods will automatically notice this and call the property accessor's underlying GetValue or SetValue methods as appropriate. 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
