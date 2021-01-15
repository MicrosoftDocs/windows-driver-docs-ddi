---
UID: NF:dbgeng.IDebugClient2.IsKernelDebuggerEnabled
title: IDebugClient2::IsKernelDebuggerEnabled (dbgeng.h)
description: The IsKernelDebuggerEnabled method checks whether kernel debugging is enabled for the local kernel.
old-location: debugger\iskerneldebuggerenabled.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient2::IsKernelDebuggerEnabled"]
ms.keywords: IDebugClient2 interface [Windows Debugging],IsKernelDebuggerEnabled method, IDebugClient2.IsKernelDebuggerEnabled, IDebugClient2::IsKernelDebuggerEnabled, IDebugClient3 interface [Windows Debugging],IsKernelDebuggerEnabled method, IDebugClient3::IsKernelDebuggerEnabled, IDebugClient4 interface [Windows Debugging],IsKernelDebuggerEnabled method, IDebugClient4::IsKernelDebuggerEnabled, IDebugClient5 interface [Windows Debugging],IsKernelDebuggerEnabled method, IDebugClient5::IsKernelDebuggerEnabled, IDebugClient_05c5446d-28b4-4d9b-bb20-7dc1746545d6.xml, IsKernelDebuggerEnabled, IsKernelDebuggerEnabled method [Windows Debugging], IsKernelDebuggerEnabled method [Windows Debugging],IDebugClient2 interface, IsKernelDebuggerEnabled method [Windows Debugging],IDebugClient3 interface, IsKernelDebuggerEnabled method [Windows Debugging],IDebugClient4 interface, IsKernelDebuggerEnabled method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::IsKernelDebuggerEnabled, dbgeng/IDebugClient3::IsKernelDebuggerEnabled, dbgeng/IDebugClient4::IsKernelDebuggerEnabled, dbgeng/IDebugClient5::IsKernelDebuggerEnabled, debugger.iskerneldebuggerenabled
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
 - IDebugClient2::IsKernelDebuggerEnabled
 - dbgeng/IDebugClient2::IsKernelDebuggerEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient2::IsKernelDebuggerEnabled
---

# IDebugClient2::IsKernelDebuggerEnabled


## -description

The <b>IsKernelDebuggerEnabled</b> method checks whether kernel debugging is enabled for the local kernel.

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
Kernel debugging is enabled for the local kernel.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
Kernel debugging is not enabled for the local kernel.

</td>
</tr>
</table>

## -remarks

Kernel debugging is available for the local computer if the computer was booted by using the <b>/debug</b> boot switch.  In some Windows installations, <a href="/windows-hardware/drivers/debugger/security-during-kernel-mode-debugging">local kernel debugging</a> is supported when other switches--such as <b>/debugport</b>--are used, but this is not a guaranteed feature of Windows and should not be relied on.  For more information about kernel debugging on a single computer, see <a href="/windows-hardware/drivers/debugger/performing-local-kernel-debugging">Performing Local Kernel Debugging</a>.

For more information about connecting to live kernel-mode targets, see <a href="/windows-hardware/drivers/debugger/live-kernel-mode-targets">Live Kernel-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachkernel">AttachKernel</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>

