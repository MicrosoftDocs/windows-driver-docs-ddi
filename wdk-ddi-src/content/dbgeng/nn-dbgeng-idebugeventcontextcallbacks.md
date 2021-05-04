---
UID: NN:dbgeng.IDebugEventContextCallbacks
title: IDebugEventContextCallbacks (dbgeng.h)
description: This interface supports event context callbacks and replaces the use of the IDebugClient::SetEventCallbacks method.
old-location: debugger\idebugeventcontextcallbacks.htm
tech.root: debugger
ms.date: 02/12/2021
keywords: ["IDebugEventContextCallbacks interface"]
ms.keywords: IDebugEventContextCallbacks, IDebugEventContextCallbacks interface [Windows Debugging], IDebugEventContextCallbacks interface [Windows Debugging],described, dbgeng/IDebugEventContextCallbacks, debugger.idebugeventcontextcallbacks
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugEventContextCallbacks
 - dbgeng/IDebugEventContextCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugEventContextCallbacks
---

# IDebugEventContextCallbacks interface

## -description

 This interface includes a [DEBUG_EVENT_CONTEXT structure](ns-dbgeng-_debug_event_context.md) as the “context” parameter of each event callback. The context structure contains the “ProcessEngineId”, “ThreadEngineId”, and “FrameEngineId”. For example, for an event callbacks like a breakpoint event, it provides information on which process/thread the breakpoint hit on without having to do additional calls back into the engine.

This interface supports event context callbacks and replaces the use of the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a> method.

Set this interface on a debugger client by using the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient6-seteventcontextcallbacks">IDebugClient6::SetEventContextCallbacks</a> method.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugEventContextCallback</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugEventContextCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient6-seteventcontextcallbacks">IDebugClient6::SetEventContextCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">IDebugClient::SetEventCallbacks</a>
