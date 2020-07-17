---
UID: NN:dbgmodel.IDebugHostEvaluator2
title: IDebugHostEvaluator2 (dbgmodel.h)
description: The expression evaluator interface to the underlying debugger.
ms.assetid: 12192b1b-57b6-4a5b-b2a9-2de8e13ea5c3
ms.date: 06/11/2019
keywords: ["IDebugHostEvaluator2 interface"]
f1_keywords:
 - "dbgmodel/IDebugHostEvaluator2"
 - "IDebugHostEvaluator2"
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
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
- IDebugHostEvaluator2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostEvaluator2 interface

## -description

The expression evaluator interface to the underlying debugger.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.


## -inheritance
IDebugHostEvaluator2 interits from [IDebugHostEvaluator](nn-dbgmodel-idebughostevaluator.md). 
## -remarks

One of the most important pieces of functionality which the debug host provides to clients is access to its language based expression evaluator. The [IDebugHostEvaluator](nn-dbgmodel-idebughostevaluator.md) and IDebugHostEvaluator2 interfaces are the means to access that functionality from the debug host. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
