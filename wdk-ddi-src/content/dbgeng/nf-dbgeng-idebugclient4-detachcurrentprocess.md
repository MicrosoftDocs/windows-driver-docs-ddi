---
UID: NF:dbgeng.IDebugClient4.DetachCurrentProcess
title: IDebugClient4::DetachCurrentProcess (dbgeng.h)
description: The DetachCurrentProcess method detaches the debugger engine from the current process, resuming all its threads.
old-location: debugger\detachcurrentprocess.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient4::DetachCurrentProcess"]
ms.keywords: DetachCurrentProcess, DetachCurrentProcess method [Windows Debugging], DetachCurrentProcess method [Windows Debugging],IDebugClient2 interface, DetachCurrentProcess method [Windows Debugging],IDebugClient3 interface, DetachCurrentProcess method [Windows Debugging],IDebugClient4 interface, DetachCurrentProcess method [Windows Debugging],IDebugClient5 interface, IDebugClient2 interface [Windows Debugging],DetachCurrentProcess method, IDebugClient2::DetachCurrentProcess, IDebugClient3 interface [Windows Debugging],DetachCurrentProcess method, IDebugClient3::DetachCurrentProcess, IDebugClient4 interface [Windows Debugging],DetachCurrentProcess method, IDebugClient4.DetachCurrentProcess, IDebugClient4::DetachCurrentProcess, IDebugClient5 interface [Windows Debugging],DetachCurrentProcess method, IDebugClient5::DetachCurrentProcess, IDebugClient_cee2b21f-2cbf-449d-a2c8-2006e21074db.xml, dbgeng/IDebugClient2::DetachCurrentProcess, dbgeng/IDebugClient3::DetachCurrentProcess, dbgeng/IDebugClient4::DetachCurrentProcess, dbgeng/IDebugClient5::DetachCurrentProcess, debugger.detachcurrentprocess
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
 - IDebugClient4::DetachCurrentProcess
 - dbgeng/IDebugClient4::DetachCurrentProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient2.DetachCurrentProcess
 - IDebugClient3.DetachCurrentProcess
 - IDebugClient4.DetachCurrentProcess
 - IDebugClient5.DetachCurrentProcess
---

# IDebugClient4::DetachCurrentProcess


## -description

The <b>DetachCurrentProcess</b> method detaches the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a> from the current process, resuming all its <a href="/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a>.

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

The target must be running on Windows XP or a later versions of Windows.

For more information about creating and attaching to live user-mode targets, see <a href="/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/debugger/-detach--detach-from-process-">.detach (Detach from Process)</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-abandoncurrentprocess">AbandonCurrentProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-detachprocesses">DetachProcesses</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-terminatecurrentprocess">TerminateCurrentProcess</a>
