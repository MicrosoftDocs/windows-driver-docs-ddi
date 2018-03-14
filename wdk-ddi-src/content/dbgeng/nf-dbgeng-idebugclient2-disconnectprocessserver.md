---
UID: NF:dbgeng.IDebugClient2.DisconnectProcessServer
title: IDebugClient2::DisconnectProcessServer method
author: windows-driver-content
description: The DisconnectProcessServer method disconnects the debugger engine from a process server.
old-location: debugger\disconnectprocessserver.htm
old-project: debugger
ms.assetid: 47776bb3-883f-4e45-9398-31de6596c57f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DisconnectProcessServer method [Windows Debugging], DisconnectProcessServer method [Windows Debugging], IDebugClient interface, DisconnectProcessServer method [Windows Debugging], IDebugClient2 interface, DisconnectProcessServer method [Windows Debugging], IDebugClient3 interface, DisconnectProcessServer method [Windows Debugging], IDebugClient4 interface, DisconnectProcessServer method [Windows Debugging], IDebugClient5 interface, DisconnectProcessServer,IDebugClient2.DisconnectProcessServer, IDebugClient interface [Windows Debugging], DisconnectProcessServer method, IDebugClient2, IDebugClient2 interface [Windows Debugging], DisconnectProcessServer method, IDebugClient2::DisconnectProcessServer, IDebugClient3 interface [Windows Debugging], DisconnectProcessServer method, IDebugClient3::DisconnectProcessServer, IDebugClient4 interface [Windows Debugging], DisconnectProcessServer method, IDebugClient4::DisconnectProcessServer, IDebugClient5 interface [Windows Debugging], DisconnectProcessServer method, IDebugClient5::DisconnectProcessServer, IDebugClient::DisconnectProcessServer, IDebugClient_7cfc70fe-c298-40bf-aa28-0c084262d41d.xml, dbgeng/IDebugClient2::DisconnectProcessServer, dbgeng/IDebugClient3::DisconnectProcessServer, dbgeng/IDebugClient4::DisconnectProcessServer, dbgeng/IDebugClient5::DisconnectProcessServer, dbgeng/IDebugClient::DisconnectProcessServer, debugger.disconnectprocessserver
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
req.lib: 
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
-	IDebugClient.DisconnectProcessServer
-	IDebugClient2.DisconnectProcessServer
-	IDebugClient3.DisconnectProcessServer
-	IDebugClient4.DisconnectProcessServer
-	IDebugClient5.DisconnectProcessServer
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient2::DisconnectProcessServer method


## -description


The <b>DisconnectProcessServer</b> method disconnects the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> from a process server.


## -syntax


````
HRESULT DisconnectProcessServer(
  [in] ULONG64 Server
);
````


## -parameters




### -param Server [in]

Specifies the server from which to disconnect.  This handle must have been previously returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>.


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



For more information about process servers and remote debugging, see <a href="https://msdn.microsoft.com/ed7ea3dc-07d1-481c-90e0-7f0b0e77ad42">Process Servers, Kernel Connection Servers, and Smart Clients</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::DisconnectProcessServer method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

