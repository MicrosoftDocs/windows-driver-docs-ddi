---
UID: NF:dbgeng.IDebugClient5.SetKernelConnectionOptionsWide
title: IDebugClient5::SetKernelConnectionOptionsWide (dbgeng.h)
description: The SetKernelConnectionOptionsWide method updates some of the connection options for a live kernel target.
old-location: debugger\setkernelconnectionoptionswide.htm
tech.root: debugger
ms.assetid: aea5651f-b361-4253-bf51-bd320408bdab
ms.date: 05/03/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],SetKernelConnectionOptionsWide method, IDebugClient5.SetKernelConnectionOptionsWide, IDebugClient5::SetKernelConnectionOptionsWide, SetKernelConnectionOptionsWide, SetKernelConnectionOptionsWide method [Windows Debugging], SetKernelConnectionOptionsWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetKernelConnectionOptionsWide, debugger.setkernelconnectionoptionswide
f1_keywords:
 - "dbgeng/IDebugClient5.SetKernelConnectionOptionsWide"
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
- IDebugClient5.SetKernelConnectionOptionsWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetKernelConnectionOptionsWide


## -description


The <b>SetKernelConnectionOptionsWide</b> method updates some of the connection options for a live kernel target.


## -parameters




### -param Options [in]

Specifies the connection options to update.  The possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
"resync"

</td>
<td>
Re-synchronize the connection between the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> and the kernel.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/synchronizing-with-the-target-computer">Synchronizing with the Target Computer</a>.

</td>
</tr>
<tr>
<td>
"cycle_speed"

</td>
<td>
For kernel connections through a COM port, cycle through the supported baud rates;  for other connections, do nothing.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/ctrl-a--toggle-baud-rate-">CTRL+A (Toggle Baud Rate)</a>.

</td>
</tr>
</table>
 


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
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The current target is not a live (non-local) kernel target.

</td>
</tr>
</table>
 




## -remarks



This method is available only for live kernel targets that are not local and not connected through eXDI.  This method is reentrant.

For more information about connecting to live kernel-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-kernel-mode-targets">Live Kernel-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachkernel">AttachKernel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

