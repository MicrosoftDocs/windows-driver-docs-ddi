---
UID: NF:dbgeng.IDebugEventCallbacksWide.ExitThread
title: IDebugEventCallbacksWide::ExitThread (dbgeng.h)
description: The ExitThread callback method is called by the engine when an exit-threaddebugging event occurs in the target.
old-location: debugger\idebugeventcallbackswide_exitthread.htm
tech.root: debugger
ms.assetid: 77933fa9-ff30-45cf-894d-83a425802e25
ms.date: 05/03/2018
keywords: ["IDebugEventCallbacksWide::ExitThread"]
ms.keywords: ExitThread, ExitThread method [Windows Debugging], ExitThread method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],ExitThread method, IDebugEventCallbacksWide.ExitThread, IDebugEventCallbacksWide::ExitThread, dbgeng/IDebugEventCallbacksWide::ExitThread, debugger.idebugeventcallbackswide_exitthread
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
 - IDebugEventCallbacksWide::ExitThread
 - dbgeng/IDebugEventCallbacksWide::ExitThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugEventCallbacksWide.ExitThread
---

# IDebugEventCallbacksWide::ExitThread


## -description

The <b>ExitThread</b> callback method is called by the engine when an exit-threaddebugging event occurs in the target.

## -parameters

### -param ExitCode 

[in]
Specifies the exit code for the thread.

## -returns

This method returns a <a href="/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> value, which indicates how the execution of the target should proceed after the engine processes this event.  For details on how the engine treats this value, see <a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.

## -remarks

This method is only called by the engine if the DEBUG_EVENT_EXIT_THREAD flag is set in the mask returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.  For information about threads, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.