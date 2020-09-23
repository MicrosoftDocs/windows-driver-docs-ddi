---
UID: NF:dbgmodel.IDataModelScriptDebugBreakpoint.QueryInterface
title: IDataModelScriptDebugBreakpoint::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: ac0b3d29-cf5f-482d-9cb1-0e74b6e9d999
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugBreakpoint::QueryInterface"]
ms.keywords: IDataModelScriptDebugBreakpoint::QueryInterface, QueryInterface, IDataModelScriptDebugBreakpoint.QueryInterface, IDataModelScriptDebugBreakpoint::QueryInterface, IDataModelScriptDebugBreakpoint.QueryInterface
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
 - IDataModelScriptDebugBreakpoint::QueryInterface
 - dbgmodel/IDataModelScriptDebugBreakpoint::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugBreakpoint.QueryInterface
---

# IDataModelScriptDebugBreakpoint::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](/windows/win32/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](/cpp/atl/introduction-to-com).

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

[IDataModelScriptDebugBreakpoint interface](nn-dbgmodel-idatamodelscriptdebugbreakpoint.md)