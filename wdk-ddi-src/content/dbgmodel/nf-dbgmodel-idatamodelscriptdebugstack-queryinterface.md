---
UID: NF:dbgmodel.IDataModelScriptDebugStack.QueryInterface
title: IDataModelScriptDebugStack::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: 8b70ad4f-96f7-45eb-aa46-04128c38fb19
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugStack::QueryInterface"]
ms.keywords: IDataModelScriptDebugStack::QueryInterface, QueryInterface, IDataModelScriptDebugStack.QueryInterface, IDataModelScriptDebugStack::QueryInterface, IDataModelScriptDebugStack.QueryInterface
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
 - IDataModelScriptDebugStack::QueryInterface
 - dbgmodel/IDataModelScriptDebugStack::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugStack.QueryInterface
---

# IDataModelScriptDebugStack::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).

## -parameters

### -param iid

The interface ID. A pointer to an existing object provided as input.

### -param iface

The returned pointer to the requested COM interface.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

Standard COM method.

## -see-also

[IDataModelScriptDebugStack interface](nn-dbgmodel-idatamodelscriptdebugstack.md)

