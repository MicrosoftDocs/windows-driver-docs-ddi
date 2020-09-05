---
UID: NF:dbgeng.IDebugClient5.CreateProcessAndAttach2
title: IDebugClient5::CreateProcessAndAttach2 (dbgeng.h)
description: The CreateProcessAndAttach2 method creates a process from a specified command line, then attaches to that process or another user-mode process.
old-location: debugger\createprocessandattach2.htm
tech.root: debugger
ms.assetid: 2e479563-8ffd-40cd-a584-d34de2530e1d
ms.date: 05/03/2018
keywords: ["IDebugClient5::CreateProcessAndAttach2"]
ms.keywords: CreateProcessAndAttach2, CreateProcessAndAttach2 method [Windows Debugging], CreateProcessAndAttach2 method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],CreateProcessAndAttach2 method, IDebugClient5.CreateProcessAndAttach2, IDebugClient5::CreateProcessAndAttach2, IDebugClient_898e4cd4-45bf-43b8-80be-f761743e7f5c.xml, dbgeng/IDebugClient5::CreateProcessAndAttach2, debugger.createprocessandattach2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugClient5::CreateProcessAndAttach2
 - dbgeng/IDebugClient5::CreateProcessAndAttach2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient5.CreateProcessAndAttach2
---

# IDebugClient5::CreateProcessAndAttach2


## -description

The <b>CreateProcessAndAttach2</b>  method creates a process from a specified command line, then attaches to that process or another user-mode process.

## -parameters

### -param Server 

[in]
Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to the local process without using a process server.

### -param CommandLine 

[in, optional]
Specifies the command line to execute to create the new process.  If <i>CommandLine</i> is <b>NULL</b>, no process is created and these methods will use <i>ProcessId</i> to attach to an existing process.

### -param OptionsBuffer 

[in]
Specifies the process creation options.  <i>OptionsBuffer</i> is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_create_process_options">DEBUG_CREATE_PROCESS_OPTIONS</a> structure.

### -param OptionsBufferSize 

[in]
Specifies the size of the buffer <i>OptionsBuffer</i>.  This should be set to <b>sizeof(DEBUG_CREATE_PROCESS_OPTIONS)</b>.

### -param InitialDirectory 

[in, optional]
Specifies the starting directory for the process.  This parameter is used only if <i>CommandLine</i> is not <b>NULL</b>.  If <i>InitialDirectory</i> is <b>NULL</b>, the current directory for the process server is used.

### -param Environment 

[in, optional]
Specifies an environment block for the new process.  An environment block consists of a null-terminated block of null-terminated strings.  Each string is of the form:


```
name=value
```

Note that the last two characters of the environment block are both <b>NULL</b>: one to terminate the string and one to terminate the block.

If <i>Environment</i> is set to <b>NULL</b>, the new process inherits the environment block of the process server.  If the DEBUG_CREATE_PROCESS_THROUGH_RTL flag is set in <i>OptionsBuffer</i>, then <i>Environment</i> must be <b>NULL</b>.

### -param ProcessId 

[in]
Specifies the process ID of the target process to which the debugger will attach.  If <i>ProcessID</i> is zero, the debugger will attach to the process it created from <i>CommandLine</i>.

### -param AttachFlags 

[in]
Specifies the flags that control how the debugger attaches to the target process.  For details on these flags, see <a href="https://docs.microsoft.com/previous-versions/ff541454(v=vs.85)">DEBUG_ATTACH_XXX</a>.

## -returns

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

<div class="alert"><b>Note</b>    The engine doesn't completely attach to the process until the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> method has been called.  Only after the process has generated an event -- for example, the create-process event -- does it become available in the debugger session.</div>
<div> </div>
For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-attach--attach-to-process-">.attach (Attach to Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-create--create-process-">.create (Create Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-abandoncurrentprocess">AbandonCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-detachcurrentprocess">DetachCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-terminatecurrentprocess">TerminateCurrentProcess</a>

