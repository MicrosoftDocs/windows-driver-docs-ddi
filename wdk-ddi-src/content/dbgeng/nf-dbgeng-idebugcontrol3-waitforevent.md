---
UID: NF:dbgeng.IDebugControl3.WaitForEvent
title: IDebugControl3::WaitForEvent method
author: windows-driver-content
description: The WaitForEvent method waits for an event that breaks into the debugger engine application.
old-location: debugger\waitforevent.htm
old-project: debugger
ms.assetid: b7038bcf-2469-4d5f-ac73-0c7835da23c3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::WaitForEvent, WaitForEvent
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
req.alt-api: IDebugControl.WaitForEvent,IDebugControl2.WaitForEvent,IDebugControl3.WaitForEvent
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The time-out expired.
<dl>
<dt><b>E_PENDING</b></dt>
</dl>An exit interrupt was issued.  The target is not available.
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>Either there is an outstanding request for input, or none of the targets could generate events.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The engine is already waiting for an event.

 


## -remarks
The method can be called only from the thread that started the debugger session.

When an event occurs, the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> will process the event and call the event callbacks. If one of these callbacks indicates that the event should break into the debugger engine application (by returning DEBUG_STATUS_BREAK), this method will return; otherwise, it will continue waiting for an event.  The event filters can also specify that an event should break into the debugger engine application.  For more information about event filters, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539287">Controlling Exceptions and Events</a>.

This method is not re-entrant.  Once it has been called, it cannot be called again on any client until it has returned.  In particular, it cannot be called from the event callbacks, including extensions and commands executed by the callbacks.

If none of the targets are capable of generating events -- for example, all the targets have exited -- this method will end the current session, discard the targets, and then return E_UNEXPECTED.

The constant INFINITE is defined in Winbase.h.

For more information about using <b>WaitForEvent</b> to control the execution flow of the debugger application and targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>. For details on the event callbacks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::WaitForEvent method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

