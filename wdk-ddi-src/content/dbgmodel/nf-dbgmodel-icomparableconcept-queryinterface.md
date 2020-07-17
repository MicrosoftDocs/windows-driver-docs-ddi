---
UID: NF:dbgmodel.IComparableConcept.QueryInterface
title: IComparableConcept::QueryInterface (dbgmodel.h)
description: Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 
ms.assetid: 90f5872f-e5b4-4a61-ab92-be2a6bae2030
ms.date: 09/21/2018
keywords: ["IComparableConcept::QueryInterface"]
f1_keywords:
 - "dbgmodel/IComparableConcept.QueryInterface"
 - "IComparableConcept.QueryInterface"
ms.keywords: IComparableConcept::QueryInterface, QueryInterface, IComparableConcept.QueryInterface, IComparableConcept::QueryInterface, IComparableConcept.QueryInterface
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
- IComparableConcept.QueryInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IComparableConcept::QueryInterface


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

[IComparableConcept interface](nn-dbgmodel-icomparableconcept.md)
