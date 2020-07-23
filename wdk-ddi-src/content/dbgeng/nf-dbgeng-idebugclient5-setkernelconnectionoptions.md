---
UID: NF:dbgeng.IDebugClient5.SetKernelConnectionOptions
title: IDebugClient5::SetKernelConnectionOptions (dbgeng.h)
description: The SetKernelConnectionOptions method updates some of the connection options for a live kernel target.
old-location: debugger\setkernelconnectionoptions.htm
tech.root: debugger
ms.assetid: 0633c710-20c4-49c0-a680-a5eff9298265
ms.date: 05/03/2018
keywords: ["IDebugClient5::SetKernelConnectionOptions"]
ms.keywords: IDebugClient interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient2 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient2::SetKernelConnectionOptions, IDebugClient3 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient3::SetKernelConnectionOptions, IDebugClient4 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient4::SetKernelConnectionOptions, IDebugClient5 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient5.SetKernelConnectionOptions, IDebugClient5::SetKernelConnectionOptions, IDebugClient::SetKernelConnectionOptions, IDebugClient_b7b26913-d776-41b9-b94a-d5fa685e5fa9.xml, SetKernelConnectionOptions, SetKernelConnectionOptions method [Windows Debugging], SetKernelConnectionOptions method [Windows Debugging],IDebugClient interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient2 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient3 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient4 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetKernelConnectionOptions, dbgeng/IDebugClient3::SetKernelConnectionOptions, dbgeng/IDebugClient4::SetKernelConnectionOptions, dbgeng/IDebugClient5::SetKernelConnectionOptions, dbgeng/IDebugClient::SetKernelConnectionOptions, debugger.setkernelconnectionoptions
f1_keywords:
 - "dbgeng/IDebugClient.SetKernelConnectionOptions"
 - "IDebugClient.SetKernelConnectionOptions"
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
- IDebugClient.SetKernelConnectionOptions
- IDebugClient2.SetKernelConnectionOptions
- IDebugClient3.SetKernelConnectionOptions
- IDebugClient4.SetKernelConnectionOptions
- IDebugClient5.SetKernelConnectionOptions
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetKernelConnectionOptions


## -description


The <b>SetKernelConnectionOptions</b>  method updates some of the connection options for a live kernel target.


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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>
 

 

