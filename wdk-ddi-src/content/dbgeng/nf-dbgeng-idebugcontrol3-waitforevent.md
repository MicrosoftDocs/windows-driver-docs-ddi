---
UID: NF:dbgeng.IDebugControl3.WaitForEvent
title: IDebugControl3::WaitForEvent method
author: windows-driver-content
description: The WaitForEvent method waits for an event that breaks into the debugger engine application.
old-location: debugger\waitforevent.htm
old-project: debugger
ms.assetid: b7038bcf-2469-4d5f-ac73-0c7835da23c3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugControl interface [Windows Debugging], WaitForEvent method, IDebugControl2 interface [Windows Debugging], WaitForEvent method, IDebugControl2::WaitForEvent, IDebugControl3, IDebugControl3 interface [Windows Debugging], WaitForEvent method, IDebugControl3::WaitForEvent, IDebugControl::WaitForEvent, IDebugControl_19a7d8b3-1f16-400e-bf8f-c782d48b2cf5.xml, WaitForEvent method [Windows Debugging], WaitForEvent method [Windows Debugging], IDebugControl interface, WaitForEvent method [Windows Debugging], IDebugControl2 interface, WaitForEvent method [Windows Debugging], IDebugControl3 interface, WaitForEvent,IDebugControl3.WaitForEvent, dbgeng/IDebugControl2::WaitForEvent, dbgeng/IDebugControl3::WaitForEvent, dbgeng/IDebugControl::WaitForEvent, debugger.waitforevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Winbase.h
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
-	IDebugControl.WaitForEvent
-	IDebugControl2.WaitForEvent
-	IDebugControl3.WaitForEvent
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::WaitForEvent method


## -description


    The <b>WaitForEvent</b> method waits for an event that breaks into the debugger engine application.


## -syntax


````
HRESULT WaitForEvent(
  [in] ULONG Flags,
  [in] ULONG Timeout
);
````


## -parameters




### -param Flags [in]

Set to zero.  There are currently no flags that can be used in this parameter.


### -param Timeout [in]

Specifies how many milliseconds to wait before this method will return.  If <i>Timeout</i> is INFINITE, this method will not return until an event that breaks into the debugger engine application occurs or an exit interrupt is issued.  If the current session has a live kernel target, <i>Timeout</i> must be set to INFINITE.


## -returns



This method may return other error values and the above error values may have additional meanings.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The time-out expired.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An exit interrupt was issued.  The target is not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
Either there is an outstanding request for input, or none of the targets could generate events.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The engine is already waiting for an event.

</td>
</tr>
</table>
 




## -remarks



The method can be called only from the thread that started the debugger session.

When an event occurs, the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> will process the event and call the event callbacks. If one of these callbacks indicates that the event should break into the debugger engine application (by returning DEBUG_STATUS_BREAK), this method will return; otherwise, it will continue waiting for an event.  The event filters can also specify that an event should break into the debugger engine application.  For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539287">Controlling Exceptions and Events</a>.

This method is not re-entrant.  Once it has been called, it cannot be called again on any client until it has returned.  In particular, it cannot be called from the event callbacks, including extensions and commands executed by the callbacks.

If none of the targets are capable of generating events -- for example, all the targets have exited -- this method will end the current session, discard the targets, and then return E_UNEXPECTED.

The constant INFINITE is defined in Winbase.h.

For more information about using <b>WaitForEvent</b> to control the execution flow of the debugger application and targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>. For details on the event callbacks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 


