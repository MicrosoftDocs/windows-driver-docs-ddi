---
UID: NF:dbgeng.IDebugEventContextCallbacks.Breakpoint
tech.root: 
title: IDebugEventContextCallbacks::Breakpoint
ms.date: 02/05/2021
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgeng.h
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
 - dbgeng.h
api_name:
 - IDebugEventContextCallbacks::Breakpoint
f1_keywords:
 - IDebugEventContextCallbacks::Breakpoint
 - dbgeng/IDebugEventContextCallbacks::Breakpoint
dev_langs:
 - c++
---

## -description

A breakpoint event is generated when a breakpoint exception is received and it can be mapped to an existing breakpoint.
The callback method is given a reference to the breakpoint and should release it when it is done with it.

## -parameters

### -param Bp

### -param Context

### -param ContextSize

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)
