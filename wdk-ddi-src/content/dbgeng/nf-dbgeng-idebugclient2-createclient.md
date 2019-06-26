---
UID: NF:dbgeng.IDebugClient2.CreateClient
title: IDebugClient2::CreateClient (dbgeng.h)
description: The CreateClient method creates a new client object for the current thread.
old-location: debugger\createclient.htm
tech.root: debugger
ms.assetid: 61733b3e-87e9-4bb1-bed0-44efeffd7e4f
ms.date: 05/03/2018
ms.keywords: CreateClient, CreateClient method [Windows Debugging], CreateClient method [Windows Debugging],IDebugClient interface, CreateClient method [Windows Debugging],IDebugClient2 interface, CreateClient method [Windows Debugging],IDebugClient3 interface, CreateClient method [Windows Debugging],IDebugClient4 interface, CreateClient method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],CreateClient method, IDebugClient2 interface [Windows Debugging],CreateClient method, IDebugClient2.CreateClient, IDebugClient2::CreateClient, IDebugClient3 interface [Windows Debugging],CreateClient method, IDebugClient3::CreateClient, IDebugClient4 interface [Windows Debugging],CreateClient method, IDebugClient4::CreateClient, IDebugClient5 interface [Windows Debugging],CreateClient method, IDebugClient5::CreateClient, IDebugClient::CreateClient, IDebugClient_baa33ba0-bc95-4bfb-b8bf-b91598833599.xml, dbgeng/IDebugClient2::CreateClient, dbgeng/IDebugClient3::CreateClient, dbgeng/IDebugClient4::CreateClient, dbgeng/IDebugClient5::CreateClient, dbgeng/IDebugClient::CreateClient, debugger.createclient
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient.CreateClient
- IDebugClient2.CreateClient
- IDebugClient3.CreateClient
- IDebugClient4.CreateClient
- IDebugClient5.CreateClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient2::CreateClient


## -description


The <b>CreateClient</b> method creates a new client object for the current thread.


## -parameters




### -param Client [out]

Receives an interface pointer for the new client.


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



This method creates a client that may be used in the current thread.

Clients are specific to the thread that created them.  Calls from other threads fail immediately.  The <b>CreateClient</b> method is a notable exception; it allows creation of a new client for a new thread. 

All callbacks for a client are made in the thread with which the client was created.

For more information about client objects and how they are used in the debugger engine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/client-objects">Client Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-debugcreate">DebugCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

