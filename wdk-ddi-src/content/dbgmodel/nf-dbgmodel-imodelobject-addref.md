---
UID: NF:dbgmodel.IModelObject.AddRef
title: IModelObject::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object.
ms.assetid: 57eec432-2950-42c7-a73c-febcfd412b55
ms.date: 07/20/2018
f1_keywords:
 - "dbgmodel/IModelObject.AddRef"
ms.keywords: IModelObject::AddRef, AddRef, IModelObject.AddRef, IModelObject::AddRef, IModelObject.AddRef
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
- IModelObject.AddRef
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).


## -returns

This method returns ULONG.

## -remarks



## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
