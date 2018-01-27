---
UID: NN:dbgeng.IDebugEventCallbacks
title: IDebugEventCallbacks
author: windows-driver-content
description: IDebugEventCallbacks interface
old-location: debugger\idebugeventcallbacks.htm
old-project: debugger
ms.assetid: f5e51d0e-0967-4e35-b24b-4bd99c975569
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugeventcallbacks, IDebugEventCallbacks interface [Windows Debugging], IDebugEventCallbacks interface [Windows Debugging], described, IDebugEventCallbacks, dbgeng/IDebugEventCallbacks, ComCallbacks_72745555-ec34-41fa-9305-cf23357bcd17.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugEventCallbacks
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugEventCallbacks interface


## -description




## -members

The <b>IDebugEventCallbacks</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/76b9aca2-4630-45e2-bed4-f701018c86a5">Breakpoint</a>
</td>
<td align="left" width="63%">
 This method is called by the engine when the target issues a breakpoint exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/157a420a-18ad-46cf-ae93-603e9226ee4f">ChangeDebuggeeState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when it makes or detects changes to the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/42ad993a-b12e-49ff-8a1f-f62e2ab968d3">ChangeEngineState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when its state has changed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/5383bd49-df44-48dd-8385-c782a1b1f80a">ChangeSymbolState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when the symbol state changes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539321">CreateProcess</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a create-process debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c3b2cbaa-33b9-4784-922d-d1209fc23dfd">CreateThread</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a create-thread debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/93f915ab-1f9e-453c-b76e-8260eecd7298">Exception</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exception debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/050b747e-5570-4e25-81e4-eccdde4f6995">ExitProcess</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exit-process debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/03ff46cb-dfc5-409a-b652-bef8f2b37b59">ExitThread</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exit-thread debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/165c83cb-c0be-4a09-9220-a5208f660308">GetInterestMask</a>
</td>
<td align="left" width="63%">
This method is called to determine which events the <b>IDebugEventCallbacks</b> object is interested in.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/f4efcbf3-f78a-4e0e-9741-4f9b68814e5b">LoadModule</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a module-load debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/127c4e48-87db-4735-8d3d-e01fed6a9cf0">SessionStatus</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a change occurs in the debugger session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/651f5207-36c8-4d46-8305-950efb2365bf">SystemError</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a system error occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2afdaee6-7714-42d4-a402-3cb85ef3b970">UnloadModule</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a module-unload debugging event occurs in the target.

</td>
</tr>
</table> This method is called by the engine when the target issues a breakpoint exception.

This method is called by the engine when it makes or detects changes to the target.

This method is called by the engine when its state has changed.

This method is called by the engine when the symbol state changes.

This method is called by the engine when a create-process debugging event occurs in the target.

This method is called by the engine when a create-thread debugging event occurs in the target.

This method is called by the engine when an exception debugging event occurs in the target.

This method is called by the engine when an exit-process debugging event occurs in the target.

This method is called by the engine when an exit-thread debugging event occurs in the target.

This method is called to determine which events the <b>IDebugEventCallbacks</b> object is interested in.

This method is called by the engine when a module-load debugging event occurs in the target.

This method is called by the engine when a change occurs in the debugger session.

This method is called by the engine when a system error occurs in the target.

This method is called by the engine when a module-unload debugging event occurs in the target.

 


## -remarks


The <a href="..\dbgeng\nn-dbgeng-idebugeventcallbackswide.md">IDebugEventCallbacksWide</a> interface includes Unicode versions of these methods; the Unicode methods share the same names as those used by the methods in <b>IDebugEventCallbacks</b>.



The following <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a> are generated by the target.
<table>
<tr>
<th>Flag</th>
<th>IDebugEventCallbacksMethod </th>
<th>Event Description</th>
</tr>
<tr>
<td>
DEBUG_EVENT_BREAKPOINT

</td>
<td>

<a href="https://msdn.microsoft.com/76b9aca2-4630-45e2-bed4-f701018c86a5">Breakpoint</a>


</td>
<td>
A breakpoint exception occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXCEPTION

</td>
<td>

<a href="https://msdn.microsoft.com/93f915ab-1f9e-453c-b76e-8260eecd7298">Exception</a>


</td>
<td>
An exception debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CREATE_THREAD

</td>
<td>

<a href="https://msdn.microsoft.com/c3b2cbaa-33b9-4784-922d-d1209fc23dfd">CreateThread</a>


</td>
<td>
A create-thread debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXIT_THREAD

</td>
<td>

<a href="https://msdn.microsoft.com/03ff46cb-dfc5-409a-b652-bef8f2b37b59">ExitThread</a>


</td>
<td>
An exit-thread debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CREATE_PROCESS

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539321">CreateProcess</a>


</td>
<td>
A create-process debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXIT_PROCESS

</td>
<td>

<a href="https://msdn.microsoft.com/050b747e-5570-4e25-81e4-eccdde4f6995">ExitProcess</a>


</td>
<td>
An exit-process debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_LOAD_MODULE

</td>
<td>

<a href="https://msdn.microsoft.com/f4efcbf3-f78a-4e0e-9741-4f9b68814e5b">LoadModule</a>


</td>
<td>
A module-load debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_UNLOAD_MODULE

</td>
<td>

<a href="https://msdn.microsoft.com/2afdaee6-7714-42d4-a402-3cb85ef3b970">UnloadModule</a>


</td>
<td>
A module-unload debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_SYSTEM_ERROR

</td>
<td>

<a href="https://msdn.microsoft.com/651f5207-36c8-4d46-8305-950efb2365bf">SystemError</a>


</td>
<td>
A system error occurred in the target.

</td>
</tr>
</table> 

The following events are generated by the debugger engine.
<table>
<tr>
<th>Flag</th>
<th>IDebugEventCallbacksMethod </th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_EVENT_SESSION_STATUS

</td>
<td>

<a href="https://msdn.microsoft.com/127c4e48-87db-4735-8d3d-e01fed6a9cf0">SessionStatus</a>


</td>
<td>
A change has occurred in the session status.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_DEBUGGEE_STATE

</td>
<td>

<a href="https://msdn.microsoft.com/157a420a-18ad-46cf-ae93-603e9226ee4f">ChangeDebuggeeState</a>


</td>
<td>
The engine has made or detected a change in the target status.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_ENGINE_STATE

</td>
<td>

<a href="https://msdn.microsoft.com/42ad993a-b12e-49ff-8a1f-f62e2ab968d3">ChangeEngineState</a>


</td>
<td>
The engine state has changed.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_SYMBOL_STATE

</td>
<td>

<a href="https://msdn.microsoft.com/5383bd49-df44-48dd-8385-c782a1b1f80a">ChangeSymbolState</a>


</td>
<td>
The symbol state has changed.

</td>
</tr>
</table> 


