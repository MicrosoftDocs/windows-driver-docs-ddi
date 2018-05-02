---
UID: NN:dbgeng.IDebugClient2
title: IDebugClient2
author: windows-driver-content
description: IDebugClient2 interface
old-location: debugger\idebugclient2.htm
old-project: debugger
ms.assetid: 0ea32baa-b318-44ec-8696-a5b42fe73ed1
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient2, IDebugClient2 interface [Windows Debugging], IDebugClient2 interface [Windows Debugging],described, dbgeng/IDebugClient2, debugger.idebugclient2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugClient2
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugClient2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>. <b>IDebugClient2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537786">AbandonCurrentProcess</a>
</td>
<td align="left" width="63%">
Removes the current process from the debugger engine's process list without detaching or terminating the process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>
</td>
<td align="left" width="63%">
Registers additional files containing supporting information that will be used when opening a dump file.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541846">DetachCurrentProcess</a>
</td>
<td align="left" width="63%">
Detaches the debugger engine from the current process, resuming all its threads.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542993">EndProcessServer</a>
</td>
<td align="left" width="63%">
Requests that a process server be shut down.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551088">IsKernelDebuggerEnabled</a>
</td>
<td align="left" width="63%">
Checks whether kernel debugging is enabled for the local kernel.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558866">TerminateCurrentProcess</a>
</td>
<td align="left" width="63%">
 Attempts to terminate the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561230">WaitForProcessServerEnd</a>
</td>
<td align="left" width="63%">
Waits for a local process server to exit.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561382">WriteDumpFile2</a>
</td>
<td align="left" width="63%">
Creates a user-mode or kernel-mode crash dump file.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

