---
UID: NF:dbgmodel.IDataModelManager4.CreateSyntheticObjectFromKeyStore
tech.root: debugger
title: IDataModelManager4::CreateSyntheticObjectFromKeyStore
ms.date: 12/03/2024
targetos: Windows
description: The CreateSyntheticObjectFromKeyStore method creates a synthetic object from an existing key store (key/value/metadata tuples).
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
 - IDataModelManager4::CreateSyntheticObjectFromKeyStore
f1_keywords:
 - IDataModelManager4::CreateSyntheticObjectFromKeyStore
 - dbgmodel/IDataModelManager4::CreateSyntheticObjectFromKeyStore
dev_langs:
 - c++
helpviewer_keywords:
 - CreateSyntheticObjectFromKeyStore
---

## -description

Creates a synthetic object from an existing key store, which consists of key/value/metadata tuples. The synthetic IModelObject that is created by the method.

## -parameters

### -param context

An IDebugHostContext interface on a context object. This context is optional.

### -param parentStore

An IKeyStore interface on the store object from which the synthetic object is to be created

### -param object

The synthetic IModelObject that is created by the method.

## -returns

This method returns an HRESULT indicating the success or failure of the method call.

## -remarks

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)