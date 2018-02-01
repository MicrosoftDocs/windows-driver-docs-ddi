---
UID: NF:dbgeng.IDebugClient5.CreateProcess2
title: IDebugClient5::CreateProcess2 method
author: windows-driver-content
description: The CreateProcess2 method executes the given command to create a new process.
old-location: debugger\createprocess2.htm
old-project: debugger
ms.assetid: 6b10dcec-2c1a-4068-adb2-4f532ec0b897
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: CreateProcess2 method [Windows Debugging], IDebugClient5 interface, CreateProcess2 method [Windows Debugging], dbgeng/IDebugClient5::CreateProcess2, CreateProcess2, IDebugClient_1cf74a01-b7bd-4899-8a17-4fc443ee0fbc.xml, IDebugClient5 interface [Windows Debugging], CreateProcess2 method, debugger.createprocess2, IDebugClient5, IDebugClient5::CreateProcess2
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
-	IDebugClient5.CreateProcess2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::CreateProcess2 method


## -description


The <b>CreateProcess2</b>  method executes the given command to create a new process.


## -syntax


````
HRESULT CreateProcess2(
  [in]           ULONG64 Server,
  [in]           PSTR    CommandLine,
  [in]           PVOID   OptionsBuffer,
  [in]           ULONG   OptionsBufferSize,
  [in, optional] PCSTR   InitialDirectory,
  [in, optional] PCSTR   Environment
);
````


## -parameters




### -param Server [in]

Specifies the process server that will be attached to the process.  If <i>Server</i> is zero, the engine will create the local process without using a process server.


### -param CommandLine [in]

Specifies the command line to execute to create the new process.


### -param OptionsBuffer [in]

Specifies the process creation options.  <i>OptionsBuffer</i> is a pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_create_process_options.md">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.


### -param OptionsBufferSize [in]

Specifies the size of the buffer <i>OptionsBuffer</i>.  This should be set to <b>sizeof(DEBUG_CREATE_PROCESS_OPTIONS)</b>.


### -param InitialDirectory [in, optional]

Specifies the starting directory for the process.  If <i>InitialDirectory</i> is <b>NULL</b>, the current directory for the process server is used.


### -param Environment [in, optional]

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

If <i>CreateFlags</i> contains either of the flags DEBUG_PROCESS or DEBUG_ONLY_THIS_PROCESS, the engine will also attach to the newly created process. This is similar to the behavior of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a> with its argument <i>ProcessId</i> set to zero.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548243">GetRunningProcessDescription</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562280">.create (Create Process)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539323">CreateProcess2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::CreateProcess2 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

