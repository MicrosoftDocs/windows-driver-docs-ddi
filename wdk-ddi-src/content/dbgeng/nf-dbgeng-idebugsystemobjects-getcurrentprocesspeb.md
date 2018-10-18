---
UID: NF:dbgeng.IDebugSystemObjects.GetCurrentProcessPeb
title: IDebugSystemObjects::GetCurrentProcessPeb
author: windows-driver-content
description: The GetCurrentProcessPeb method returns the process environment block (PEB) of the current process.
old-location: debugger\getcurrentprocesspeb.htm
tech.root: debugger
ms.assetid: fa1e2915-3cb5-4634-a8fb-0d2d565c1c00
ms.date: 5/3/2018
ms.keywords: GetCurrentProcessPeb, GetCurrentProcessPeb method [Windows Debugging], GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessPeb method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects.GetCurrentProcessPeb, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects2::GetCurrentProcessPeb, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects3::GetCurrentProcessPeb, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessPeb method, IDebugSystemObjects4::GetCurrentProcessPeb, IDebugSystemObjects::GetCurrentProcessPeb, IDebugSystemObjects_fd672d78-9254-4f24-9f10-99a91d825f2e.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects3::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects4::GetCurrentProcessPeb, dbgeng/IDebugSystemObjects::GetCurrentProcessPeb, debugger.getcurrentprocesspeb
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
-	IDebugSystemObjects.GetCurrentProcessPeb
-	IDebugSystemObjects2.GetCurrentProcessPeb
-	IDebugSystemObjects3.GetCurrentProcessPeb
-	IDebugSystemObjects4.GetCurrentProcessPeb
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetCurrentProcessPeb


## -description


The <b>GetCurrentProcessPeb</b> method returns the process environment block (PEB) of the current process.


## -parameters




### -param Offset [out]

Receives the location in the target's virtual address space of the PEB of the current process.


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



In user-mode debugging, this method provides the same information as <a href="https://msdn.microsoft.com/library/windows/hardware/ff545787">GetCurrentProcessDataOffset</a>.

In kernel-mode debugging, the location returned is that of the PEB structure for the system process in which the last event occurred.

<div class="alert"><b>Note</b>    In kernel mode, the current process of the target is always the single virtual process the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> created for the kernel.  However, because events may occur in different system processes, the PEB location returned by this method may change.</div>
<div> </div>
For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



