---
UID: NF:dbgeng.IDebugEventContextCallbacks.SessionStatus
tech.root: 
title: IDebugEventContextCallbacks::SessionStatus
ms.date: 02/10/2021
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
 - IDebugEventContextCallbacks::SessionStatus
f1_keywords:
 - IDebugEventContextCallbacks::SessionStatus
 - dbgeng/IDebugEventContextCallbacks::SessionStatus
dev_langs:
 - c++
---

## -description

**Microsoft internal use only**

Session status is synchronous like the other wait callbacks but it is called as the state of the session is changing rather than at specific events so its return value does not influence waiting.  Implementations should just return DEBUG_STATUS_NO_CHANGE.
Also, because some of the status notifications are very early or very late in the session lifetime there may not be current processes or threads when the notification is generated.

## -parameters

### -param Status

## -returns

## -remarks

## -see-also

[IDebugEventContextCallbacks (dbgeng.h)](nn-dbgeng-idebugeventcontextcallbacks.md)