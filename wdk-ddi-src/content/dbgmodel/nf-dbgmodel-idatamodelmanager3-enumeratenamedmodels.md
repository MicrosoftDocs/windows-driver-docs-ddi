---
UID: NF:dbgmodel.IDataModelManager3.EnumerateNamedModels
tech.root: debugger
title: IDataModelManager3::EnumerateNamedModels
ms.date: 11/20/2024
targetos: Windows
description: The EnumerateNamedModels method enumerates the named models in the data model manager.
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
 - IDataModelManager3::EnumerateNamedModels
f1_keywords:
 - IDataModelManager3::EnumerateNamedModels
 - dbgmodel/IDataModelManager3::EnumerateNamedModels
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateNamedModels
---

## -description

EnumerateNamedModels returns an enumerator which will enumerate all registered named models and their associated name.

## -parameters

### -param ppEnumerator

A pointer to an INamedModelsEnumerator interface. This enumerator can be used to enumerate all registered named models

## -returns

This method returns an HRESULT indicating the success or failure of the method call.

## -remarks

You can use this method to get an enumerator and then use the methods of the INamedModelsEnumerator interface to iterate through the named models.

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)