---
UID: NN:dbgmodel.IDebugHostContext2
tech.root: debugger
title: IDebugHostContext2 (dbgmodel.h)
ms.date: 10/31/2024
targetos: Windows
description: Represents a context of the debugger answers questions about (what session, process, thread). Version 2. (dbgmodel.h)
prerelease: false
req.assembly: 
req.construct-type: iface
req.ddi-compliance: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContext2
f1_keywords:
 - IDebugHostContext2
 - dbgmodel/IDebugHostContext2
dev_langs:
 - c++
helpviewer_keywords:
 - IDebugHostContext2
---

## -description

Represents a context of the debugger answers questions about (what session, process, thread).

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance

IDebugHostContext inherits from IDebugHostContext and IUnknown.

## -remarks

Context objects are opaque blobs of information that the debug host (in cooperation with the data model) associates with every object. It may include things such as the process context or address space the information comes from, etc... A context object is an implementation of IDebugHostContext boxed within an [IModelObject](nn-dbgmodel-imodelobject.md). 

Note that IDebugHostContext is a host defined interface. A client will never implement this interface. 

**Context: The Address Space**

It is important to note that unlike prior extension models where context (the target, process, thread you are looking at) is a UI concept with all APIs relative to the current UI state, data model interfaces typically take this context either explicitly or implicitly as an IDebugHostContext interface. Each [IModelObject](nn-dbgmodel-imodelobject.md) within the data model carries this type of context information along with it and can propagate that context to objects it returns. This means that when you read a native value or a key value out of an [IModelObject](nn-dbgmodel-imodelobject.md), it will read out of the target and process where the object was originally acquired from. 
There is an explicit constant value, USE_CURRENT_HOST_CONTEXT, that can be passed to methods which take an IDebugHostContext argument. This value indicates that the context should indeed be the current UI state of the debugger. This notion does, however, need to be explicit.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

