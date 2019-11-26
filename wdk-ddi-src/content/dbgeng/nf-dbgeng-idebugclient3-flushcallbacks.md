---
UID: NF:dbgeng.IDebugClient3.FlushCallbacks
title: IDebugClient3::FlushCallbacks (dbgeng.h)
description: The FlushCallbacks method forces any remaining buffered output to be delivered to the IDebugOutputCallbacks object registered with this client.
old-location: debugger\flushcallbacks.htm
tech.root: debugger
ms.assetid: 2ca4ea3b-befd-424d-a4a8-81436d0ffc1c
ms.date: 05/03/2018
ms.keywords: FlushCallbacks, FlushCallbacks method [Windows Debugging], FlushCallbacks method [Windows Debugging],IDebugClient interface, FlushCallbacks method [Windows Debugging],IDebugClient2 interface, FlushCallbacks method [Windows Debugging],IDebugClient3 interface, FlushCallbacks method [Windows Debugging],IDebugClient4 interface, FlushCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],FlushCallbacks method, IDebugClient2 interface [Windows Debugging],FlushCallbacks method, IDebugClient2::FlushCallbacks, IDebugClient3 interface [Windows Debugging],FlushCallbacks method, IDebugClient3.FlushCallbacks, IDebugClient3::FlushCallbacks, IDebugClient4 interface [Windows Debugging],FlushCallbacks method, IDebugClient4::FlushCallbacks, IDebugClient5 interface [Windows Debugging],FlushCallbacks method, IDebugClient5::FlushCallbacks, IDebugClient::FlushCallbacks, IDebugClient_e808ca3a-5762-419b-96de-4c49984c1ccd.xml, dbgeng/IDebugClient2::FlushCallbacks, dbgeng/IDebugClient3::FlushCallbacks, dbgeng/IDebugClient4::FlushCallbacks, dbgeng/IDebugClient5::FlushCallbacks, dbgeng/IDebugClient::FlushCallbacks, debugger.flushcallbacks
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugClient.FlushCallbacks"
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
- IDebugClient.FlushCallbacks
- IDebugClient2.FlushCallbacks
- IDebugClient3.FlushCallbacks
- IDebugClient4.FlushCallbacks
- IDebugClient5.FlushCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::FlushCallbacks


## -description


The <b>FlushCallbacks</b> method forces any remaining buffered output to be delivered to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a> object registered with this client. 


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



The engine sometimes merges compatible callback requests to reduce callback overhead; small pieces of output are collected into larger groups to reduce the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks-output">IDebugOutputCallbacks::Output</a> calls.  Using <b>FlushCallbacks</b> is necessary for a client to guarantee that all pending callbacks have been processed at a particular point.  For example, a caller can flush callbacks before starting a lengthy operation outside of the engine so that pending callbacks are not delayed until after the operation.

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-dispatchcallbacks">DispatchCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugoutputcallbacks">IDebugOutputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugoutputcallbacks-output">IDebugOutputCallbacks::Output</a>
 

 

