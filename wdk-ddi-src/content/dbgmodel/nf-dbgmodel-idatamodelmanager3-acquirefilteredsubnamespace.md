---
UID: NF:dbgmodel.IDataModelManager3.AcquireFilteredSubNamespace
tech.root: debugger
title: IDataModelManager3::AcquireFilteredSubNamespace method (dbgmodel.h)
ms.date: 11/20/2024
targetos: Windows
description: The AcquireFilteredSubNamespace method acquires a sub-namespace of the data model manager that is filtered by a specified filter.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager3::AcquireFilteredSubNamespace
f1_keywords:
 - IDataModelManager3::AcquireFilteredSubNamespace
 - dbgmodel/IDataModelManager3::AcquireFilteredSubNamespace
dev_langs:
 - c++
helpviewer_keywords:
 - AcquireFilteredSubNamespace
---

## -description

A convenience method for acquiring (and registering if necessary) a filtered sub-namespace on an object.

## -parameters

### -param modelName

The name of the model which is being extended with a namespace. For example, "Debugger.Models.Process".

### -param subNamespaceModelName

The name of the model which is being added. For example, "Debugger.Models.Process.Io".

### -param accessName

The name used to access the namespace from the parent object. For example, "Io".

### -param metadata

The metadata store used on the accessor for the namespace, such as the help on "Io" if it is newly created.

### -param filter

A filter method to evaluate the context object in order to determine if the namespace property will be applied to the context object.

### -param namespaceModelObject

The resulting namespace model is placed here.

### -param token

The resulting token is placed here.

## -returns

This method returns an HRESULT indicating the success or failure of the method call.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)