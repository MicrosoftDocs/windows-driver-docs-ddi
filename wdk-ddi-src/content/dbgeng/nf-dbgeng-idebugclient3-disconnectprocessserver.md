---
UID: NF:dbgeng.IDebugClient3.DisconnectProcessServer
title: IDebugClient3::DisconnectProcessServer (dbgeng.h)
description: The DisconnectProcessServer method disconnects the debugger engine from a process server.
old-location: debugger\disconnectprocessserver.htm
tech.root: debugger
ms.assetid: 47776bb3-883f-4e45-9398-31de6596c57f
ms.date: 05/03/2018
ms.keywords: DisconnectProcessServer, DisconnectProcessServer method [Windows Debugging], DisconnectProcessServer method [Windows Debugging],IDebugClient interface, DisconnectProcessServer method [Windows Debugging],IDebugClient2 interface, DisconnectProcessServer method [Windows Debugging],IDebugClient3 interface, DisconnectProcessServer method [Windows Debugging],IDebugClient4 interface, DisconnectProcessServer method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],DisconnectProcessServer method, IDebugClient2 interface [Windows Debugging],DisconnectProcessServer method, IDebugClient2::DisconnectProcessServer, IDebugClient3 interface [Windows Debugging],DisconnectProcessServer method, IDebugClient3.DisconnectProcessServer, IDebugClient3::DisconnectProcessServer, IDebugClient4 interface [Windows Debugging],DisconnectProcessServer method, IDebugClient4::DisconnectProcessServer, IDebugClient5 interface [Windows Debugging],DisconnectProcessServer method, IDebugClient5::DisconnectProcessServer, IDebugClient::DisconnectProcessServer, IDebugClient_7cfc70fe-c298-40bf-aa28-0c084262d41d.xml, dbgeng/IDebugClient2::DisconnectProcessServer, dbgeng/IDebugClient3::DisconnectProcessServer, dbgeng/IDebugClient4::DisconnectProcessServer, dbgeng/IDebugClient5::DisconnectProcessServer, dbgeng/IDebugClient::DisconnectProcessServer, debugger.disconnectprocessserver
f1_keywords:
 - "dbgeng/IDebugClient.DisconnectProcessServer"
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
- IDebugClient.DisconnectProcessServer
- IDebugClient2.DisconnectProcessServer
- IDebugClient3.DisconnectProcessServer
- IDebugClient4.DisconnectProcessServer
- IDebugClient5.DisconnectProcessServer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::DisconnectProcessServer


## -description


The <b>DisconnectProcessServer</b> method disconnects the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> from a process server.


## -parameters




### -param Server [in]

Specifies the server from which to disconnect.  This handle must have been previously returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>.


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



For more information about process servers and remote debugging, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/remote-targets">Process Servers, Kernel Connection Servers, and Smart Clients</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-endprocessserver">EndProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>
 

 

