---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentThreadDataOffset
title: IDebugSystemObjects4::GetCurrentThreadDataOffset method
author: windows-driver-content
description: The GetCurrentThreadDataOffset method returns the location of the system data structure for the current thread.
old-location: debugger\getcurrentthreaddataoffset.htm
old-project: debugger
ms.assetid: 7837c049-fdca-4f90-9f38-2ec91ed8703b
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetCurrentThreadDataOffset method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects::GetCurrentThreadDataOffset, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentThreadDataOffset method, debugger.getcurrentthreaddataoffset, GetCurrentThreadDataOffset method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects4::GetCurrentThreadDataOffset, dbgeng/IDebugSystemObjects4::GetCurrentThreadDataOffset, IDebugSystemObjects_5d09a9f7-d6a3-49ed-b872-1b9ee5173d28.xml, GetCurrentThreadDataOffset method [Windows Debugging], IDebugSystemObjects2 interface, IDebugSystemObjects4, IDebugSystemObjects interface [Windows Debugging], GetCurrentThreadDataOffset method, GetCurrentThreadDataOffset method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects::GetCurrentThreadDataOffset, dbgeng/IDebugSystemObjects2::GetCurrentThreadDataOffset, IDebugSystemObjects2::GetCurrentThreadDataOffset, dbgeng/IDebugSystemObjects3::GetCurrentThreadDataOffset, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentThreadDataOffset method, GetCurrentThreadDataOffset method [Windows Debugging], IDebugSystemObjects3::GetCurrentThreadDataOffset, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentThreadDataOffset method, GetCurrentThreadDataOffset
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
-	IDebugSystemObjects.GetCurrentThreadDataOffset
-	IDebugSystemObjects2.GetCurrentThreadDataOffset
-	IDebugSystemObjects3.GetCurrentThreadDataOffset
-	IDebugSystemObjects4.GetCurrentThreadDataOffset
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugSystemObjects4::GetCurrentThreadDataOffset method


## -description


The <b>GetCurrentThreadDataOffset</b> method returns the location of the system data structure for the current thread.


## -syntax


````
HRESULT GetCurrentThreadDataOffset(
  [out] PULONG64 Offset
);
````


## -parameters




### -param Offset [out]

Receives the location of the system data structure for the current thread.


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


In user-mode debugging, the location returned is of the thread environment block (TEB) for the current thread.  This is the same location returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546549">GetCurrentThreadTeb</a>.

In kernel-mode debugging, the location returned is of the KTHREAD structure of the system thread that was executing on the processor represented by the current thread when the last event occurred.
<div class="alert"><b>Note</b>    In kernel mode debugging, the current thread is always a virtual thread the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> created for a processor in the target computer.  Because events may occur in different system threads, the KTHREAD location for a virtual thread may change.</div><div> </div>For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD and TEB structures, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.


