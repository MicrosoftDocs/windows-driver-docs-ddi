---
UID: NN:dbgeng.IDebugClient3
title: IDebugClient3
author: windows-driver-content
description: IDebugClient3 interface
old-location: debugger\idebugclient3.htm
tech.root: debugger
ms.assetid: 316a4d8b-4cf6-4270-8d9b-e1ede53d567d
ms.date: 05/03/2018
ms.keywords: IDebugClient3, IDebugClient3 interface [Windows Debugging], IDebugClient3 interface [Windows Debugging],described, dbgeng/IDebugClient3, debugger.idebugclient3
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
-	IDebugClient3
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient3 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugClient3</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>. <b>IDebugClient3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugClient3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540070">CreateProcessAndAttachWide</a>
</td>
<td align="left" width="63%">
Creates a process from a specified command line, then attaches to another user-mode process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540077">CreateProcessWide</a>
</td>
<td align="left" width="63%">
Creates a process from the specified command line.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548250">GetRunningProcessDescriptionWide</a>
</td>
<td align="left" width="63%">
Returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548260">GetRunningProcessSystemIdByExecutableNameWide</a>
</td>
<td align="left" width="63%">
 Searches for a process with a given executable file name and return its process ID.


</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

