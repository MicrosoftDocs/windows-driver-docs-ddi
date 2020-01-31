---
UID: NF:dbgeng.IDebugClient3.DetachProcesses
title: IDebugClient3::DetachProcesses (dbgeng.h)
description: The DetachProcesses method detaches the debugger engine from all processes in all targets, resuming all their threads.
old-location: debugger\detachprocesses.htm
tech.root: debugger
ms.assetid: aa410f46-7bd9-436e-9c97-495f35cff778
ms.date: 05/03/2018
ms.keywords: DetachProcesses, DetachProcesses method [Windows Debugging], DetachProcesses method [Windows Debugging],IDebugClient interface, DetachProcesses method [Windows Debugging],IDebugClient2 interface, DetachProcesses method [Windows Debugging],IDebugClient3 interface, DetachProcesses method [Windows Debugging],IDebugClient4 interface, DetachProcesses method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],DetachProcesses method, IDebugClient2 interface [Windows Debugging],DetachProcesses method, IDebugClient2::DetachProcesses, IDebugClient3 interface [Windows Debugging],DetachProcesses method, IDebugClient3.DetachProcesses, IDebugClient3::DetachProcesses, IDebugClient4 interface [Windows Debugging],DetachProcesses method, IDebugClient4::DetachProcesses, IDebugClient5 interface [Windows Debugging],DetachProcesses method, IDebugClient5::DetachProcesses, IDebugClient::DetachProcesses, IDebugClient_375aab38-2821-4154-911f-1df9e204146c.xml, dbgeng/IDebugClient2::DetachProcesses, dbgeng/IDebugClient3::DetachProcesses, dbgeng/IDebugClient4::DetachProcesses, dbgeng/IDebugClient5::DetachProcesses, dbgeng/IDebugClient::DetachProcesses, debugger.detachprocesses
f1_keywords:
 - "dbgeng/IDebugClient.DetachProcesses"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugClient.DetachProcesses
- IDebugClient2.DetachProcesses
- IDebugClient3.DetachProcesses
- IDebugClient4.DetachProcesses
- IDebugClient5.DetachProcesses
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3::DetachProcesses


## -description


The <b>DetachProcesses</b> method detaches the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> from all <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">processes</a> in all targets, resuming all their <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">threads</a>.


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
</table>
 




## -remarks



The targets must be running on Windows XP or a later version of Windows.

For more information about creating and attaching to live user-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-detach--detach-from-process-">.detach (Detach from Process)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-createprocessandattach2">CreateProcessAndAttach2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-detachcurrentprocess">DetachCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-terminateprocesses">TerminateProcesses</a>
 

 

