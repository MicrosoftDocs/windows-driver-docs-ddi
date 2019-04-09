---
UID: NF:dbgmodel.IDataModelNameBinder.BindValue
title: IDataModelNameBinder::BindValue (dbgmodel.h)
description: The BindValue method performs the equivalent of contextObject.name on the given object according to a set of binding rules.
ms.assetid: deaa874d-59a5-4deb-9ea6-426374c5666a
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDataModelNameBinder::BindValue, BindValue, IDataModelNameBinder.BindValue, IDataModelNameBinder::BindValue, IDataModelNameBinder.BindValue
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
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelNameBinder.BindValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelNameBinder::BindValue


## -description

The BindValue method performs the equivalent of contextObject.name on the given object according to a set of binding rules. The result of this binding is a value. As a value, the underlying script provider cannot use the value to perform assignment back to name. 

## -parameters

### -param contextObject
The object to bind a name against.

### -param name
The name to bind in the context of contextObject.

### -param value
The value of name in the context of contextObject is returned. As a value binding, this cannot be used to support assignment back to name.

### -param metadata
Any metadata optionally associated with name is returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelNameBinder interface](nn-dbgmodel-idatamodelnamebinder.md)
