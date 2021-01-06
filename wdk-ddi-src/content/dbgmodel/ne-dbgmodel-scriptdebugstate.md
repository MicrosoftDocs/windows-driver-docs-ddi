---
UID: NE:dbgmodel.ScriptDebugState
title: ScriptDebugState (dbgmodel.h)
description: Defines the current debugging state of a script.
ms.date: 07/16/2018
keywords: ["ScriptDebugState enumeration"]
ms.keywords: ScriptDebugState, ,
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - ScriptDebugState
 - dbgmodel/ScriptDebugState
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - ScriptDebugState
---

# ScriptDebugState enumeration


## -description

Defines the current debugging state of a script.

## -enum-fields

### -field ScriptDebugNoDebugger

Indicates that debugging is not active on the script.

### -field ScriptDebugNotExecuting 

Indicates that no code within the script is actively executing.

### -field ScriptDebugExecuting 

Indicates that the script is executing code.

### -field ScriptDebugBreak

The script status is that it is broken into the script debugger.

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
