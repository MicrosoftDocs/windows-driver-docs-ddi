---
UID: NF:dbgmodel.IDebugHostEvaluator.AddRef
title: IDebugHostEvaluator::AddRef
author: windows-driver-content
description: TBD
ms.assetid: 518e7c4b-216c-4ee6-890d-d555d7a097b5
ms.author: windowsdriverdev
ms.date: 09/21/2018 
ms.topic: method
ms.keywords: IDebugHostEvaluator::AddRef, AddRef, IDebugHostEvaluator.AddRef, IDebugHostEvaluator::AddRef, IDebugHostEvaluator.AddRef
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
-	IDebugHostEvaluator.AddRef
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostEvaluator::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](https://docs.microsoft.com/windows/desktop/api/Unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](https://docs.microsoft.com/cpp/atl/introduction-to-com).


## -parameters

None

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IDebugHostEvaluator interface](nn-dbgmodel-idebughostevaluator.md)
