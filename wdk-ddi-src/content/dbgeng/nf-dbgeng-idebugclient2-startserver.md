---
UID: NF:dbgeng.IDebugClient2.StartServer
title: IDebugClient2::StartServer (dbgeng.h)
description: The StartServer method starts a debugging server.
old-location: debugger\startserver.htm
tech.root: debugger
ms.assetid: 52b1c590-a62b-4e27-a267-1862cb76e6d4
ms.date: 05/03/2018
keywords: ["IDebugClient2::StartServer"]
ms.keywords: IDebugClient interface [Windows Debugging],StartServer method, IDebugClient2 interface [Windows Debugging],StartServer method, IDebugClient2.StartServer, IDebugClient2::StartServer, IDebugClient3 interface [Windows Debugging],StartServer method, IDebugClient3::StartServer, IDebugClient4 interface [Windows Debugging],StartServer method, IDebugClient4::StartServer, IDebugClient5 interface [Windows Debugging],StartServer method, IDebugClient5::StartServer, IDebugClient::StartServer, IDebugClient_5ca142fb-bb02-4484-adf0-9337f53d0bdc.xml, StartServer, StartServer method [Windows Debugging], StartServer method [Windows Debugging],IDebugClient interface, StartServer method [Windows Debugging],IDebugClient2 interface, StartServer method [Windows Debugging],IDebugClient3 interface, StartServer method [Windows Debugging],IDebugClient4 interface, StartServer method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::StartServer, dbgeng/IDebugClient3::StartServer, dbgeng/IDebugClient4::StartServer, dbgeng/IDebugClient5::StartServer, dbgeng/IDebugClient::StartServer, debugger.startserver
f1_keywords:
 - "dbgeng/IDebugClient.StartServer"
 - "IDebugClient.StartServer"
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
- IDebugClient.StartServer
- IDebugClient2.StartServer
- IDebugClient3.StartServer
- IDebugClient4.StartServer
- IDebugClient5.StartServer
targetos: Windows
req.typenames: 
---

# IDebugClient2::StartServer


## -description


The <b>StartServer</b>  method starts a debugging server.


## -parameters




### -param Options 
[in]
Specifies the connections options for this server.  These are the same options given to the <b>.server</b> debugger command or the WinDbg and CDB <b>-server</b> command-line option.  For details on the syntax of this string, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/activating-a-debugging-server">Activating a Debugging Server</a>.


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



The server that is started will be accessible by other <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debuggers-in-the-debugging-tools-for-windows-package">debuggers</a> through the transport specified in the <i>Options</i> parameter.

For more information about debugging servers, see Debugging Server and Debugging Client.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-debugconnect">DebugConnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-outputservers">OutputServers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>
 

 

