---
UID: NF:dbgeng.IDebugClient5.GetEventCallbacksWide
title: IDebugClient5::GetEventCallbacksWide (dbgeng.h)
description: The GetEventCallbacksWide method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbackswide.htm
tech.root: debugger
ms.assetid: 254eb89f-c330-4fca-8c58-6dbe56861743
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetEventCallbacksWide"]
ms.keywords: GetEventCallbacksWide, GetEventCallbacksWide method [Windows Debugging], GetEventCallbacksWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetEventCallbacksWide method, IDebugClient5.GetEventCallbacksWide, IDebugClient5::GetEventCallbacksWide, dbgeng/IDebugClient5::GetEventCallbacksWide, debugger.geteventcallbackswide
f1_keywords:
 - "dbgeng/IDebugClient5.GetEventCallbacksWide"
 - "IDebugClient5.GetEventCallbacksWide"
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
- IDebugClient5.GetEventCallbacksWide
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetEventCallbacksWide


## -description


The <b>GetEventCallbacksWide</b> method returns the event callbacks object registered with this client.


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the event callbacks object registered with this client.


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



Each client can have at most one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/events">events</a>.

If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacksWide</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-callback-objects">Callbacks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugeventcallbacks">IDebugEventCallbacks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-seteventcallbacks">SetEventCallbacks</a>
 

 

