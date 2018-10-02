---
UID: NF:dbgmodel.IDebugHostExtensibility.QueryInterface
title: IDebugHostExtensibility::QueryInterface
author: windows-driver-content
description: TBD
ms.assetid: 930a629c-8cb7-4aa4-bfba-3a12dda1bd34
ms.author: windowsdriverdev
ms.date: 09/12/2018 
ms.topic: method
ms.keywords: IDebugHostExtensibility::QueryInterface, QueryInterface, IDebugHostExtensibility.QueryInterface, IDebugHostExtensibility::QueryInterface, IDebugHostExtensibility.QueryInterface
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
-	IDebugHostExtensibility.QueryInterface
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostExtensibility::QueryInterface


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

[IDebugHostExtensibility interface](nn-dbgmodel-idebughostextensibility.md)
