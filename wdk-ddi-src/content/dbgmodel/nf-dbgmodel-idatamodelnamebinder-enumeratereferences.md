---
UID: NF:dbgmodel.IDataModelNameBinder.EnumerateReferences
title: IDataModelNameBinder::EnumerateReferences
author: windows-driver-content
description: The EnumerateReferences method enumerates the set of names and references to them which will bind against the object according to the rules of the BindReference method.
ms.assetid: 7959dcc0-5da5-4952-bb98-d7c41950ba35
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDataModelNameBinder::EnumerateReferences, EnumerateReferences, IDataModelNameBinder.EnumerateReferences, IDataModelNameBinder::EnumerateReferences, IDataModelNameBinder.EnumerateReferences
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
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelNameBinder.EnumerateReferences
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelNameBinder::EnumerateReferences


## -description
The EnumerateReferences method enumerates the set of names and references to them which will bind against the object according to the rules of the BindReference method. Unlike the EnumerateKeys, EnumerateValues, and similar methods on IModelObject which may return multiple names with the same value (for base classes, parent models, and the like), this enumerator will only return the specific set of names which will bind with BindValue and BindReference. Names will never be duplicated. Note that there is a significantly higher cost of enumerating an object via the name binder than calling the IModelObject methods. 

## -parameters

### -param contextObject
The object for which to enumerate all name bindings and references to them.

### -param enumerator
An enumerator which will enumerate every name that would bind according to calls to BindReference and references to them. Note that this enumerator will never duplicate names. It will only return the set of names and values which would come out of explicit calls to BindReference.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelNameBinder interface](nn-dbgmodel-idatamodelnamebinder.md)
