---
UID: NF:dbgeng.IDebugEventCallbacksWide.ChangeEngineState
title: IDebugEventCallbacksWide::ChangeEngineState (dbgeng.h)
description: The ChangeEngineState callback method is called by the engine when its state has changed.
old-location: debugger\idebugeventcallbackswide_changeenginestate.htm
tech.root: debugger
ms.assetid: 14205476-3f58-4105-99a7-a3baa2eba033
ms.date: 05/03/2018
keywords: ["IDebugEventCallbacksWide::ChangeEngineState"]
ms.keywords: ChangeEngineState, ChangeEngineState method [Windows Debugging], ChangeEngineState method [Windows Debugging],IDebugEventCallbacksWide interface, IDebugEventCallbacksWide interface [Windows Debugging],ChangeEngineState method, IDebugEventCallbacksWide.ChangeEngineState, IDebugEventCallbacksWide::ChangeEngineState, dbgeng/IDebugEventCallbacksWide::ChangeEngineState, debugger.idebugeventcallbackswide_changeenginestate
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
 - IDebugEventCallbacksWide::ChangeEngineState
 - dbgeng/IDebugEventCallbacksWide::ChangeEngineState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugEventCallbacksWide.ChangeEngineState
---

# IDebugEventCallbacksWide::ChangeEngineState


## -description

The <b>ChangeEngineState</b> callback method is called by the engine when its state has changed.

## -parameters

### -param Flags 

[in]
Specifies a bit-set indicating the type of changes that occurred in the engine's state.  The following bit flags might be set:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CES_CURRENT_THREAD

</td>
<td>
The current thread has changed, which implies that the current target and current process might also have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_EFFECTIVE_PROCESSOR

</td>
<td>
The effective processor has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_BREAKPOINTS

</td>
<td>
One or more <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/breakpoints3">breakpoints</a> have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_CODE_LEVEL

</td>
<td>
The code interpretation level has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_EXECUTION_STATUS

</td>
<td>
The execution status has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_ENGINE_OPTIONS

</td>
<td>
The engine options have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_LOG_FILE

</td>
<td>
The log file has been opened or closed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_RADIX

</td>
<td>
The default radix has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_EVENT_FILTERS

</td>
<td>
The event filters have changed.  

</td>
</tr>
<tr>
<td>
DEBUG_CES_PROCESS_OPTIONS

</td>
<td>
The process options for the current process have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_EXTENSIONS

</td>
<td>
Extension DLLs have been loaded or unloaded. (For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/loading-debugger-extension-dlls">Loading Debugger Extension DLLs</a>.)

</td>
</tr>
<tr>
<td>
DEBUG_CES_SYSTEMS

</td>
<td>
A target has been added or removed.  

</td>
</tr>
<tr>
<td>
DEBUG_CES_ASSEMBLY_OPTIONS

</td>
<td>
The assemble options have changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_EXPRESSION_SYNTAX

</td>
<td>
The default expression syntax has changed.

</td>
</tr>
<tr>
<td>
DEBUG_CES_TEXT_REPLACEMENTS

</td>
<td>
Text replacements have changed.  

</td>
</tr>
</table>

### -param Argument 

[in]
Provides additional information about the change to the engine's state.  If more than one bit flag is set in the <i>Flags</i> parameter, the <i>Argument</i> parameter is not used.  Otherwise, the interpretation of the value of <i>Argument</i> depends on the value of <i>Flags</i>:





#### DEBUG_CES_CURRENT_THREAD

The value of <i>Argument</i> is the current engine thread ID or--if there is no current thread--DEBUG_ANY_ID.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



#### DEBUG_CES_EFFECTIVE_PROCESSOR

The value of <i>Argument</i> is the type of the effective processor.



#### DEBUG_CES_BREAKPOINTS

The value of <i>Argument</i> is the breakpoint ID of the breakpoint that was changed or--if more than one breakpoint was changed--DEBUG_ANY_ID.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/breakpoints3">Breakpoints</a>.



#### DEBUG_CES_CODE_LEVEL

The value of <i>Argument</i> is the code interpretation level.



#### DEBUG_CES_EXECUTION_STATUS

The value of <i>Argument</i> is the execution status (as described in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-status-xxx">DEBUG_STATUS_XXX</a> topic) possibly combined with the bit flag DEBUG_STATUS_INSIDE_WAIT. DEBUG_STATUS_INSIDE_WAIT is set when a <b>WaitForEvent</b> call is pending. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>.



#### DEBUG_CES_ENGINE_OPTIONS

The value of <i>Argument</i> is the engine options. 



#### DEBUG_CES_LOG_FILE

The value of <i>Argument</i> is <b>TRUE</b> if the log file was opened and <b>FALSE</b> if the log file was closed.



#### DEBUG_CES_RADIX

The value of <i>Argument</i> is the default radix.



#### DEBUG_CES_EVENT_FILTERS

The value of <i>Argument</i> is the index of the event filter that was changed or--if more than one event filter was changed--DEBUG_ANY_ID.



#### DEBUG_CES_PROCESS_OPTIONS

The value of <i>Argument</i> is the process options for the current process.



#### DEBUG_CES_EXTENSIONS

The value of <i>Argument</i> is zero.



#### DEBUG_CES_SYSTEMS

The value of <i>Argument</i> is the target ID of the target that was added or--if a target was removed--DEBUG_ANY_ID.



#### DEBUG_CES_ASSEMBLE_OPTIONS

The value of <i>Argument</i> is the assemble options.



#### DEBUG_CES_EXPRESSION_SYNTAX

The value of <i>Argument</i> is the default expression syntax.



#### DEBUG_CES_TEXT_REPLACEMENTS

The value of <i>Argument</i> is DEBUG_ANY_ID.

## -returns

The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacksWide</b> object is registered, is disabled.

## -remarks

This method is only called by the engine if the DEBUG_EVENT_CHANGE_ENGINE_STATE flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbackswide-getinterestmask">IDebugEventCallbacksWide::GetInterestMask</a>.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.

