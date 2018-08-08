---
UID: NF:dbgeng.IDebugSystemObjects.GetCurrentProcessSystemId
title: IDebugSystemObjects::GetCurrentProcessSystemId
author: windows-driver-content
description: The GetCurrentProcessSystemId method returns the system process ID of the current process.
old-location: debugger\getcurrentprocesssystemid.htm
tech.root: debugger
ms.assetid: 850f2f86-af0d-414a-99d7-d081753c591f
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetCurrentProcessSystemId, GetCurrentProcessSystemId method [Windows Debugging], GetCurrentProcessSystemId method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessSystemId method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessSystemId method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessSystemId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessSystemId method, IDebugSystemObjects.GetCurrentProcessSystemId, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessSystemId method, IDebugSystemObjects2::GetCurrentProcessSystemId, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessSystemId method, IDebugSystemObjects3::GetCurrentProcessSystemId, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessSystemId method, IDebugSystemObjects4::GetCurrentProcessSystemId, IDebugSystemObjects::GetCurrentProcessSystemId, IDebugSystemObjects_e2d8479b-c723-462c-b423-905186bf69e6.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessSystemId, dbgeng/IDebugSystemObjects3::GetCurrentProcessSystemId, dbgeng/IDebugSystemObjects4::GetCurrentProcessSystemId, dbgeng/IDebugSystemObjects::GetCurrentProcessSystemId, debugger.getcurrentprocesssystemid
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
-	IDebugSystemObjects.GetCurrentProcessSystemId
-	IDebugSystemObjects2.GetCurrentProcessSystemId
-	IDebugSystemObjects3.GetCurrentProcessSystemId
-	IDebugSystemObjects4.GetCurrentProcessSystemId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetCurrentProcessSystemId


## -description


The <b>GetCurrentProcessSystemId</b> method returns the system process ID of the current process.


## -parameters




### -param SysId [out]

Receives the system process ID.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>
 




## -remarks



This method is only available in user-mode debugging.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.



