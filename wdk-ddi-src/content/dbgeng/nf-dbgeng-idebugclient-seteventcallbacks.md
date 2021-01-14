---
UID: NF:dbgeng.IDebugClient.SetEventCallbacks
title: IDebugClient::SetEventCallbacks (dbgeng.h)
description: The SetEventCallbacks method registers an event callbacks object with this client.
old-location: debugger\seteventcallbacks.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient::SetEventCallbacks"]
ms.keywords: IDebugClient interface [Windows Debugging],SetEventCallbacks method, IDebugClient.SetEventCallbacks, IDebugClient2 interface [Windows Debugging],SetEventCallbacks method, IDebugClient2::SetEventCallbacks, IDebugClient3 interface [Windows Debugging],SetEventCallbacks method, IDebugClient3::SetEventCallbacks, IDebugClient4 interface [Windows Debugging],SetEventCallbacks method, IDebugClient4::SetEventCallbacks, IDebugClient5 interface [Windows Debugging],SetEventCallbacks method, IDebugClient5::SetEventCallbacks, IDebugClient::SetEventCallbacks, IDebugClient_a234bf28-5dd1-4e92-ab72-aa8d9a3a282b.xml, SetEventCallbacks, SetEventCallbacks method [Windows Debugging], SetEventCallbacks method [Windows Debugging],IDebugClient interface, SetEventCallbacks method [Windows Debugging],IDebugClient2 interface, SetEventCallbacks method [Windows Debugging],IDebugClient3 interface, SetEventCallbacks method [Windows Debugging],IDebugClient4 interface, SetEventCallbacks method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetEventCallbacks, dbgeng/IDebugClient3::SetEventCallbacks, dbgeng/IDebugClient4::SetEventCallbacks, dbgeng/IDebugClient5::SetEventCallbacks, dbgeng/IDebugClient::SetEventCallbacks, debugger.seteventcallbacks
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
 - IDebugClient::SetEventCallbacks
 - dbgeng/IDebugClient::SetEventCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient::SetEventCallbacks
---

# IDebugClient::SetEventCallbacks


## -description

The <b>SetEventCallbacks</b> method registers an event callbacks object with this client.

## -parameters

### -param Callbacks 

[in, optional]
Specifies the interface pointer to the event callbacks object to register with this client.

## -returns

Depending on the implementation of the method <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">IDebugEventCallbacks::GetInterestMask</a> in the object specified by <i>Callbacks</i>, other values may be returned, as described in the Remarks section.

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

If the value of <i>Callbacks</i> is not <b>NULL</b>, the method <b>IDebugEventCallbacks::GetInterestMask</b> is called.  If the return value is not S_OK, <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> have no effect and they return this value.

Each client can have at most one <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="/windows-hardware/drivers/debugger/events">events</a>.

The <b>IDebugEventCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  When <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> are successful, they call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this object will be called the next time <b>SetEventCallbacks</b> or <b>SetEventCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-geteventcallbacks">GetEventCallbacks</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a>

