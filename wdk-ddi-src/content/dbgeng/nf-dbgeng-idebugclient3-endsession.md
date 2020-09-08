---
UID: NF:dbgeng.IDebugClient3.EndSession
title: IDebugClient3::EndSession (dbgeng.h)
description: The EndSession method ends the current debugger session.
old-location: debugger\endsession.htm
tech.root: debugger
ms.assetid: 521a0e4a-99c6-4ad4-886d-3fff9855e1fd
ms.date: 05/03/2018
keywords: ["IDebugClient3::EndSession"]
ms.keywords: EndSession, EndSession method [Windows Debugging], EndSession method [Windows Debugging],IDebugClient interface, EndSession method [Windows Debugging],IDebugClient2 interface, EndSession method [Windows Debugging],IDebugClient3 interface, EndSession method [Windows Debugging],IDebugClient4 interface, EndSession method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],EndSession method, IDebugClient2 interface [Windows Debugging],EndSession method, IDebugClient2::EndSession, IDebugClient3 interface [Windows Debugging],EndSession method, IDebugClient3.EndSession, IDebugClient3::EndSession, IDebugClient4 interface [Windows Debugging],EndSession method, IDebugClient4::EndSession, IDebugClient5 interface [Windows Debugging],EndSession method, IDebugClient5::EndSession, IDebugClient::EndSession, IDebugClient_b3243254-eb98-4ee6-8dc9-92fe4c998500.xml, dbgeng/IDebugClient2::EndSession, dbgeng/IDebugClient3::EndSession, dbgeng/IDebugClient4::EndSession, dbgeng/IDebugClient5::EndSession, dbgeng/IDebugClient::EndSession, debugger.endsession
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
 - IDebugClient3::EndSession
 - dbgeng/IDebugClient3::EndSession
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.EndSession
 - IDebugClient2.EndSession
 - IDebugClient3.EndSession
 - IDebugClient4.EndSession
 - IDebugClient5.EndSession
---

# IDebugClient3::EndSession


## -description

The <b>EndSession</b> method ends the current debugger session.

## -parameters

### -param Flags 

[in]
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

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>

## -remarks

This method may be called at any time with <i>Flags</i> set to DEBUG_END_REENTRANT.  If, for example, the application needs to exit but another thread is using the engine, this method can be used to perform as much cleanup as possible.

Using DEBUG_END_REENTRANT may leave the engine in an indeterminate state. If this flag is used, no subsequent calls should be made to the engine.

For more information about debugger sessions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>.

