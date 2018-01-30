---
UID: NF:dbgeng.IDebugEventCallbacks.SessionStatus
title: IDebugEventCallbacks::SessionStatus method
author: windows-driver-content
description: The SessionStatus callback method is called by the engine when a change occurs in the debugger session.
old-location: debugger\idebugeventcallbacks_sessionstatus.htm
old-project: debugger
ms.assetid: 127c4e48-87db-4735-8d3d-e01fed6a9cf0
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugEventCallbacks, IDebugEventCallbacks interface [Windows Debugging], SessionStatus method, IDebugEventCallbacks::SessionStatus, SessionStatus method [Windows Debugging], IDebugEventCallbacks interface, SessionStatus, debugger.idebugeventcallbacks_sessionstatus, SessionStatus method [Windows Debugging], dbgeng/IDebugEventCallbacks::SessionStatus, ComCallbacks_72cb31db-cc24-41b7-b891-65921c50ce12.xml
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
-	IDebugEventCallbacks.SessionStatus
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugEventCallbacks::SessionStatus method


## -description


The <b>SessionStatus</b> callback method is called by the engine when a change occurs in the debugger session.


## -syntax


````
HRESULT SessionStatus(
  [in] ULONG Status
);
````


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
The session was ended by sending DEBUG_END_ACTIVE_TERMINATE to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543004">EndSession</a>.

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


This method is only called by the engine if the DEBUG_EVENT_SESSION_STATUS flag is set in the mask returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a>.

After the engine has notified all the event callbacks of the change in the session status, it will also notify any loaded <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">extensions</a> that export the <a href="..\dbgeng\nc-dbgeng-pdebug_extension_notify.md">DebugExtensionNotify</a> callback method.  The value that it passes to the extensions depends on the value of <i>Status</i>.  If <i>Status</i> is DEBUG_SESSION_ACTIVE, it passes DEBUG_SESSION_ACTIVE; otherwise, it passes DEBUG_SESSION_INACTIVE.

In the DEBUG_SESSION_ACTIVE case, the engine follows the debugger session change notification with a target state change notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550678">IDebugEventCallbacks::ChangeDebuggeeState</a> on the event callbacks and passing DEBUG_CDS_ALL in the <i>Flags</i> parameter.  In all other cases, the engine precedes this notification with an engine state change notification by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> on the event callbacks and passing DEBUG_CES_EXECUTION_STATUS in the <i>Flags</i> parameter.

For more information about handling events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.  For information about debugger sessions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>.


