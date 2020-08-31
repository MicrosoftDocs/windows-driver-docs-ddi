---
UID: NF:dbgeng.IDebugClient.ConnectProcessServer
title: IDebugClient::ConnectProcessServer (dbgeng.h)
description: The ConnectProcessServer methods connect to a process server.
old-location: debugger\connectprocessserver.htm
tech.root: debugger
ms.assetid: c5fd12eb-0779-400f-a271-84b7b379529f
ms.date: 05/03/2018
keywords: ["IDebugClient::ConnectProcessServer"]
ms.keywords: ConnectProcessServer, ConnectProcessServer method [Windows Debugging], ConnectProcessServer method [Windows Debugging],IDebugClient interface, ConnectProcessServer method [Windows Debugging],IDebugClient2 interface, ConnectProcessServer method [Windows Debugging],IDebugClient3 interface, ConnectProcessServer method [Windows Debugging],IDebugClient4 interface, ConnectProcessServer method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],ConnectProcessServer method, IDebugClient.ConnectProcessServer, IDebugClient2 interface [Windows Debugging],ConnectProcessServer method, IDebugClient2::ConnectProcessServer, IDebugClient3 interface [Windows Debugging],ConnectProcessServer method, IDebugClient3::ConnectProcessServer, IDebugClient4 interface [Windows Debugging],ConnectProcessServer method, IDebugClient4::ConnectProcessServer, IDebugClient5 interface [Windows Debugging],ConnectProcessServer method, IDebugClient5::ConnectProcessServer, IDebugClient::ConnectProcessServer, IDebugClient_519f5e11-6f3b-4469-8352-e6cd7c1ed384.xml, dbgeng/IDebugClient2::ConnectProcessServer, dbgeng/IDebugClient3::ConnectProcessServer, dbgeng/IDebugClient4::ConnectProcessServer, dbgeng/IDebugClient5::ConnectProcessServer, dbgeng/IDebugClient::ConnectProcessServer, debugger.connectprocessserver
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
 - IDebugClient::ConnectProcessServer
 - dbgeng/IDebugClient::ConnectProcessServer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient.ConnectProcessServer
 - IDebugClient2.ConnectProcessServer
 - IDebugClient3.ConnectProcessServer
 - IDebugClient4.ConnectProcessServer
 - IDebugClient5.ConnectProcessServer
---

# IDebugClient::ConnectProcessServer


## -description

The <b>ConnectProcessServer</b>  methods connect to a <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/p">process server</a>.

## -parameters

### -param RemoteOptions 

[in]
Specifies how the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/d">debugger engine</a> will connect with the process server.  These are the same options passed to the <b>-premote</b> option on the WinDbg and CDB command lines.  For details on the syntax of this string, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/activating-a-smart-client">Activating a Smart Client</a>.

### -param Server 

[out]
Receives a handle for the process server.  This handle is used when creating or attaching to processes by using the process server.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-disconnectprocessserver">DisconnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-endprocessserver">EndProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemidbyexecutablename">GetRunningProcessSystemIdByExecutableName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>

