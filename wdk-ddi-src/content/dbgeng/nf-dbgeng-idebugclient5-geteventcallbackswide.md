---
UID: NF:dbgeng.IDebugClient5.GetEventCallbacksWide
title: IDebugClient5::GetEventCallbacksWide
author: windows-driver-content
description: The GetEventCallbacksWide method returns the event callbacks object registered with this client.
old-location: debugger\geteventcallbackswide.htm
old-project: debugger
ms.assetid: 254eb89f-c330-4fca-8c58-6dbe56861743
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetEventCallbacksWide, GetEventCallbacksWide method [Windows Debugging], GetEventCallbacksWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetEventCallbacksWide method, IDebugClient5.GetEventCallbacksWide, IDebugClient5::GetEventCallbacksWide, dbgeng/IDebugClient5::GetEventCallbacksWide, debugger.geteventcallbackswide
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
-	IDebugClient5.GetEventCallbacksWide
product: Windows
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



Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

If no event callbacks object is registered with the client, the value of <i>Callbacks</i> will be set to <b>NULL</b>.

The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  Before returning the <b>IDebugEventCallbacksWide</b> object specified by <i>Callbacks</i>, the engine calls its <b>IUnknown::AddRef</b> method.  When this object is no longer needed, its <b>IUnknown::Release</b> method should be called. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>
 

 

