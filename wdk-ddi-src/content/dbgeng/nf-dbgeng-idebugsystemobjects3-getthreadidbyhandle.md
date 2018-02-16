---
UID: NF:dbgeng.IDebugSystemObjects3.GetThreadIdByHandle
title: IDebugSystemObjects3::GetThreadIdByHandle method
author: windows-driver-content
description: The GetThreadIdByHandle method returns the engine thread ID for the specified thread. The thread is specified by its system handle.
old-location: debugger\getthreadidbyhandle.htm
old-project: debugger
ms.assetid: 80962f29-9a11-456b-b083-bd0f4e26e954
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSystemObjects3::GetThreadIdByHandle, IDebugSystemObjects3::GetThreadIdByHandle, IDebugSystemObjects3, dbgeng/IDebugSystemObjects4::GetThreadIdByHandle, GetThreadIdByHandle method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects interface [Windows Debugging], GetThreadIdByHandle method, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdByHandle method, dbgeng/IDebugSystemObjects2::GetThreadIdByHandle, IDebugSystemObjects, IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdByHandle method, IDebugSystemObjects::GetThreadIdByHandle, IDebugSystemObjects4::GetThreadIdByHandle, IDebugSystemObjects_d1cb023a-dd00-42bf-9827-e2ee98878964.xml, debugger.getthreadidbyhandle, IDebugSystemObjects2::GetThreadIdByHandle, GetThreadIdByHandle method [Windows Debugging], IDebugSystemObjects2 interface, dbgeng/IDebugSystemObjects::GetThreadIdByHandle, GetThreadIdByHandle, GetThreadIdByHandle method [Windows Debugging], IDebugSystemObjects4 interface, GetThreadIdByHandle method [Windows Debugging], IDebugSystemObjects3 interface, GetThreadIdByHandle method [Windows Debugging], IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdByHandle method
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
-	IDebugSystemObjects.GetThreadIdByHandle
-	IDebugSystemObjects2.GetThreadIdByHandle
-	IDebugSystemObjects3.GetThreadIdByHandle
-	IDebugSystemObjects4.GetThreadIdByHandle
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects3::GetThreadIdByHandle method


## -description


The <b>GetThreadIdByHandle</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system handle.


## -syntax


````
HRESULT GetThreadIdByHandle(
  [in]  ULONG64 Handle,
  [out] PULONG  Id
);
````


## -parameters




### -param Handle [in]

Specifies the system handle of the thread whose thread ID is requested.


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



In kernel-mode debugging, because the handle is an artificial handle for a processor,  this method returns the engine thread ID for the virtual thread representing that processor.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="https://msdn.microsoft.com/3be5c842-d1b6-4c34-8990-e23e2d08dd23">Handles</a>.



