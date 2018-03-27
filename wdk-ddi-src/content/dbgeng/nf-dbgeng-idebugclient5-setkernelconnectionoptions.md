---
UID: NF:dbgeng.IDebugClient5.SetKernelConnectionOptions
title: IDebugClient5::SetKernelConnectionOptions method
author: windows-driver-content
description: The SetKernelConnectionOptions method updates some of the connection options for a live kernel target.
old-location: debugger\setkernelconnectionoptions.htm
old-project: debugger
ms.assetid: 0633c710-20c4-49c0-a680-a5eff9298265
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetKernelConnectionOptions method, IDebugClient2 interface [Windows Debugging], SetKernelConnectionOptions method, IDebugClient2::SetKernelConnectionOptions, IDebugClient3 interface [Windows Debugging], SetKernelConnectionOptions method, IDebugClient3::SetKernelConnectionOptions, IDebugClient4 interface [Windows Debugging], SetKernelConnectionOptions method, IDebugClient4::SetKernelConnectionOptions, IDebugClient5, IDebugClient5 interface [Windows Debugging], SetKernelConnectionOptions method, IDebugClient5::SetKernelConnectionOptions, IDebugClient::SetKernelConnectionOptions, IDebugClient_b7b26913-d776-41b9-b94a-d5fa685e5fa9.xml, SetKernelConnectionOptions method [Windows Debugging], SetKernelConnectionOptions method [Windows Debugging], IDebugClient interface, SetKernelConnectionOptions method [Windows Debugging], IDebugClient2 interface, SetKernelConnectionOptions method [Windows Debugging], IDebugClient3 interface, SetKernelConnectionOptions method [Windows Debugging], IDebugClient4 interface, SetKernelConnectionOptions method [Windows Debugging], IDebugClient5 interface, SetKernelConnectionOptions,IDebugClient5.SetKernelConnectionOptions, dbgeng/IDebugClient2::SetKernelConnectionOptions, dbgeng/IDebugClient3::SetKernelConnectionOptions, dbgeng/IDebugClient4::SetKernelConnectionOptions, dbgeng/IDebugClient5::SetKernelConnectionOptions, dbgeng/IDebugClient::SetKernelConnectionOptions, debugger.setkernelconnectionoptions
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
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::SetKernelConnectionOptions method


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetKernelConnectionOptions method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

