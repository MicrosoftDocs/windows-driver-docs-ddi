---
UID: NF:dbgeng.IDebugClient4.AttachKernel
title: IDebugClient4::AttachKernel (dbgeng.h)
description: The AttachKernel methods connect the debugger engine to a kernel target.
old-location: debugger\attachkernel.htm
tech.root: debugger
ms.assetid: eb861179-3567-4654-a702-40ee3319b27a
ms.date: 05/03/2018
ms.keywords: AttachKernel, AttachKernel method [Windows Debugging], AttachKernel method [Windows Debugging],IDebugClient interface, AttachKernel method [Windows Debugging],IDebugClient2 interface, AttachKernel method [Windows Debugging],IDebugClient3 interface, AttachKernel method [Windows Debugging],IDebugClient4 interface, AttachKernel method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],AttachKernel method, IDebugClient2 interface [Windows Debugging],AttachKernel method, IDebugClient2::AttachKernel, IDebugClient3 interface [Windows Debugging],AttachKernel method, IDebugClient3::AttachKernel, IDebugClient4 interface [Windows Debugging],AttachKernel method, IDebugClient4.AttachKernel, IDebugClient4::AttachKernel, IDebugClient5 interface [Windows Debugging],AttachKernel method, IDebugClient5::AttachKernel, IDebugClient::AttachKernel, IDebugClient_9008538b-3492-4952-a18f-b1dd346e887e.xml, dbgeng/IDebugClient2::AttachKernel, dbgeng/IDebugClient3::AttachKernel, dbgeng/IDebugClient4::AttachKernel, dbgeng/IDebugClient5::AttachKernel, dbgeng/IDebugClient::AttachKernel, debugger.attachkernel
f1_keywords:
 - "dbgeng/IDebugClient.AttachKernel"
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
- IDebugClient.AttachKernel
- IDebugClient2.AttachKernel
- IDebugClient3.AttachKernel
- IDebugClient4.AttachKernel
- IDebugClient5.AttachKernel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4::AttachKernel


## -description


The <b>AttachKernel</b>  methods connect the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/d">debugger engine</a> to a kernel target.


## -parameters




### -param Flags [in]

Specifies the flags that control how the debugger attaches to the kernel target.  The possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_ATTACH_KERNEL_CONNECTION

</td>
<td>
Attach to the kernel on the target computer.

</td>
</tr>
<tr>
<td>
DEBUG_ATTACH_EXDI_DRIVER

</td>
<td>
Attach to a kernel by using an eXDI driver.

</td>
</tr>
</table>
 


### -param ConnectOptions [in, optional]

Specifies the connection settings for communicating with the computer running the kernel target.  The interpretation of <i>ConnectOptions</i> depends on the value of <i>Flags</i>.





#### DEBUG_ATTACH_KERNEL_CONNECTION

<i>ConnectOptions</i> will be interpreted the same way as the options that follow the <b>-k</b> switch on the WinDbg and KD command lines.  Environment variables affect <i>ConnectOptions</i> in the same way they affect the <b>-k</b> switch.



#### DEBUG_ATTACH_EXDI_DRIVER

eXDI drivers are not described in this documentation.  If you have an eXDI interface to your hardware probe or hardware simulator, please contact Microsoft for debugging information.


##### - ConnectOptions.DEBUG_ATTACH_EXDI_DRIVER

eXDI drivers are not described in this documentation.  If you have an eXDI interface to your hardware probe or hardware simulator, please contact Microsoft for debugging information.


##### - ConnectOptions.DEBUG_ATTACH_KERNEL_CONNECTION

<i>ConnectOptions</i> will be interpreted the same way as the options that follow the <b>-k</b> switch on the WinDbg and KD command lines.  Environment variables affect <i>ConnectOptions</i> in the same way they affect the <b>-k</b> switch.


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



<div class="alert"><b>Note</b>    The engine doesn't completely attach to the kernel until the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> method has been called.  Only after the kernel has generated an event -- for example, the initial breakpoint -- does it become available in the debugger session.</div>
<div> </div>
For more information about connecting to live kernel-mode targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/live-kernel-mode-targets">Live Kernel-Mode Targets</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-attachprocess">AttachProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-getkernelconnectionoptions">GetKernelConnectionOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-iskerneldebuggerenabled">IsKernelDebuggerEnabled</a>
 

 

