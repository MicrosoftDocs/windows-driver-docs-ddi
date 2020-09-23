---
UID: NF:dbgmodel.IDebugHostMemory.QueryInterface
title: IDebugHostMemory::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: b15dd2bb-0ffb-4ad2-a03d-c574e23074db
ms.date: 09/18/2018
keywords: ["IDebugHostMemory::QueryInterface"]
ms.keywords: IDebugHostMemory::QueryInterface, QueryInterface, IDebugHostMemory.QueryInterface, IDebugHostMemory::QueryInterface, IDebugHostMemory.QueryInterface
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
 - IDebugHostMemory::QueryInterface
 - dbgmodel/IDebugHostMemory::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostMemory.QueryInterface
---

# IDebugHostMemory::QueryInterface


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

[IDebugHostMemory interface](nn-dbgmodel-idebughostmemory.md)