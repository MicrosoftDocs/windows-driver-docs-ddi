---
UID: NF:dbgeng.IDebugClient4.SetKernelConnectionOptions
title: IDebugClient4::SetKernelConnectionOptions
author: windows-driver-content
description: The SetKernelConnectionOptions method updates some of the connection options for a live kernel target.
old-location: debugger\setkernelconnectionoptions.htm
tech.root: debugger
ms.assetid: 0633c710-20c4-49c0-a680-a5eff9298265
ms.date: 5/3/2018
ms.keywords: IDebugClient interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient2 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient2::SetKernelConnectionOptions, IDebugClient3 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient3::SetKernelConnectionOptions, IDebugClient4 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient4.SetKernelConnectionOptions, IDebugClient4::SetKernelConnectionOptions, IDebugClient5 interface [Windows Debugging],SetKernelConnectionOptions method, IDebugClient5::SetKernelConnectionOptions, IDebugClient::SetKernelConnectionOptions, IDebugClient_b7b26913-d776-41b9-b94a-d5fa685e5fa9.xml, SetKernelConnectionOptions, SetKernelConnectionOptions method [Windows Debugging], SetKernelConnectionOptions method [Windows Debugging],IDebugClient interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient2 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient3 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient4 interface, SetKernelConnectionOptions method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient2::SetKernelConnectionOptions, dbgeng/IDebugClient3::SetKernelConnectionOptions, dbgeng/IDebugClient4::SetKernelConnectionOptions, dbgeng/IDebugClient5::SetKernelConnectionOptions, dbgeng/IDebugClient::SetKernelConnectionOptions, debugger.setkernelconnectionoptions
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.SetKernelConnectionOptions
-	IDebugClient2.SetKernelConnectionOptions
-	IDebugClient3.SetKernelConnectionOptions
-	IDebugClient4.SetKernelConnectionOptions
-	IDebugClient5.SetKernelConnectionOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient4::SetKernelConnectionOptions


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
Re-synchronize the connection between the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> and the kernel.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558852">Synchronizing with the Target Computer</a>.

</td>
</tr>
<tr>
<td>
"cycle_speed"

</td>
<td>
For kernel connections through a COM port, cycle through the supported baud rates;  for other connections, do nothing.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540165">CTRL+A (Toggle Baud Rate)</a>.

</td>
</tr>
</table>
 


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

For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

