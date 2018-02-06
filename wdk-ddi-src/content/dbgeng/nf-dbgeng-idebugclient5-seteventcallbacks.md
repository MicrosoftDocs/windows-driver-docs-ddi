---
UID: NF:dbgeng.IDebugClient5.SetEventCallbacks
title: IDebugClient5::SetEventCallbacks method
author: windows-driver-content
description: The SetEventCallbacks method registers an event callbacks object with this client.
old-location: debugger\seteventcallbacks.htm
old-project: debugger
ms.assetid: c741777b-dfaf-42b0-9dd7-6678281b6359
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetEventCallbacks method, dbgeng/IDebugClient::SetEventCallbacks, dbgeng/IDebugClient2::SetEventCallbacks, SetEventCallbacks method [Windows Debugging], IDebugClient interface, dbgeng/IDebugClient3::SetEventCallbacks, IDebugClient4::SetEventCallbacks, IDebugClient5, SetEventCallbacks, IDebugClient4 interface [Windows Debugging], SetEventCallbacks method, IDebugClient3::SetEventCallbacks, SetEventCallbacks method [Windows Debugging], IDebugClient5 interface, IDebugClient_a234bf28-5dd1-4e92-ab72-aa8d9a3a282b.xml, debugger.seteventcallbacks, IDebugClient5 interface [Windows Debugging], SetEventCallbacks method, SetEventCallbacks method [Windows Debugging], IDebugClient2 interface, IDebugClient3 interface [Windows Debugging], SetEventCallbacks method, IDebugClient::SetEventCallbacks, IDebugClient2::SetEventCallbacks, SetEventCallbacks method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient5::SetEventCallbacks, SetEventCallbacks method [Windows Debugging], IDebugClient2 interface [Windows Debugging], SetEventCallbacks method, SetEventCallbacks method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient4::SetEventCallbacks, IDebugClient5::SetEventCallbacks
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
-	IDebugClient.SetEventCallbacks
-	IDebugClient2.SetEventCallbacks
-	IDebugClient3.SetEventCallbacks
-	IDebugClient4.SetEventCallbacks
-	IDebugClient5.SetEventCallbacks
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient5::SetEventCallbacks method


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

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetEventCallbacks method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

