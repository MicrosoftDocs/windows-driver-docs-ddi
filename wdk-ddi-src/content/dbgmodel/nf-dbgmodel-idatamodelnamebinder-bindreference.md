---
UID: NF:dbgmodel.IDataModelNameBinder.BindReference
title: IDataModelNameBinder::BindReference (dbgmodel.h)
description: The BindReference method is similar to BindValue in that it also performs the equivalent of contextObject.name on the given object according to a set of binding rules. 
ms.assetid: e1930647-984f-4aec-a07b-8c3dac9e9ae1
ms.date: 09/12/2018
keywords: ["IDataModelNameBinder::BindReference"]
f1_keywords:
 - "dbgmodel/IDataModelNameBinder.BindReference"
 - "IDataModelNameBinder.BindReference"
ms.keywords: IDataModelNameBinder::BindReference, BindReference, IDataModelNameBinder.BindReference, IDataModelNameBinder::BindReference, IDataModelNameBinder.BindReference
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
- IDataModelNameBinder.BindReference
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelNameBinder::BindReference


## -description

The BindReference method is similar to BindValue in that it also performs the equivalent of contextObject.name on the given object according to a set of binding rules. The result of the binding from this method is, however, a reference instead of a value. As a reference, the script provider can utilize the reference to perform assignment back to name. 

## -parameters

### -param contextObject
The object to bind a name against.

### -param name
The name to bind in the context of contextObject.

### -param reference
A reference to name in the context of contextObject is returned. As a reference binding, this can be used to support assignment back to name.

### -param metadata
Any metadata optionally associated with name is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelNameBinder interface](nn-dbgmodel-idatamodelnamebinder.md)
