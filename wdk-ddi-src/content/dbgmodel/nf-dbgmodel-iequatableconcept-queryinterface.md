---
UID: NF:dbgmodel.IEquatableConcept.QueryInterface
title: IEquatableConcept::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns.
ms.assetid: f0a9e269-c78b-4425-8e6c-0a3cce39d219
ms.date: 09/19/2018
keywords: ["IEquatableConcept::QueryInterface"]
ms.keywords: IEquatableConcept::QueryInterface, QueryInterface, IEquatableConcept.QueryInterface, IEquatableConcept::QueryInterface, IEquatableConcept.QueryInterface
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
 - IEquatableConcept::QueryInterface
 - dbgmodel/IEquatableConcept::QueryInterface
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IEquatableConcept.QueryInterface
---

# IEquatableConcept::QueryInterface


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

[IEquatableConcept interface](nn-dbgmodel-iequatableconcept.md)

