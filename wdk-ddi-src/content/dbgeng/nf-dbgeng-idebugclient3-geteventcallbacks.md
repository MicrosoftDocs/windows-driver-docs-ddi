---
UID: NF:dbgeng.IDebugClient3.GetEventCallbacks
title: IDebugClient3::GetEventCallbacks (dbgeng.h)
description: The GetEventCallbacks method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbacks.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient3::GetEventCallbacks"]
ms.keywords: GetEventCallbacks, GetEventCallbacks method [Windows Debugging], GetEventCallbacks method [Windows Debugging],IDebugClient interface, GetEventCallbacks method [Windows Debugging],IDebugClient2 interface, GetEventCallbacks method [Windows Debugging],IDebugClient3 interface, GetEventCallbacks method [Windows Debugging],IDebugClient4 interface, GetEventCallbacks method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetEventCallbacks method, IDebugClient2 interface [Windows Debugging],GetEventCallbacks method, IDebugClient2::GetEventCallbacks, IDebugClient3 interface [Windows Debugging],GetEventCallbacks method, IDebugClient3.GetEventCallbacks, IDebugClient3::GetEventCallbacks, IDebugClient4 interface [Windows Debugging],GetEventCallbacks method, IDebugClient4::GetEventCallbacks, IDebugClient5 interface [Windows Debugging],GetEventCallbacks method, IDebugClient5::GetEventCallbacks, IDebugClient::GetEventCallbacks, IDebugClient_81e23179-deb3-4c14-ae9e-b0c0a1d48f00.xml, dbgeng/IDebugClient2::GetEventCallbacks, dbgeng/IDebugClient3::GetEventCallbacks, dbgeng/IDebugClient4::GetEventCallbacks, dbgeng/IDebugClient5::GetEventCallbacks, dbgeng/IDebugClient::GetEventCallbacks, debugger.geteventcallbacks
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
 - IDebugClient3::GetEventCallbacks
 - dbgeng/IDebugClient3::GetEventCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient3::GetEventCallbacks
---

# IDebugClient3::GetEventCallbacks


## -description

The <b>GetEventCallbacks</b>  method returns the event callbacks object registered with this client.

## -parameters

### -param Callbacks 

[out]
Receives an interface pointer to the event callbacks object registered with this client.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

Each client can have at most one <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="/windows-hardware/drivers/debugger/events">events</a>.

If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugEventCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">SetEventCallbacks</a>

