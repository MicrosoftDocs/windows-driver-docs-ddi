---
UID: NF:dbgmodel.IDataModelManager.AddRef
title: IDataModelManager::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object.
ms.assetid: 99772ad4-1a6d-4611-81c9-c83ce12d3d30
ms.date: 07/20/2018
keywords: ["IDataModelManager::AddRef"]
ms.keywords: IDataModelManager::AddRef, AddRef, IDataModelManager.AddRef, IDataModelManager::AddRef, IDataModelManager.AddRef
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelManager::AddRef
 - dbgmodel/IDataModelManager::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelManager.AddRef
---

# IDataModelManager::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](https://docs.microsoft.com/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)

