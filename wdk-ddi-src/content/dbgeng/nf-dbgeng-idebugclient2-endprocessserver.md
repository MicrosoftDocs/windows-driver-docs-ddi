---
UID: NF:dbgeng.IDebugClient2.EndProcessServer
title: IDebugClient2::EndProcessServer (dbgeng.h)
description: The EndProcessServer method requests that a process server be shut down.
old-location: debugger\endprocessserver.htm
tech.root: debugger
ms.assetid: 45421556-6781-4ec4-9ee1-783df99437ae
ms.date: 05/03/2018
keywords: ["IDebugClient2::EndProcessServer"]
ms.keywords: EndProcessServer, EndProcessServer method [Windows Debugging], EndProcessServer method [Windows Debugging],IDebugClient2 interface, EndProcessServer method [Windows Debugging],IDebugClient3 interface, EndProcessServer method [Windows Debugging],IDebugClient4 interface, EndProcessServer method [Windows Debugging],IDebugClient5 interface, IDebugClient2 interface [Windows Debugging],EndProcessServer method, IDebugClient2.EndProcessServer, IDebugClient2::EndProcessServer, IDebugClient3 interface [Windows Debugging],EndProcessServer method, IDebugClient3::EndProcessServer, IDebugClient4 interface [Windows Debugging],EndProcessServer method, IDebugClient4::EndProcessServer, IDebugClient5 interface [Windows Debugging],EndProcessServer method, IDebugClient5::EndProcessServer, IDebugClient_a24a3c82-f966-424c-a739-a775b45cb600.xml, dbgeng/IDebugClient2::EndProcessServer, dbgeng/IDebugClient3::EndProcessServer, dbgeng/IDebugClient4::EndProcessServer, dbgeng/IDebugClient5::EndProcessServer, debugger.endprocessserver
f1_keywords:
 - "dbgeng/IDebugClient2.EndProcessServer"
 - "IDebugClient2.EndProcessServer"
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
- IDebugClient2.EndProcessServer
- IDebugClient3.EndProcessServer
- IDebugClient4.EndProcessServer
- IDebugClient5.EndProcessServer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient2::EndProcessServer


## -description


The <b>EndProcessServer</b> method requests that a process server be shut down.


## -parameters




### -param Server [in]

Specifies the process server to shut down.  This handle must have been previously returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-disconnectprocessserver">DisconnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-startprocessserver">StartProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-waitforprocessserverend">WaitForProcessServerEnd</a>
 

 

