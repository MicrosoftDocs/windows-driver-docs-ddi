---
UID: NF:dbgeng.IDebugClient5.GetKernelConnectionOptionsWide
title: IDebugClient5::GetKernelConnectionOptionsWide (dbgeng.h)
description: The GetKernelConnectionOptionsWide method returns the connection options for the current kernel target.
old-location: debugger\getkernelconnectionoptionswide.htm
tech.root: debugger
ms.assetid: f85ef2cf-704a-4a7c-aeeb-483a7b1fdc8f
ms.date: 05/03/2018
keywords: ["IDebugClient5::GetKernelConnectionOptionsWide"]
ms.keywords: GetKernelConnectionOptionsWide, GetKernelConnectionOptionsWide method [Windows Debugging], GetKernelConnectionOptionsWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetKernelConnectionOptionsWide method, IDebugClient5.GetKernelConnectionOptionsWide, IDebugClient5::GetKernelConnectionOptionsWide, dbgeng/IDebugClient5::GetKernelConnectionOptionsWide, debugger.getkernelconnectionoptionswide
f1_keywords:
 - "dbgeng/IDebugClient5.GetKernelConnectionOptionsWide"
 - "IDebugClient5.GetKernelConnectionOptionsWide"
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
- IDebugClient5.GetKernelConnectionOptionsWide
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetKernelConnectionOptionsWide


## -description


The <b>GetKernelConnectionOptionsWide</b> method returns the connection options for the current kernel target.


## -parameters




### -param Buffer [out, optional]

Specifies the buffer to receive the connection options.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param OptionsSize [out, optional]

Receives the size in characters of the connection options.  If <i>OptionsSize</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The current target is not a standard live kernel target.

</td>
</tr>
</table>
 




## -remarks



This method is available only for live kernel targets that are not local and not connected through eXDI.

The connection options returned are the same options used to connect to the kernel.

For more information about connecting to live kernel-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-kernel-mode-targets">Live Kernel-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachkernel">AttachKernel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

