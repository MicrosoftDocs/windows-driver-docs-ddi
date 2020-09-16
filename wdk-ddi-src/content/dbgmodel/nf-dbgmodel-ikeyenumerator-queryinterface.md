---
UID: NF:dbgmodel.IKeyEnumerator.QueryInterface
title: IKeyEnumerator::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: 4f870fe7-0c4f-4cf0-aa73-78802329d35d
ms.date: 08/13/2018
keywords: ["IKeyEnumerator::QueryInterface"]
ms.keywords: IKeyEnumerator::QueryInterface, QueryInterface, IKeyEnumerator.QueryInterface, IKeyEnumerator::QueryInterface, IKeyEnumerator.QueryInterface
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
 - IKeyEnumerator::QueryInterface
 - dbgmodel/IKeyEnumerator::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IKeyEnumerator.QueryInterface
---

# IKeyEnumerator::QueryInterface


## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](https://docs.microsoft.com/windows/win32/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).

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

[IKeyEnumerator interface](nn-dbgmodel-ikeyenumerator.md)

