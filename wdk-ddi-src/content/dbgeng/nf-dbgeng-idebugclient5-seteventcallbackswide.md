---
UID: NF:dbgeng.IDebugClient5.SetEventCallbacksWide
title: IDebugClient5::SetEventCallbacksWide
author: windows-driver-content
description: The SetEventCallbacksWide method registers an event callbacks object with this client.
old-location: debugger\seteventcallbackswide.htm
tech.root: debugger
ms.assetid: f5aecd1f-e0f2-47a9-aa70-767a42fefdff
ms.date: 5/3/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],SetEventCallbacksWide method, IDebugClient5.SetEventCallbacksWide, IDebugClient5::SetEventCallbacksWide, SetEventCallbacksWide, SetEventCallbacksWide method [Windows Debugging], SetEventCallbacksWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetEventCallbacksWide, debugger.seteventcallbackswide
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
-	IDebugClient5.SetEventCallbacksWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetEventCallbacksWide


## -description


The <b>SetEventCallbacksWide</b> method registers an event callbacks object with this client.


## -parameters




### -param Callbacks [in]

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

Each client can have at most one <a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a>.

The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  When <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> are successful, they call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this object will be called the next time <b>SetEventCallbacks</b> or <b>SetEventCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550550">IDebugEventCallbacks</a>
 

 

