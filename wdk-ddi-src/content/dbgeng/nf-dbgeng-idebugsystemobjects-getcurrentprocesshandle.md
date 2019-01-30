---
UID: NF:dbgeng.IDebugSystemObjects.GetCurrentProcessHandle
title: IDebugSystemObjects::GetCurrentProcessHandle (dbgeng.h)
description: The GetCurrentProcessHandle method returns the system handle for the current process.
old-location: debugger\getcurrentprocesshandle2.htm
tech.root: debugger
ms.assetid: 87f60064-5722-4b4e-af9b-f1d9009a7551
ms.date: 05/03/2018
ms.keywords: GetCurrentProcessHandle, GetCurrentProcessHandle method [Windows Debugging], GetCurrentProcessHandle method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessHandle method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessHandle method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessHandle method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessHandle method, IDebugSystemObjects.GetCurrentProcessHandle, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessHandle method, IDebugSystemObjects2::GetCurrentProcessHandle, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessHandle method, IDebugSystemObjects3::GetCurrentProcessHandle, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessHandle method, IDebugSystemObjects4::GetCurrentProcessHandle, IDebugSystemObjects::GetCurrentProcessHandle, IDebugSystemObjects_480199cd-20d9-467c-a5c3-42d221f44509.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessHandle, dbgeng/IDebugSystemObjects3::GetCurrentProcessHandle, dbgeng/IDebugSystemObjects4::GetCurrentProcessHandle, dbgeng/IDebugSystemObjects::GetCurrentProcessHandle, debugger.getcurrentprocesshandle2
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
-	IDebugSystemObjects.GetCurrentProcessHandle
-	IDebugSystemObjects2.GetCurrentProcessHandle
-	IDebugSystemObjects3.GetCurrentProcessHandle
-	IDebugSystemObjects4.GetCurrentProcessHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetCurrentProcessHandle


## -description


The <b>GetCurrentProcessHandle</b> method returns the system handle for the current process.


## -parameters




### -param Handle [out]

Receives the system handle of the current process.


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



In kernel-mode debugging, the only process in the target is the virtual process created for the kernel.  In this case, an artificial handle is created.  The artificial handle can only be used with the debugger engine API.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on system handles, see <a href="https://msdn.microsoft.com/3be5c842-d1b6-4c34-8990-e23e2d08dd23">Handles</a>.



