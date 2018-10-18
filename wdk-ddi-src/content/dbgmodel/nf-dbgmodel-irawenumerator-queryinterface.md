---
UID: NF:dbgmodel.IRawEnumerator.QueryInterface
title: IRawEnumerator::QueryInterface
author: windows-driver-content
description: Retrieves pointers to the supported interfaces on an object. 
ms.assetid: e98eeb95-89ff-4112-8562-8cf0d6f13050
ms.date: 08/13/2018 
ms.topic: method
ms.keywords: IRawEnumerator::QueryInterface, QueryInterface, IRawEnumerator.QueryInterface, IRawEnumerator::QueryInterface, IRawEnumerator.QueryInterface
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
-	IRawEnumerator.QueryInterface
product: Windows
targetos: Windows
tech.root: debugger
---

# IRawEnumerator::QueryInterface


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

[IRawEnumerator interface](nn-dbgmodel-irawenumerator.md)
