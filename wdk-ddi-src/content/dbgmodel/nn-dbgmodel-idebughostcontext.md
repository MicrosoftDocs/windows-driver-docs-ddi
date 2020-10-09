---
UID: NN:dbgmodel.IDebugHostContext
title: IDebugHostContext (dbgmodel.h)
description: Represents a context of the debugger answers questions about (what session, process, thread).
ms.assetid: d0930562-7c04-499a-89e3-d50a463b7cce
ms.date: 07/13/2018
keywords: ["IDebugHostContext interface"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostContext
 - dbgmodel/IDebugHostContext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContext
---

# IDebugHostContext interface


## -description

Represents a context of the debugger answers questions about (what session, process, thread).

## -inheritance

IDebugHostContext interits from IUnknown.

## -remarks

Context objects are opaque blobs of information that the debug host (in cooperation with the data model) associates with every object. It may include things such as the process context or address space the information comes from, etc... A context object is an implementation of IDebugHostContext boxed within an [IModelObject](nn-dbgmodel-imodelobject.md). 

Note that IDebugHostContext is a host defined interface. A client will never implement this interface. 

**Context: The Address Space**

It is important to note that unlike prior extension models where context (the target, process, thread you are looking at) is a UI concept with all APIs relative to the current UI state, data model interfaces typically take this context either explicitly or implicitly as an IDebugHostContext interface. Each [IModelObject](nn-dbgmodel-imodelobject.md) within the data model carries this type of context information along with it and can propagate that context to objects it returns. This means that when you read a native value or a key value out of an [IModelObject](nn-dbgmodel-imodelobject.md), it will read out of the target and process where the object was originally acquired from. 
There is an explicit constant value, USE_CURRENT_HOST_CONTEXT, that can be passed to methods which take an IDebugHostContext argument. This value indicates that the context should indeed be the current UI state of the debugger. This notion does, however, need to be explicit.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)