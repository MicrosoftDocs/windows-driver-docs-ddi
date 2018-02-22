---
UID: NF:dbgeng.IDebugClient2.DetachProcesses
title: IDebugClient2::DetachProcesses method
author: windows-driver-content
description: The DetachProcesses method detaches the debugger engine from all processes in all targets, resuming all their threads.
old-location: debugger\detachprocesses.htm
old-project: Debugger
ms.assetid: aa410f46-7bd9-436e-9c97-495f35cff778
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient5 interface [Windows Debugging], DetachProcesses method, IDebugClient4 interface [Windows Debugging], DetachProcesses method, IDebugClient4::DetachProcesses, dbgeng/IDebugClient3::DetachProcesses, DetachProcesses method [Windows Debugging], DetachProcesses method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient5::DetachProcesses, IDebugClient3 interface [Windows Debugging], DetachProcesses method, DetachProcesses method [Windows Debugging], IDebugClient5 interface, DetachProcesses method [Windows Debugging], IDebugClient3 interface, DetachProcesses, IDebugClient, IDebugClient::DetachProcesses, dbgeng/IDebugClient::DetachProcesses, dbgeng/IDebugClient2::DetachProcesses, DetachProcesses method [Windows Debugging], IDebugClient2 interface, IDebugClient_375aab38-2821-4154-911f-1df9e204146c.xml, debugger.detachprocesses, IDebugClient3::DetachProcesses, dbgeng/IDebugClient4::DetachProcesses, IDebugClient2, IDebugClient interface [Windows Debugging], DetachProcesses method, IDebugClient5::DetachProcesses, DetachProcesses method [Windows Debugging], IDebugClient interface, IDebugClient2::DetachProcesses, IDebugClient2 interface [Windows Debugging], DetachProcesses method
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
-	IDebugClient.DetachProcesses
-	IDebugClient2.DetachProcesses
-	IDebugClient3.DetachProcesses
-	IDebugClient4.DetachProcesses
-	IDebugClient5.DetachProcesses
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient2::DetachProcesses method


## -description


The <b>DetachProcesses</b> method detaches the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> from all <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">processes</a> in all targets, resuming all their <a href="https://msdn.microsoft.com/6182ca34-ee5e-47e9-82fe-29266397e3a8">threads</a>.


## -syntax


````
HRESULT DetachProcesses();
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



The targets must be running on Windows XP or a later version of Windows.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562334">.detach (Detach from Process)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558867">TerminateProcesses</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::DetachProcesses method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

