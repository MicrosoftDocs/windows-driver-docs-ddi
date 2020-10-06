---
UID: NF:dbgmodel.IRawEnumerator.AddRef
title: IRawEnumerator::AddRef (dbgmodel.h)
description: Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object.
ms.assetid: 9fe59d32-e769-4b2e-8d6b-2069a6e0b884
ms.date: 09/21/2018
keywords: ["IRawEnumerator::AddRef"]
ms.keywords: IRawEnumerator::AddRef, AddRef, IRawEnumerator.AddRef, IRawEnumerator::AddRef, IRawEnumerator.AddRef
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
 - IRawEnumerator::AddRef
 - dbgmodel/IRawEnumerator::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IRawEnumerator.AddRef
---

# IRawEnumerator::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IRawEnumerator interface](nn-dbgmodel-irawenumerator.md)