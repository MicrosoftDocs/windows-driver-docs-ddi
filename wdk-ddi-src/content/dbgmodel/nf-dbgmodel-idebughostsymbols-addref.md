---
UID: NF:dbgmodel.IDebugHostSymbols.AddRef
title: IDebugHostSymbols::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object.
ms.date: 09/21/2018
keywords: ["IDebugHostSymbols::AddRef"]
ms.keywords: IDebugHostSymbols::AddRef, AddRef, IDebugHostSymbols.AddRef, IDebugHostSymbols::AddRef, IDebugHostSymbols.AddRef
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
 - IDebugHostSymbols::AddRef
 - dbgmodel/IDebugHostSymbols::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbols.AddRef
---

# IDebugHostSymbols::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
