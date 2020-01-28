---
UID: NF:dbgeng.IDebugEventCallbacks.SessionStatus
title: IDebugEventCallbacks::SessionStatus (dbgeng.h)
description: The SessionStatus callback method is called by the engine when a change occurs in the debugger session.
old-location: debugger\idebugeventcallbacks_sessionstatus.htm
tech.root: debugger
ms.assetid: 127c4e48-87db-4735-8d3d-e01fed6a9cf0
ms.date: 05/03/2018
ms.keywords: ComCallbacks_72cb31db-cc24-41b7-b891-65921c50ce12.xml, IDebugEventCallbacks interface [Windows Debugging],SessionStatus method, IDebugEventCallbacks.SessionStatus, IDebugEventCallbacks::SessionStatus, SessionStatus, SessionStatus method [Windows Debugging], SessionStatus method [Windows Debugging],IDebugEventCallbacks interface, dbgeng/IDebugEventCallbacks::SessionStatus, debugger.idebugeventcallbacks_sessionstatus
f1_keywords:
 - "dbgeng/IDebugEventCallbacks.SessionStatus"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugEventCallbacks.SessionStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks::SessionStatus


## -description


The <b>SessionStatus</b> callback method is called by the engine when a change occurs in the debugger session.


## -parameters




### -param Status [in]

Specifies the new status of the debugger session.  The following table describes the possible values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_SESSION_ACTIVE

</td>
<td>
A debugger session has started.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_ACTIVE_TERMINATE

</td>
<td>
The session was ended by sending DEBUG_END_ACTIVE_TERMINATE to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-endsession">EndSession</a>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_ACTIVE_DETACH

</td>
<td>
The session was ended by sending DEBUG_END_ACTIVE_DETACH to <b>EndSession</b>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END_SESSION_PASSIVE

</td>
<td>
The session was ended by sending DEBUG_END_PASSIVE to <b>EndSession</b>.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_END

</td>
<td>
The  target ran to completion, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_REBOOT

</td>
<td>
The  target computer rebooted, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_HIBERNATE

</td>
<td>
The  target computer went into hibernation, ending the session.

</td>
</tr>
<tr>
<td>
DEBUG_SESSION_FAILURE

</td>
<td>
The engine was unable to continue the session.

</td>
</tr>
</table>
 


## -returns



This method's return value is ignored by the engine.




## -remarks



This method is only called by the engine if the DEBUG_EVENT_SESSION_STATUS flag is set in the mask returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">IDebugEventCallbacks::GetInterestMask</a>.

After the engine has notified all the event callbacks of the change in the session status, it will also notify any loaded <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">extensions</a> that export the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nc-dbgeng-pdebug_extension_notify">DebugExtensionNotify</a> callback method.  The value that it passes to the extensions depends on the value of <i>Status</i>.  If <i>Status</i> is DEBUG_SESSION_ACTIVE, it passes DEBUG_SESSION_ACTIVE; otherwise, it passes DEBUG_SESSION_INACTIVE.

In the DEBUG_SESSION_ACTIVE case, the engine follows the debugger session change notification with a target state change notification by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changedebuggeestate">IDebugEventCallbacks::ChangeDebuggeeState</a> on the event callbacks and passing DEBUG_CDS_ALL in the <i>Flags</i> parameter.  In all other cases, the engine precedes this notification with an engine state change notification by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> on the event callbacks and passing DEBUG_CES_EXECUTION_STATUS in the <i>Flags</i> parameter.

For more information about handling events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.  For information about debugger sessions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>.



