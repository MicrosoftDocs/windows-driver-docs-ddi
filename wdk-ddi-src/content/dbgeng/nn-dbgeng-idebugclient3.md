---
UID: NN:dbgeng.IDebugClient3
title: IDebugClient3
author: windows-driver-content
description: IDebugClient3 interface
old-location: debugger\idebugclient3.htm
old-project: Debugger
ms.assetid: 316a4d8b-4cf6-4270-8d9b-e1ede53d567d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.idebugclient3, IDebugClient3 interface [Windows Debugging], IDebugClient3 interface [Windows Debugging], described, IDebugClient3, dbgeng/IDebugClient3
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
-	IDebugClient3
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient3 interface


## -description




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
</table>Creates a process from a specified command line, then attaches to another user-mode process.

Creates a process from the specified command line.

Returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.


 Searches for a process with a given executable file name and return its process ID.


 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient3 interface%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

