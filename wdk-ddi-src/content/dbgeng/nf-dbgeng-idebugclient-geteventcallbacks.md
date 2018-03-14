---
UID: NF:dbgeng.IDebugClient.GetEventCallbacks
title: IDebugClient::GetEventCallbacks method
author: windows-driver-content
description: The GetEventCallbacks method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbacks.htm
old-project: debugger
ms.assetid: b67edb7a-2e74-4b7b-bbfb-5886e89a10a5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetEventCallbacks method [Windows Debugging], GetEventCallbacks method [Windows Debugging], IDebugClient interface, GetEventCallbacks method [Windows Debugging], IDebugClient2 interface, GetEventCallbacks method [Windows Debugging], IDebugClient3 interface, GetEventCallbacks method [Windows Debugging], IDebugClient4 interface, GetEventCallbacks method [Windows Debugging], IDebugClient5 interface, GetEventCallbacks,IDebugClient.GetEventCallbacks, IDebugClient, IDebugClient interface [Windows Debugging], GetEventCallbacks method, IDebugClient2 interface [Windows Debugging], GetEventCallbacks method, IDebugClient2::GetEventCallbacks, IDebugClient3 interface [Windows Debugging], GetEventCallbacks method, IDebugClient3::GetEventCallbacks, IDebugClient4 interface [Windows Debugging], GetEventCallbacks method, IDebugClient4::GetEventCallbacks, IDebugClient5 interface [Windows Debugging], GetEventCallbacks method, IDebugClient5::GetEventCallbacks, IDebugClient::GetEventCallbacks, IDebugClient_81e23179-deb3-4c14-ae9e-b0c0a1d48f00.xml, dbgeng/IDebugClient2::GetEventCallbacks, dbgeng/IDebugClient3::GetEventCallbacks, dbgeng/IDebugClient4::GetEventCallbacks, dbgeng/IDebugClient5::GetEventCallbacks, dbgeng/IDebugClient::GetEventCallbacks, debugger.geteventcallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.GetEventCallbacks
-	IDebugClient2.GetEventCallbacks
-	IDebugClient3.GetEventCallbacks
-	IDebugClient4.GetEventCallbacks
-	IDebugClient5.GetEventCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::GetEventCallbacks method


## -description


The <b>GetEventCallbacks</b>  method returns the event callbacks object registered with this client.


## -syntax


````
HRESULT GetEventCallbacks(
  [out] PDEBUG_EVENT_CALLBACKS *Callbacks
);
````


## -parameters




### -param Callbacks [out]

Receives an interface pointer to the event callbacks object registered with this client.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugEventCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacks</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 


