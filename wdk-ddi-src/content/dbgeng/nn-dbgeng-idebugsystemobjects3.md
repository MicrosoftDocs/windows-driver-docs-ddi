---
UID: NN:dbgeng.IDebugSystemObjects3
title: IDebugSystemObjects3
author: windows-driver-content
description: IDebugSystemObjects3 interface
old-location: debugger\idebugsystemobjects3.htm
old-project: Debugger
ms.assetid: 8924c46b-e2b5-473f-aa0c-e755cd9cbbc6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.idebugsystemobjects3, IDebugSystemObjects3 interface [Windows Debugging], IDebugSystemObjects3 interface [Windows Debugging], described, IDebugSystemObjects3, dbgeng/IDebugSystemObjects3
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
-	IDebugSystemObjects3
-	IDebugSystemObjects3.GetCurrentSystemServer
-	IDebugSystemObjects3.GetSystemByServer
-	IDebugSystemObjects3.GetCurrentSystemServerName
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects3 interface


## -description




## -members

The <b>IDebugSystemObjects3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545871">GetCurrentSystemId</a>
</td>
<td align="left" width="63%">
Returns the engine target ID for the current process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetCurrentSystemServer</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetCurrentSystemServerName</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546641">GetEventSystem</a>
</td>
<td align="left" width="63%">
Returns the engine target ID for the target in which the last event occurred.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547978">GetNumberSystems</a>
</td>
<td align="left" width="63%">
Returns the number of targets to which the engine is currently connected.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>GetSystemByServer</b></td>
<td align="left" width="63%">


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549218">GetSystemIdsByIndex</a>
</td>
<td align="left" width="63%">
Returns the engine target IDs for the specified targets.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549364">GetTotalNumberThreadsAndProcesses</a>
</td>
<td align="left" width="63%">
Returns the total number of threads and processes in all the targets the engine is attached to, in addition to the largest number of threads and processes in a target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556647">SetCurrentSystemId</a>
</td>
<td align="left" width="63%">
Makes the specified target the current target.

</td>
</tr>
</table>Returns the engine target ID for the current process.





Returns the engine target ID for the target in which the last event occurred.

Returns the number of targets to which the engine is currently connected.



Returns the engine target IDs for the specified targets.

Returns the total number of threads and processes in all the targets the engine is attached to, in addition to the largest number of threads and processes in a target.

Makes the specified target the current target.

 


## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects2.md">IDebugSystemObjects2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects.md">IDebugSystemObjects</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSystemObjects3 interface%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

