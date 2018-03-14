---
UID: NF:dbgeng.IDebugClient.SetEventCallbacks
title: IDebugClient::SetEventCallbacks method
author: windows-driver-content
description: The SetEventCallbacks method registers an event callbacks object with this client.
old-location: debugger\seteventcallbacks.htm
old-project: debugger
ms.assetid: c741777b-dfaf-42b0-9dd7-6678281b6359
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient, IDebugClient interface [Windows Debugging], SetEventCallbacks method, IDebugClient2 interface [Windows Debugging], SetEventCallbacks method, IDebugClient2::SetEventCallbacks, IDebugClient3 interface [Windows Debugging], SetEventCallbacks method, IDebugClient3::SetEventCallbacks, IDebugClient4 interface [Windows Debugging], SetEventCallbacks method, IDebugClient4::SetEventCallbacks, IDebugClient5 interface [Windows Debugging], SetEventCallbacks method, IDebugClient5::SetEventCallbacks, IDebugClient::SetEventCallbacks, IDebugClient_a234bf28-5dd1-4e92-ab72-aa8d9a3a282b.xml, SetEventCallbacks method [Windows Debugging], SetEventCallbacks method [Windows Debugging], IDebugClient interface, SetEventCallbacks method [Windows Debugging], IDebugClient2 interface, SetEventCallbacks method [Windows Debugging], IDebugClient3 interface, SetEventCallbacks method [Windows Debugging], IDebugClient4 interface, SetEventCallbacks method [Windows Debugging], IDebugClient5 interface, SetEventCallbacks,IDebugClient.SetEventCallbacks, dbgeng/IDebugClient2::SetEventCallbacks, dbgeng/IDebugClient3::SetEventCallbacks, dbgeng/IDebugClient4::SetEventCallbacks, dbgeng/IDebugClient5::SetEventCallbacks, dbgeng/IDebugClient::SetEventCallbacks, debugger.seteventcallbacks
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
-	IDebugClient.SetEventCallbacks
-	IDebugClient2.SetEventCallbacks
-	IDebugClient3.SetEventCallbacks
-	IDebugClient4.SetEventCallbacks
-	IDebugClient5.SetEventCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::SetEventCallbacks method


## -description


The <b>SetEventCallbacks</b> method registers an event callbacks object with this client.


## -syntax


````
HRESULT SetEventCallbacks(
  [in, optional] PDEBUG_EVENT_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [in, optional]

Specifies the interface pointer to the event callbacks object to register with this client.


## -returns



Depending on the implementation of the method <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a> in the object specified by <i>Callbacks</i>, other values may be returned, as described in the Remarks section.

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

Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

The <b>IDebugEventCallbacks</b> interface extends the COM interface <b>IUnknown</b>.  When <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> are successful, they call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this object will be called the next time <b>SetEventCallbacks</b> or <b>SetEventCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 


