---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadId
title: IDebugSystemObjects4::GetCurrentThreadId method
author: windows-driver-content
description: The GetCurrentThreadId method returns the engine thread ID for the current thread.
old-location: debugger\getcurrentthreadid.htm
old-project: debugger
ms.assetid: 7062c962-2e82-40e3-81ea-97ac0948e501
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadId method, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects3::GetCurrentThreadId, dbgeng/IDebugSystemObjects2::GetCurrentThreadId, GetCurrentThreadId, IDebugSystemObjects2::GetCurrentThreadId, IDebugSystemObjects_e40e3ab8-b03d-4b1e-805b-ad8ba51ea1c5.xml, IDebugSystemObjects::GetCurrentThreadId, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadId method, dbgeng/IDebugSystemObjects4::GetCurrentThreadId, IDebugSystemObjects4::GetCurrentThreadId, debugger.getcurrentthreadid, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadId method, dbgeng/IDebugSystemObjects::GetCurrentThreadId, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects4, IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadId method, IDebugSystemObjects2, IDebugSystemObjects3, IDebugSystemObjects, GetCurrentThreadId method [Windows Debugging], IDebugSystemObjects3 interface, dbgeng/IDebugSystemObjects3::GetCurrentThreadId
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
-	IDebugSystemObjects.GetCurrentThreadId
-	IDebugSystemObjects2.GetCurrentThreadId
-	IDebugSystemObjects3.GetCurrentThreadId
-	IDebugSystemObjects4.GetCurrentThreadId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects4::GetCurrentThreadId method


## -description


The <b>GetCurrentThreadId</b> method returns the engine thread ID for the current thread.


## -syntax


````
HRESULT GetCurrentThreadId(
  [out] PULONG Id
);
````


## -parameters




### -param Id [out]

Receives the engine thread ID.


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



For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



