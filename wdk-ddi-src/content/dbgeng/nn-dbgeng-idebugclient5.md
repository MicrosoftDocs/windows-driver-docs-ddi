---
UID: NN:dbgeng.IDebugClient5
title: IDebugClient5
author: windows-driver-content
description: IDebugClient5 interface
old-location: debugger\idebugclient5.htm
tech.root: debugger
ms.assetid: 4230fbc2-524a-44b1-a090-011e334629a7
ms.date: 05/03/2018
ms.keywords: IDebugClient5, IDebugClient5 interface [Windows Debugging], IDebugClient5 interface [Windows Debugging],described, dbgeng/IDebugClient5, debugger.idebugclient5
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
-	IDebugClient5
-	IDebugClient5.GetOutputLinePrefixWide
-	IDebugClient5.SetOutputLinePrefixWide
-	IDebugClient5.PushOutputLinePrefix
-	IDebugClient5.PushOutputLinePrefixWide
-	IDebugClient5.PopOutputLinePrefix
-	IDebugClient5.GetQuitLockString
-	IDebugClient5.SetQuitLockString
-	IDebugClient5.GetQuitLockStringWide
-	IDebugClient5.SetQuitLockStringWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient5</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>. <b>IDebugClient5</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538148">AttachKernelWide</a>
</td>
<td align="left" width="63%">
Connects the debugger engine to a kernel target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539240">ConnectProcessServerWide</a>
</td>
<td align="left" width="63%">
Connects to a process server.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>
</td>
<td align="left" width="63%">
Executes the given command to create a new process. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540038">CreateProcess2Wide</a>
</td>
<td align="left" width="63%">
Executes the given command to create a new process. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>
</td>
<td align="left" width="63%">
Creates a process from a specified command line, then attach to that process or another user-mode process. (ANSI version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540062">CreateProcessAndAttach2Wide</a>
</td>
<td align="left" width="63%">
Creates a process from a specified command line, then attach to that process or another user-mode process. (Unicode version)

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546607">GetEventCallbacksWide</a>
</td>
<td align="left" width="63%">
Returns the event callbacks object registered with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546844">GetIdentityWide</a>
</td>
<td align="left" width="63%">
Returns a string describing the computer and user this client represents.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546973">GetKernelConnectionOptionsWide</a>
</td>
<td align="left" width="63%">
Returns the connection options for the current kernel target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547896">GetNumberEventCallbacks</a>
</td>
<td align="left" width="63%">
Returns the  number of event callbacks that are interested in the given events.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547923">GetNumberInputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the number of input callbacks registered over all clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547931">GetNumberOutputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the number of output callbacks registered over all clients.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548074">GetOutputCallbacksWide</a>
</td>
<td align="left" width="63%">
Returns the output callbacks object registered with the client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetOutputLinePrefixWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetQuitLockString</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetQuitLockStringWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553224">OutputIdentityWide</a>
</td>
<td align="left" width="63%">
Formats and outputs a string describing the computer and user this client represents.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553250">OutputServersWide</a>
</td>
<td align="left" width="63%">
Lists the servers running on a given computer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PopOutputLinePrefix</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PushOutputLinePrefix</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>PushOutputLinePrefixWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556674">SetEventCallbacksWide</a>
</td>
<td align="left" width="63%">
Registers an event callbacks object with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556732">SetKernelConnectionOptionsWide</a>
</td>
<td align="left" width="63%">
Updates some of the connection options for a live kernel target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556753">SetOutputCallbacksWide</a>
</td>
<td align="left" width="63%">
Registers an output callbacks object with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetOutputLinePrefixWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetQuitLockString</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetQuitLockStringWide</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558812">StartProcessServerWide</a>
</td>
<td align="left" width="63%">
Starts a process server.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558814">StartServerWide</a>
</td>
<td align="left" width="63%">
Starts a debugging server.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>
 

 

