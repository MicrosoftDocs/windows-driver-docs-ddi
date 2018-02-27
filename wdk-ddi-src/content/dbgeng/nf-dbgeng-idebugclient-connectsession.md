---
UID: NF:dbgeng.IDebugClient.ConnectSession
title: IDebugClient::ConnectSession method
author: windows-driver-content
description: The ConnectSession method joins the client to an existing debugger session.
old-location: debugger\connectsession.htm
old-project: debugger
ms.assetid: 4531bf2f-ef3b-4d4f-b922-3a01a9468ac9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ConnectSession method [Windows Debugging], ConnectSession method [Windows Debugging], IDebugClient interface, ConnectSession method [Windows Debugging], IDebugClient2 interface, ConnectSession method [Windows Debugging], IDebugClient3 interface, ConnectSession method [Windows Debugging], IDebugClient4 interface, ConnectSession method [Windows Debugging], IDebugClient5 interface, ConnectSession,IDebugClient.ConnectSession, IDebugClient, IDebugClient interface [Windows Debugging], ConnectSession method, IDebugClient2 interface [Windows Debugging], ConnectSession method, IDebugClient2::ConnectSession, IDebugClient3 interface [Windows Debugging], ConnectSession method, IDebugClient3::ConnectSession, IDebugClient4 interface [Windows Debugging], ConnectSession method, IDebugClient4::ConnectSession, IDebugClient5 interface [Windows Debugging], ConnectSession method, IDebugClient5::ConnectSession, IDebugClient::ConnectSession, IDebugClient_b6ec9f48-f400-4a91-bf23-dc40dd702a15.xml, dbgeng/IDebugClient2::ConnectSession, dbgeng/IDebugClient3::ConnectSession, dbgeng/IDebugClient4::ConnectSession, dbgeng/IDebugClient5::ConnectSession, dbgeng/IDebugClient::ConnectSession, debugger.connectsession
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.ConnectSession
-	IDebugClient2.ConnectSession
-	IDebugClient3.ConnectSession
-	IDebugClient4.ConnectSession
-	IDebugClient5.ConnectSession
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::ConnectSession method


## -description


The <b>ConnectSession</b> method joins the client to an existing debugger session.


## -syntax


````
HRESULT ConnectSession(
  [in] ULONG Flags,
  [in] ULONG HistoryLimit
);
````


## -parameters




### -param Flags [in]

Specifies a bit-set of option flags for connecting to the session.  The possible values of these flags are:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_CONNECT_SESSION_NO_VERSION

</td>
<td>
Do not output the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>'s version to this client.

</td>
</tr>
<tr>
<td>
DEBUG_CONNECT_SESSION_NO_ANNOUNCE

</td>
<td>
Do not output a message notifying other clients that this client has connected.

</td>
</tr>
</table>
 


### -param HistoryLimit [in]

Specifies the maximum number of characters from the session's history to send to this client's output upon connection.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



When the client object connects to a session, the most recent output from the session is sent to the client.  If the session is currently waiting on input, the client object is given the opportunity to provide input.  Thus, the client object synchronizes with the session's input and output.

The client becomes a primary client and will appear among the list of clients in the output of the <a href="https://msdn.microsoft.com/a5f760d7-f454-49c5-853d-bcb545c0b05e">.clients</a> debugger command.

For more information about debugging clients, see Debugging Server and Debugging Client.  For more information about debugger sessions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553247">OutputServers</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nf-dbgeng-debugconnect.md">DebugConnect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558813">StartServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::ConnectSession method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

