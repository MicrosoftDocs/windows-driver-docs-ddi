---
UID: NF:dbgeng.IDebugClient5.CreateProcessAndAttach2Wide
title: IDebugClient5::CreateProcessAndAttach2Wide method
author: windows-driver-content
description: The CreateProcessAndAttach2Wide method creates a process from a specified command line, then attach to that process or another user-mode process.
old-location: debugger\createprocessandattach2wide.htm
old-project: debugger
ms.assetid: a1a1170b-9ecc-4432-badd-50847c974469
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugClient5::CreateProcessAndAttach2Wide, IDebugClient5::CreateProcessAndAttach2Wide, debugger.createprocessandattach2wide, IDebugClient5, IDebugClient5 interface [Windows Debugging], CreateProcessAndAttach2Wide method, CreateProcessAndAttach2Wide method [Windows Debugging], CreateProcessAndAttach2Wide method [Windows Debugging], IDebugClient5 interface, CreateProcessAndAttach2Wide
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
-	IDebugClient5.CreateProcessAndAttach2Wide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::CreateProcessAndAttach2Wide method


## -description


The <b>CreateProcessAndAttach2Wide</b> method creates a process from a specified command line, then attach to that process or another user-mode process.


## -syntax


````
HRESULT CreateProcessAndAttach2Wide(
  [in]           ULONG64 Server,
  [in, optional] PWSTR   CommandLine,
  [in]           PVOID   OptionsBuffer,
  [in]           ULONG   OptionsBufferSize,
  [in, optional] PCWSTR  InitialDirectory,
  [in, optional] PCWSTR  Environment,
  [in]           ULONG   ProcessId,
  [in]           ULONG   AttachFlags
);
````


## -parameters




#### - Server [in]

Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to the local process without using a process server.


#### - CommandLine [in, optional]

Specifies the command line to execute to create the new process.  If <i>CommandLine</i> is <b>NULL</b>, no process is created and these methods will use <i>ProcessId</i> to attach to an existing process.


#### - OptionsBuffer [in]

Specifies the process creation options.  <i>OptionsBuffer</i> is a pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_create_process_options.md">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


#### - OptionsBufferSize [in]

Specifies the size of the buffer <i>OptionsBuffer</i>.  This should be set to <b>sizeof(DEBUG_CREATE_PROCESS_OPTIONS)</b>.


#### - InitialDirectory [in, optional]

Specifies the starting directory for the process.  This parameter is used only if <i>CommandLine</i> is not <b>NULL</b>.  If <i>InitialDirectory</i> is <b>NULL</b>, the current directory for the process server is used.


#### - Environment [in, optional]

Specifies an environment block for the new process.  An environment block consists of a null-terminated block of null-terminated strings.  Each string is of the form:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>name=value</pre>
</td>
</tr>
</table></span></div>Note that the last two characters of the environment block are both <b>NULL</b>: one to terminate the string and one to terminate the block.

If <i>Environment</i> is set to <b>NULL</b>, the new process inherits the environment block of the process server.  If the DEBUG_CREATE_PROCESS_THROUGH_RTL flag is set in <i>OptionsBuffer</i>, then <i>Environment</i> must be <b>NULL</b>.


#### - ProcessId [in]

Specifies the process ID of the target process to which the debugger will attach.  If <i>ProcessID</i> is zero, the debugger will attach to the process it created from <i>CommandLine</i>.


#### - AttachFlags [in]

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
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
This is returned if <i>CommandLine</i> is <b>NULL</b> and <i>ProcessId</i> is zero.

</td>
</tr>
</table> 



## -remarks


This method is available only for live user-mode debugging.

If <i>CommandLine</i> is not <b>NULL</b> and <i>ProcessId</i> is not zero, then the engine will create the process in a suspended state.  The engine will resume this newly created process after it successfully connects to the process specified in <i>ProcessId</i>.
<div class="alert"><b>Note</b>    The engine doesn't completely attach to the process until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  Only after the process has generated an event -- for example, the create-process event -- does it become available in the debugger session.</div><div> </div>For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562135">.attach (Attach to Process)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::CreateProcessAndAttach2Wide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

