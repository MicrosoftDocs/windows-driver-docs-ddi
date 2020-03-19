---
UID: NN:dbgmodel.IDataModelScriptDebugStack
title: IDataModelScriptDebugStack (dbgmodel.h)
description: An interface to a stack in the script. The script provider implements this interface to expose the notion of a call stack to the script debugger.
ms.assetid: 835f361a-a4eb-4b32-a4a6-0aff8d9a2f50
ms.date: 07/13/2018
keywords: ["IDataModelScriptDebugStack interface"]
f1_keywords:
 - "dbgmodel/IDataModelScriptDebugStack"
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
- IDataModelScriptDebugStack
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugStack interface

## -description

An interface to a stack in the script. The script provider implements this interface to expose the notion of a call stack to the script debugger.


## -inheritance
IDataModelScriptDebugStack interits from IUnknown. 
## -remarks

When an event occurs which breaks into the script debugger, the debugging interface will want to retrieve the call stack for the break location. This is done through the GetStack method. Such stack is expressed via the IDataModelScriptDebugStack which is defined as indicated below. 

Note that the overall stack may span multiple scripts and/or multiple script providers. The call stack which is returned from a single call to the GetStack method on a particular script's debug interface should only return the segment of the call stack within the bounds of that script. It is entirely possible that a script debug engine can retrieve the call stack as spans multiple script contexts if two scripts of the same provider interact. The GetStack method should not return the portion of the stack which is in another script. Instead, if this situation can be detected, the stack frame which is the boundary frame into the script should mark itself as a transition frame via an implementation of the IsTransitionPoint and GetTransition methods on that stack frame. It is expected that the debugger interface will stitch together the overall stack from the multiple stack segments which exist. 

It is imperative that transitions be implemented in this manner or the debug interface may direct inquiries about local variables, parameters, breakpoints, and other script specific constructs to the wrong script context. This will result in undefined behavior in the debugger interface. 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)

