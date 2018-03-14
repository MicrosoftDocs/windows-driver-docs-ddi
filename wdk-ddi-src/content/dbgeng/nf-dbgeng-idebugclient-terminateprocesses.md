---
UID: NF:dbgeng.IDebugClient.TerminateProcesses
title: IDebugClient::TerminateProcesses method
author: windows-driver-content
description: The TerminateProcesses method attempts to terminate all processes in all targets.
old-location: debugger\terminateprocesses.htm
old-project: debugger
ms.assetid: e106a176-b7f9-4812-9995-a23246439b23
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient, IDebugClient interface [Windows Debugging], TerminateProcesses method, IDebugClient2 interface [Windows Debugging], TerminateProcesses method, IDebugClient2::TerminateProcesses, IDebugClient3 interface [Windows Debugging], TerminateProcesses method, IDebugClient3::TerminateProcesses, IDebugClient4 interface [Windows Debugging], TerminateProcesses method, IDebugClient4::TerminateProcesses, IDebugClient5 interface [Windows Debugging], TerminateProcesses method, IDebugClient5::TerminateProcesses, IDebugClient::TerminateProcesses, IDebugClient_6bbf21ae-e69b-4f44-a4e7-9b5abe428903.xml, TerminateProcesses method [Windows Debugging], TerminateProcesses method [Windows Debugging], IDebugClient interface, TerminateProcesses method [Windows Debugging], IDebugClient2 interface, TerminateProcesses method [Windows Debugging], IDebugClient3 interface, TerminateProcesses method [Windows Debugging], IDebugClient4 interface, TerminateProcesses method [Windows Debugging], IDebugClient5 interface, TerminateProcesses,IDebugClient.TerminateProcesses, dbgeng/IDebugClient2::TerminateProcesses, dbgeng/IDebugClient3::TerminateProcesses, dbgeng/IDebugClient4::TerminateProcesses, dbgeng/IDebugClient5::TerminateProcesses, dbgeng/IDebugClient::TerminateProcesses, debugger.terminateprocesses
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
-	IDebugClient.TerminateProcesses
-	IDebugClient2.TerminateProcesses
-	IDebugClient3.TerminateProcesses
-	IDebugClient4.TerminateProcesses
-	IDebugClient5.TerminateProcesses
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::TerminateProcesses method


## -description


The <b>TerminateProcesses</b> method attempts to terminate all <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> in all targets.


## -syntax


````
HRESULT TerminateProcesses();
````


## -parameters






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



Only live user-mode processes are terminated by this method.  For other targets, the target is detached from the debugger without terminating.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563855">.kill (Kill Process)</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541851">DetachProcesses</a>



 

 


