---
UID: NF:dbgmodel.IDebugHostModuleSignature.QueryInterface
title: IDebugHostModuleSignature::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown AddRef on the pointer it returns.
ms.assetid: 7af09ba2-347c-408f-b9bc-df93c097021b
ms.date: 09/18/2018
keywords: ["IDebugHostModuleSignature::QueryInterface"]
ms.keywords: IDebugHostModuleSignature::QueryInterface, QueryInterface, IDebugHostModuleSignature.QueryInterface, IDebugHostModuleSignature::QueryInterface, IDebugHostModuleSignature.QueryInterface
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
 - IDebugHostModuleSignature::QueryInterface
 - dbgmodel/IDebugHostModuleSignature::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostModuleSignature.QueryInterface
---

# IDebugHostModuleSignature::QueryInterface


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

[IDebugHostModuleSignature interface](nn-dbgmodel-idebughostmodulesignature.md)

