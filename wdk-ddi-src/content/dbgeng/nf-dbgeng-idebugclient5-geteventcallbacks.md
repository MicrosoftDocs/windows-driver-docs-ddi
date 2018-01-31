---
UID: NF:dbgeng.IDebugClient5.GetEventCallbacks
title: IDebugClient5::GetEventCallbacks method
author: windows-driver-content
description: The GetEventCallbacks method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbacks.htm
old-project: debugger
ms.assetid: b67edb7a-2e74-4b7b-bbfb-5886e89a10a5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient2::GetEventCallbacks, GetEventCallbacks method [Windows Debugging], IDebugClient interface, IDebugClient_81e23179-deb3-4c14-ae9e-b0c0a1d48f00.xml, GetEventCallbacks method [Windows Debugging], IDebugClient2 interface, IDebugClient5 interface [Windows Debugging], GetEventCallbacks method, dbgeng/IDebugClient::GetEventCallbacks, dbgeng/IDebugClient3::GetEventCallbacks, dbgeng/IDebugClient5::GetEventCallbacks, debugger.geteventcallbacks, IDebugClient5, GetEventCallbacks, IDebugClient3::GetEventCallbacks, GetEventCallbacks method [Windows Debugging], IDebugClient4 interface, IDebugClient3 interface [Windows Debugging], GetEventCallbacks method, IDebugClient4 interface [Windows Debugging], GetEventCallbacks method, IDebugClient interface [Windows Debugging], GetEventCallbacks method, IDebugClient5::GetEventCallbacks, GetEventCallbacks method [Windows Debugging], IDebugClient5 interface, GetEventCallbacks method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient2::GetEventCallbacks, GetEventCallbacks method [Windows Debugging], IDebugClient2 interface [Windows Debugging], GetEventCallbacks method, IDebugClient4::GetEventCallbacks, dbgeng/IDebugClient4::GetEventCallbacks, IDebugClient::GetEventCallbacks
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient.GetEventCallbacks
-	IDebugClient2.GetEventCallbacks
-	IDebugClient3.GetEventCallbacks
-	IDebugClient4.GetEventCallbacks
-	IDebugClient5.GetEventCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetEventCallbacks method


## -description


The <b>GetEventCallbacks</b>  method returns the event callbacks object registered with this client.


## -syntax


````
HRESULT GetEventCallbacks(
  [out] PDEBUG_EVENT_CALLBACKS *Callbacks
);
````


## -parameters




#### - Callbacks [out]

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

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetEventCallbacks method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

