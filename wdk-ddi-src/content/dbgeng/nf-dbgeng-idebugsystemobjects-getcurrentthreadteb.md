---
UID: NF:dbgeng.IDebugSystemObjects.GetCurrentThreadTeb
title: IDebugSystemObjects::GetCurrentThreadTeb method
author: windows-driver-content
description: The GetCurrentThreadTeb method returns the location of the thread environment block (TEB) for the current thread.
old-location: debugger\getcurrentthreadteb.htm
old-project: debugger
ms.assetid: f5acd64c-c5a8-4977-8059-cc0bd12ef0c0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentThreadTeb method [Windows Debugging], GetCurrentThreadTeb method [Windows Debugging], IDebugSystemObjects interface, GetCurrentThreadTeb method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentThreadTeb method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentThreadTeb method [Windows Debugging], IDebugSystemObjects4 interface, GetCurrentThreadTeb,IDebugSystemObjects.GetCurrentThreadTeb, IDebugSystemObjects, IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadTeb method, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadTeb method, IDebugSystemObjects2::GetCurrentThreadTeb, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadTeb method, IDebugSystemObjects3::GetCurrentThreadTeb, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadTeb method, IDebugSystemObjects4::GetCurrentThreadTeb, IDebugSystemObjects::GetCurrentThreadTeb, IDebugSystemObjects_d496c1cf-524f-469f-9cb6-1476f972ae9a.xml, dbgeng/IDebugSystemObjects2::GetCurrentThreadTeb, dbgeng/IDebugSystemObjects3::GetCurrentThreadTeb, dbgeng/IDebugSystemObjects4::GetCurrentThreadTeb, dbgeng/IDebugSystemObjects::GetCurrentThreadTeb, debugger.getcurrentthreadteb
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSystemObjects.GetCurrentThreadTeb
-	IDebugSystemObjects2.GetCurrentThreadTeb
-	IDebugSystemObjects3.GetCurrentThreadTeb
-	IDebugSystemObjects4.GetCurrentThreadTeb
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects::GetCurrentThreadTeb method


## -description


The <b>GetCurrentThreadTeb</b> method returns the location of the thread environment block (TEB) for the current thread.


## -syntax


````
HRESULT GetCurrentThreadTeb(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

Receives the location in the target's virtual address space of the TEB for the current thread.


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



In user-mode debugging, this method provides the same information as <a href="https://msdn.microsoft.com/library/windows/hardware/ff545894">GetCurrentThreadDataOffset</a>.

In kernel-mode debugging, the location returned is of the TEB structure of the system thread that was executing on the processor represented by the current thread when the last event occurred.

<div class="alert"><b>Note</b>    In kernel mode, the current thread is always a virtual thread the debugger created for a processor in the target computer.  Because events may occur in different system threads, the TEB location for a virtual thread may change.</div>
<div> </div>
For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the TEB structure, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.



