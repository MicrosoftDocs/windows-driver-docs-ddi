---
UID: NF:dbgeng.IDebugClient5.CreateProcessAndAttachWide
title: IDebugClient5::CreateProcessAndAttachWide (dbgeng.h)
description: The CreateProcessAndAttachWide method creates a process from a specified command line, then attach to another user-mode process.
old-location: debugger\createprocessandattachwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient5::CreateProcessAndAttachWide"]
ms.keywords: CreateProcessAndAttachWide, CreateProcessAndAttachWide method [Windows Debugging], CreateProcessAndAttachWide method [Windows Debugging],IDebugClient3 interface, CreateProcessAndAttachWide method [Windows Debugging],IDebugClient4 interface, CreateProcessAndAttachWide method [Windows Debugging],IDebugClient5 interface, IDebugClient3 interface [Windows Debugging],CreateProcessAndAttachWide method, IDebugClient3::CreateProcessAndAttachWide, IDebugClient4 interface [Windows Debugging],CreateProcessAndAttachWide method, IDebugClient4::CreateProcessAndAttachWide, IDebugClient5 interface [Windows Debugging],CreateProcessAndAttachWide method, IDebugClient5.CreateProcessAndAttachWide, IDebugClient5::CreateProcessAndAttachWide, dbgeng/IDebugClient3::CreateProcessAndAttachWide, dbgeng/IDebugClient4::CreateProcessAndAttachWide, dbgeng/IDebugClient5::CreateProcessAndAttachWide, debugger.createprocessandattachwide
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
 - IDebugClient5::CreateProcessAndAttachWide
 - dbgeng/IDebugClient5::CreateProcessAndAttachWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient3.CreateProcessAndAttachWide
 - IDebugClient4.CreateProcessAndAttachWide
 - IDebugClient5.CreateProcessAndAttachWide
---

# IDebugClient5::CreateProcessAndAttachWide


## -description

The <b>CreateProcessAndAttachWide</b> method creates a process from a specified command line, then attach to another user-mode process.  The created process is suspended and only allowed to execute when the attach has completed.  This allows rough synchronization when debugging both,  client and server processes.

## -parameters

### -param Server 

[in]
Specifies the process server to use to attach to the process.  If <i>Server</i> is zero, the engine will connect to the local process without using a process server.

### -param CommandLine 

[in, optional]
Specifies the command line to execute to create the new process.  If <i>CommandLine</i> is <b>NULL</b>, then no process is created and these methods attach to an existing process, as <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a> does.

### -param CreateFlags 

[in]
Specifies the flags to use when creating the process.  For details on these flags, see <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_create_process_options">DEBUG_CREATE_PROCESS_OPTIONS</a>.<b>CreateFlags</b>.

### -param ProcessId 

[in]
Specifies the process ID of the target process the debugger will attach to.  If <i>ProcessId</i> is zero, the debugger will attach to the process it created from <i>CommandLine</i>.

### -param AttachFlags 

[in]
Specifies the flags that control how the debugger attaches to the target process.  For details on these flags, see <a href="/previous-versions/ff541454(v=vs.85)">DEBUG_ATTACH_XXX</a>.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The engine does not completely attach to the process until the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> method has been called.  Only after the process has generated an event -- for example, the create-process event -- does it become available in the debugger session.

For more information about creating and attaching to live user-mode targets, see <a href="/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/debugger/-attach--attach-to-process-">.attach (Attach to Process)</a>



<a href="/windows-hardware/drivers/debugger/-create--create-process-">.create (Create Process)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-abandoncurrentprocess">AbandonCurrentProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-connectprocessserver">ConnectProcessServer</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocess2">CreateProcess2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-detachcurrentprocess">DetachCurrentProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocessdescription">GetRunningProcessDescription</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getrunningprocesssystemids">GetRunningProcessSystemIds</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-terminatecurrentprocess">TerminateCurrentProcess</a>
