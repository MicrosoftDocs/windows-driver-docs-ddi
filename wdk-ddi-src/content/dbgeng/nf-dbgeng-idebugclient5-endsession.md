---
UID: NF:dbgeng.IDebugClient5.EndSession
title: IDebugClient5::EndSession method
author: windows-driver-content
description: The EndSession method ends the current debugger session.
old-location: debugger\endsession.htm
old-project: debugger
ms.assetid: 521a0e4a-99c6-4ad4-886d-3fff9855e1fd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::EndSession, EndSession
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
req.alt-api: IDebugClient.EndSession,IDebugClient2.EndSession,IDebugClient3.EndSession,IDebugClient4.EndSession,IDebugClient5.EndSession
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugClient5::EndSession method



## -description
The <b>EndSession</b> method ends the current debugger session.



## -syntax

````
HRESULT EndSession(
  [in] ULONG Flags
);
````


## -parameters

### -param Flags [in]

Specifies how to end the session.  <i>Flags</i> can be one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_END_PASSIVE

</td>
<td>
Perform cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_ACTIVE_TERMINATE

</td>
<td>
Attempt to terminate all user-mode targets before performing cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_ACTIVE_DETACH

</td>
<td>
Attempt to disconnect from all targets before performing cleanup for the session.

</td>
</tr>
<tr>
<td>
DEBUG_END_REENTRANT

</td>
<td>
Perform only the cleanup that doesn't require acquiring locks.  See Remarks section for details.

</td>
</tr>
<tr>
<td>
DEBUG_END_DISCONNECT

</td>
<td>
Do not end the session.  Disconnect the client from the session and disable the client.

This flag is intended for when remote clients disconnect.  It generates a server message about the disconnection.

</td>
</tr>
</table>
 


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method may be called at any time with <i>Flags</i> set to DEBUG_END_REENTRANT.  If, for example, the application needs to exit but another thread is using the engine, this method can be used to perform as much cleanup as possible.

Using DEBUG_END_REENTRANT may leave the engine in an indeterminate state. If this flag is used, no subsequent calls should be made to the engine.

For more information about debugger sessions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>.</p>