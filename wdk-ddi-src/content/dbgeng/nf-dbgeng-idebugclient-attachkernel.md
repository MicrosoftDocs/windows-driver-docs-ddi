---
UID: NF:dbgeng.IDebugClient.AttachKernel
title: IDebugClient::AttachKernel method
author: windows-driver-content
description: The AttachKernel methods connect the debugger engine to a kernel target.
old-location: debugger\attachkernel.htm
old-project: debugger
ms.assetid: eb861179-3567-4654-a702-40ee3319b27a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AttachKernel method [Windows Debugging], AttachKernel method [Windows Debugging], IDebugClient interface, AttachKernel method [Windows Debugging], IDebugClient2 interface, AttachKernel method [Windows Debugging], IDebugClient3 interface, AttachKernel method [Windows Debugging], IDebugClient4 interface, AttachKernel method [Windows Debugging], IDebugClient5 interface, AttachKernel,IDebugClient.AttachKernel, IDebugClient, IDebugClient interface [Windows Debugging], AttachKernel method, IDebugClient2 interface [Windows Debugging], AttachKernel method, IDebugClient2::AttachKernel, IDebugClient3 interface [Windows Debugging], AttachKernel method, IDebugClient3::AttachKernel, IDebugClient4 interface [Windows Debugging], AttachKernel method, IDebugClient4::AttachKernel, IDebugClient5 interface [Windows Debugging], AttachKernel method, IDebugClient5::AttachKernel, IDebugClient::AttachKernel, IDebugClient_9008538b-3492-4952-a18f-b1dd346e887e.xml, dbgeng/IDebugClient2::AttachKernel, dbgeng/IDebugClient3::AttachKernel, dbgeng/IDebugClient4::AttachKernel, dbgeng/IDebugClient5::AttachKernel, dbgeng/IDebugClient::AttachKernel, debugger.attachkernel
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
-	IDebugClient.AttachKernel
-	IDebugClient2.AttachKernel
-	IDebugClient3.AttachKernel
-	IDebugClient4.AttachKernel
-	IDebugClient5.AttachKernel
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::AttachKernel method


## -description


The <b>AttachKernel</b>  methods connect the <a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">debugger engine</a> to a kernel target.


## -syntax


````
HRESULT AttachKernel(
  [in]           ULONG Flags,
  [in, optional] PCSTR ConnectOptions
);
````


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



<div class="alert"><b>Note</b>    The engine doesn't completely attach to the kernel until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> method has been called.  Only after the kernel has generated an event -- for example, the initial breakpoint -- does it become available in the debugger session.</div>
<div> </div>
For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551088">IsKernelDebuggerEnabled</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546970">GetKernelConnectionOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::AttachKernel method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

