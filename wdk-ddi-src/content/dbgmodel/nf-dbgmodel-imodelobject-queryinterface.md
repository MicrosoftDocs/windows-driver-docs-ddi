---
UID: NF:dbgmodel.IModelObject.QueryInterface
title: IModelObject::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 250d519d-54d7-4f86-a210-e6f6c5048d3c
ms.date: 09/21/2018
f1_keywords:
 - "dbgmodel/IModelObject.QueryInterface"
ms.keywords: IModelObject::QueryInterface, QueryInterface, IModelObject.QueryInterface, IModelObject::QueryInterface, IModelObject.QueryInterface
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
- IModelObject.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::QueryInterface

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

[IModelObject interface](nn-dbgmodel-imodelobject.md)
