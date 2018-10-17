---
UID: NF:dbgeng.IDebugClient4.CreateProcessAndAttach
title: IDebugClient4::CreateProcessAndAttach
author: windows-driver-content
description: The CreateProcessAndAttach method creates a process from a specified command line, then attach to another user-mode process.
old-location: debugger\createprocessandattach.htm
tech.root: debugger
ms.assetid: 1a92a823-ec50-406f-942c-c64fc820f9af
ms.date: 5/3/2018
ms.keywords: CreateProcessAndAttach, CreateProcessAndAttach method [Windows Debugging], CreateProcessAndAttach method [Windows Debugging],IDebugClient interface, CreateProcessAndAttach method [Windows Debugging],IDebugClient2 interface, CreateProcessAndAttach method [Windows Debugging],IDebugClient3 interface, CreateProcessAndAttach method [Windows Debugging],IDebugClient4 interface, CreateProcessAndAttach method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],CreateProcessAndAttach method, IDebugClient2 interface [Windows Debugging],CreateProcessAndAttach method, IDebugClient2::CreateProcessAndAttach, IDebugClient3 interface [Windows Debugging],CreateProcessAndAttach method, IDebugClient3::CreateProcessAndAttach, IDebugClient4 interface [Windows Debugging],CreateProcessAndAttach method, IDebugClient4.CreateProcessAndAttach, IDebugClient4::CreateProcessAndAttach, IDebugClient5 interface [Windows Debugging],CreateProcessAndAttach method, IDebugClient5::CreateProcessAndAttach, IDebugClient::CreateProcessAndAttach, IDebugClient_5ff3afdf-164e-4f2f-a625-389f3da41d24.xml, dbgeng/IDebugClient2::CreateProcessAndAttach, dbgeng/IDebugClient3::CreateProcessAndAttach, dbgeng/IDebugClient4::CreateProcessAndAttach, dbgeng/IDebugClient5::CreateProcessAndAttach, dbgeng/IDebugClient::CreateProcessAndAttach, debugger.createprocessandattach
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
-	IDebugClient.CreateProcessAndAttach
-	IDebugClient2.CreateProcessAndAttach
-	IDebugClient3.CreateProcessAndAttach
-	IDebugClient4.CreateProcessAndAttach
-	IDebugClient5.CreateProcessAndAttach
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4::CreateProcessAndAttach


## -description


The <b>CreateProcessAndAttach</b>  method creates a process from a specified command line, then attach to another user-mode process.  The created process is suspended and only allowed to execute when the attach has completed.  This allows rough synchronization when debugging both,  client and server processes.


## -parameters




### -param Server [in]

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to the local process without using a process server.


### -param CommandLine [in, optional]

Specifies the command line to execute to create the new process.  If <i>CommandLine</i> is <b>NULL</b>, then no process is created and these methods attach to an existing process, as <a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a> does.


### -param CreateFlags [in]

Specifies the flags to use when creating the process.  For details on these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541464">DEBUG_CREATE_PROCESS_OPTIONS</a>.<b>CreateFlags</b>.


### -param ProcessId [in]

Specifies the process ID of the target process the debugger will attach to.  If <i>ProcessId</i> is zero, the debugger will attach to the process it created from <i>CommandLine</i>.


### -param AttachFlags [in]

Specifies the flags that control how the debugger attaches to the target process.  For details on these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541454">DEBUG_ATTACH_XXX</a>.


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



This method is available only for live user-mode debugging.

If <i>CommandLine</i> is not <b>NULL</b> and <i>ProcessId</i> is not zero, then the engine will create the process in a suspended state.  The engine will resume this newly created process after it successfully connects to the process specified in <i>ProcessId</i>.

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the process until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  Only after the process has generated an event -- for example, the create-process event -- does it become available in the debugger session.</div>
<div> </div>
For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562135">.attach (Attach to Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>
 

 

