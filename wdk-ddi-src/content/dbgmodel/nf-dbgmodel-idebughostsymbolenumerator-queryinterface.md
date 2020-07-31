---
UID: NF:dbgmodel.IDebugHostSymbolEnumerator.QueryInterface
title: IDebugHostSymbolEnumerator::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 27784335-4eb9-48f9-a442-7ce943178a15
ms.date: 08/22/2018
keywords: ["IDebugHostSymbolEnumerator::QueryInterface"]
f1_keywords:
 - "dbgmodel/IDebugHostSymbolEnumerator.QueryInterface"
 - "IDebugHostSymbolEnumerator.QueryInterface"
ms.keywords: IDebugHostSymbolEnumerator::QueryInterface, QueryInterface, IDebugHostSymbolEnumerator.QueryInterface, IDebugHostSymbolEnumerator::QueryInterface, IDebugHostSymbolEnumerator.QueryInterface
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
- IDebugHostSymbolEnumerator.QueryInterface
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbolEnumerator::QueryInterface


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

[IDebugHostSymbolEnumerator interface](nn-dbgmodel-idebughostsymbolenumerator.md)
