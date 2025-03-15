---
UID: NF:dbgmodel.IConstructableConcept.AddRef
tech.root: debugger
title: IConstructableConcept::AddRef method (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description: The AddRef method increments the reference count for an interface on an object. This method belongs to the IConstructableConcept interface.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IConstructableConcept::AddRef
f1_keywords:
 - IConstructableConcept::AddRef
 - dbgmodel/IConstructableConcept::AddRef
dev_langs:
 - c++
helpviewer_keywords:
 - AddRef
---

## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).


## -returns

This method returns ULONG.

## -remarks

Standard COM method.

## -see-also

[IConstructableConcept interface](nn-dbgmodel-iconstructableconcept.md)
