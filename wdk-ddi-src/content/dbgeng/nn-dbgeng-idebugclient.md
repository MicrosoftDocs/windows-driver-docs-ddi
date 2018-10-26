---
UID: NN:dbgeng.IDebugClient
title: IDebugClient
author: windows-driver-content
description: IDebugClient interface
old-location: debugger\idebugclient.htm
tech.root: debugger
ms.assetid: 2e47f7ae-2017-4f05-9a06-6c09bb401e21
ms.date: 05/03/2018
ms.keywords: IDebugClient, IDebugClient interface [Windows Debugging], IDebugClient interface [Windows Debugging],described, IDebugClient_3f5f6372-0e7d-4050-b09a-b7776ff8bf7c.xml, dbgeng/IDebugClient, debugger.idebugclient
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
-	IDebugClient
-	IDebugClient.GetOutputWidth
-	IDebugClient.SetOutputWidth
-	IDebugClient.GetOutputLinePrefix
-	IDebugClient.SetOutputLinePrefix
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IDebugClient</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537917">AddProcessOptions</a>
</td>
<td align="left" width="63%">
Adds the process options to those options that affect the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>
</td>
<td align="left" width="63%">
Connects the debugger engine to a kernel target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>
</td>
<td align="left" width="63%">
Connects the debugger engine to a user-mode process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>
</td>
<td align="left" width="63%">
Connects to a process server.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539245">ConnectSession</a>
</td>
<td align="left" width="63%">
Joins the client to an existing debugger session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539320">CreateClient</a>
</td>
<td align="left" width="63%">
Creates a new client object for the current thread.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539321">CreateProcess</a>
</td>
<td align="left" width="63%">
Creates a process from the specified command line.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540048">CreateProcessAndAttach</a>
</td>
<td align="left" width="63%">
 Create a process from a specified command line, then attaches to another user-mode process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541851">DetachProcesses</a>
</td>
<td align="left" width="63%">
Detaches the debugger engine from all processes in all targets, resuming all their threads.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541969">DisconnectProcessServer</a>
</td>
<td align="left" width="63%">
Disconnects the debugger engine from a process server.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a>
</td>
<td align="left" width="63%">
Enables the debugger engine to use the current thread for callbacks.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543004">EndSession</a>
</td>
<td align="left" width="63%">
Ends the current debugger session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543265">ExitDispatch</a>
</td>
<td align="left" width="63%">
Causes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541970">DispatchCallbacks</a> method to return.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545475">FlushCallbacks</a>
</td>
<td align="left" width="63%">
 Forces any remaining buffered output to be delivered to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550801">IDebugOutputCallbacks</a> object registered with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>
</td>
<td align="left" width="63%">
Returns the event callbacks object registered with this client.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546679">GetExitCode</a>
</td>
<td align="left" width="63%">
Returns the exit code of the current process if that process has already run through to completion.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546831">GetIdentity</a>
</td>
<td align="left" width="63%">
Returns a string describing the computer and user this client represents.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546892">GetInputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the input callbacks object registered with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546970">GetKernelConnectionOptions</a>
</td>
<td align="left" width="63%">
Returns the connection options for the current kernel target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>
</td>
<td align="left" width="63%">
Returns the output mask for another client.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>
</td>
<td align="left" width="63%">
Returns the output callbacks object registered with the client.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetOutputLinePrefix</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548080">GetOutputMask</a>
</td>
<td align="left" width="63%">
Returns the output mask currently set for the client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetOutputWidth</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548163">GetProcessOptions</a>
</td>
<td align="left" width="63%">
Retrieves the process options affecting the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>
</td>
<td align="left" width="63%">
Returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548254">GetRunningProcessSystemIdByExecutableName</a>
</td>
<td align="left" width="63%">
 Searches for a process with a given executable file name and return its process ID.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>
</td>
<td align="left" width="63%">
 Returns the process IDs for each running process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>
</td>
<td align="left" width="63%">
Opens a dump file as a debugger target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553219">OutputIdentity</a>
</td>
<td align="left" width="63%">
 Formats and outputs a string describing the computer and user this client represents.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553247">OutputServers</a>
</td>
<td align="left" width="63%">
Lists the servers running on a given computer.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554505">RemoveProcessOptions</a>
</td>
<td align="left" width="63%">
Removes process options from those options that affect the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556671">SetEventCallbacks</a>
</td>
<td align="left" width="63%">
Registers an event callbacks object with this client.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556721">SetInputCallbacks</a>
</td>
<td align="left" width="63%">
Registers an input callbacks object with the client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556729">SetKernelConnectionOptions</a>
</td>
<td align="left" width="63%">
Updates some of the connection options for a live kernel target.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556750">SetOtherOutputMask</a>
</td>
<td align="left" width="63%">
Sets the output mask for another client.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>
</td>
<td align="left" width="63%">
Registers an output callbacks object with this client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetOutputLinePrefix</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>
</td>
<td align="left" width="63%">
Sets the output mask for the client.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetOutputWidth</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556765">SetProcessOptions</a>
</td>
<td align="left" width="63%">
Sets the process options affecting the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558810">StartProcessServer</a>
</td>
<td align="left" width="63%">
Starts a process server.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558813">StartServer</a>
</td>
<td align="left" width="63%">
 Starts a debugging server.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558867">TerminateProcesses</a>
</td>
<td align="left" width="63%">
Attempts to terminate all processes in all targets.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561380">WriteDumpFile</a>
</td>
<td align="left" width="63%">
Creates a user-mode or kernel-mode crash dump file.


</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

