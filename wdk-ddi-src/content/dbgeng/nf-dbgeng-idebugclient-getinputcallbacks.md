---
UID: NF:dbgeng.IDebugClient.GetInputCallbacks
title: IDebugClient::GetInputCallbacks (dbgeng.h)
description: The GetInputCallbacks method returns the input callbacks object registered with this client.
old-location: debugger\getinputcallbacks.htm
tech.root: debugger
ms.assetid: 1788d9b6-5e5e-48b6-b746-fd078768892f
ms.date: 05/03/2018
ms.keywords: GetInputCallbacks, GetInputCallbacks method [Windows Debugging], GetInputCallbacks method [Windows Debugging],IDebugClient interface, GetInputCallbacks method [Windows Debugging],IDebugClient2 interface, GetInputCallbacks method [Windows Debugging],IDebugClient3 interface, GetInputCallbacks method [Windows Debugging],IDebugClient4 interface, GetInputCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetInputCallbacks method, IDebugClient.GetInputCallbacks, IDebugClient2 interface [Windows Debugging],GetInputCallbacks method, IDebugClient2::GetInputCallbacks, IDebugClient3 interface [Windows Debugging],GetInputCallbacks method, IDebugClient3::GetInputCallbacks, IDebugClient4 interface [Windows Debugging],GetInputCallbacks method, IDebugClient4::GetInputCallbacks, IDebugClient5 interface [Windows Debugging],GetInputCallbacks method, IDebugClient5::GetInputCallbacks, IDebugClient::GetInputCallbacks, IDebugClient_ab365943-baaa-4a51-9c1b-d82086098b2f.xml, dbgeng/IDebugClient2::GetInputCallbacks, dbgeng/IDebugClient3::GetInputCallbacks, dbgeng/IDebugClient4::GetInputCallbacks, dbgeng/IDebugClient5::GetInputCallbacks, dbgeng/IDebugClient::GetInputCallbacks, debugger.getinputcallbacks
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
- IDebugClient.GetInputCallbacks
- IDebugClient2.GetInputCallbacks
- IDebugClient3.GetInputCallbacks
- IDebugClient4.GetInputCallbacks
- IDebugClient5.GetInputCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient::GetInputCallbacks


## -description


The <b>GetInputCallbacks</b> method returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">input callbacks</a> object registered with this client.


## -parameters




### -param Callbacks [out]

Receives an interface pointer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> object registered with the client.


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



Each client can have at most one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a> object registered with it to receive requests for input.

If no <b>IDebugInputCallbacks</b> object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugInputCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugInputCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebuginputcallbacks">IDebugInputCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-setinputcallbacks">SetInputCallbacks</a>
 

 

