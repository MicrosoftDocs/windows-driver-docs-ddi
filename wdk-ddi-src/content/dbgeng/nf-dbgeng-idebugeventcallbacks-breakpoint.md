---
UID: NF:dbgeng.IDebugEventCallbacks.Breakpoint
title: IDebugEventCallbacks::Breakpoint method
author: windows-driver-content
description: The Breakpoint callback method is called by the engine when the target issues a breakpointexception.
old-location: debugger\idebugeventcallbacks_breakpoint.htm
old-project: debugger
ms.assetid: 76b9aca2-4630-45e2-bed4-f701018c86a5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Breakpoint method [Windows Debugging], IDebugEventCallbacks, IDebugEventCallbacks::Breakpoint, Breakpoint method [Windows Debugging], IDebugEventCallbacks interface, Breakpoint, IDebugEventCallbacks interface [Windows Debugging], Breakpoint method, ComCallbacks_16ba89ba-0eb2-4565-ba29-5865abffe1bc.xml, debugger.idebugeventcallbacks_breakpoint, dbgeng/IDebugEventCallbacks::Breakpoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugEventCallbacks.Breakpoint
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugEventCallbacks::Breakpoint method


## -description


The <b>Breakpoint</b> callback method is called by the engine when the target issues a breakpoint<a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">exception</a>.


## -syntax


````
HRESULT Breakpoint(
  [in] PDEBUG_BREAKPOINT Bp
);
````


## -parameters




### -param Bp [in]

Specifies a pointer to the <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint that was triggered.


## -returns


This method returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541651">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.



## -remarks


If the breakpoint has an associated command, the engine executes that command before calling this method.

The engine will only call this method if an <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> object corresponding to the breakpoint exists in the engine, and--if the breakpoint is a private breakpoint--this <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> object was registered with the client that added the breakpoint.

The engine calls this method only if the DEBUG_EVENT_BREAKPOINT flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

Because the engine deletes the corresponding <b>IDebugBreakpoint</b> object when a breakpoint is removed (for example, by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff554487">RemoveBreakpoint</a>), the value of <i>Bp</i> might be invalid after <b>Breakpoint</b> returns.  Therefore, implementations of <b>IDebugEventCallbacks</b> should not access <i>Bp</i> after <b>Breakpoint</b> returns.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about managing breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.


