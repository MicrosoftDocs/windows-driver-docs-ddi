---
UID: NF:dbgeng.IDebugEventCallbacksWide.Breakpoint
title: IDebugEventCallbacksWide::Breakpoint (dbgeng.h)
description: The Breakpoint callback method is called by the engine when the target issues a breakpointexception.
old-location: debugger\idebugeventcallbackswide_breakpoint.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugEventCallbacksWide::Breakpoint"]
ms.keywords: Breakpoint, Breakpoint method [Windows Debugging], Breakpoint method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],Breakpoint method, IDebugEventCallbacksWide.Breakpoint, IDebugEventCallbacksWide::Breakpoint, dbgeng/IDebugEventCallbacksWide::Breakpoint, debugger.idebugeventcallbackswide_breakpoint
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
 - IDebugEventCallbacksWide::Breakpoint
 - dbgeng/IDebugEventCallbacksWide::Breakpoint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugEventCallbacksWide.Breakpoint
---

# IDebugEventCallbacksWide::Breakpoint


## -description

The <b>Breakpoint</b> callback method is called by the engine when the target issues a breakpoint<a href="/windows-hardware/drivers/">exception</a>.

## -parameters

### -param Bp 

[in]
Specifies a pointer to the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> object corresponding to the breakpoint that was triggered.

## -returns

This method returns a <a href="/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.

## -remarks

If the breakpoint has an associated command, the engine executes that command before calling this method.

The engine will only call this method if an <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> object corresponding to the breakpoint exists in the engine, and--if the breakpoint is a private breakpoint--this <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbackswide">IDebugEventCallbacksWide</a> object was registered with the client that added the breakpoint.

The engine calls this method only if the DEBUG_EVENT_BREAKPOINT flag is set in the mask returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">IDebugEventCallbacksWide::GetInterestMask</a>.

Because the engine deletes the corresponding <b>IDebugBreakpoint</b> object when a breakpoint is removed (for example, by using <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a>), the value of <i>Bp</i> might be invalid after <b>Breakpoint</b> returns.  Therefore, implementations of <b>IDebugEventCallbacksWide</b> should not access <i>Bp</i> after <b>Breakpoint</b> returns.

For more information about handling events, see <a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.  For information about managing breakpoints, see <a href="/windows-hardware/drivers/debugger/breakpoints3">Breakpoints</a>.
