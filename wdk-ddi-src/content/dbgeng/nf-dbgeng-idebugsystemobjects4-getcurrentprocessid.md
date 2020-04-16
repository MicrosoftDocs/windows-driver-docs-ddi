---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessId
title: IDebugSystemObjects4::GetCurrentProcessId (dbgeng.h)
description: The GetCurrentProcessId method returns the engine process ID for the current process.
old-location: debugger\getcurrentprocessid.htm
tech.root: debugger
ms.assetid: 5b256ccb-8f03-4936-8e03-9955c81384a5
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects4::GetCurrentProcessId"]
ms.keywords: GetCurrentProcessId, GetCurrentProcessId method [Windows Debugging], GetCurrentProcessId method [Windows Debugging],IDebugSystemObjects interface, GetCurrentProcessId method [Windows Debugging],IDebugSystemObjects2 interface, GetCurrentProcessId method [Windows Debugging],IDebugSystemObjects3 interface, GetCurrentProcessId method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetCurrentProcessId method, IDebugSystemObjects2 interface [Windows Debugging],GetCurrentProcessId method, IDebugSystemObjects2::GetCurrentProcessId, IDebugSystemObjects3 interface [Windows Debugging],GetCurrentProcessId method, IDebugSystemObjects3::GetCurrentProcessId, IDebugSystemObjects4 interface [Windows Debugging],GetCurrentProcessId method, IDebugSystemObjects4.GetCurrentProcessId, IDebugSystemObjects4::GetCurrentProcessId, IDebugSystemObjects::GetCurrentProcessId, IDebugSystemObjects_9ae912e7-68db-45d0-8129-f55e5b3ee462.xml, dbgeng/IDebugSystemObjects2::GetCurrentProcessId, dbgeng/IDebugSystemObjects3::GetCurrentProcessId, dbgeng/IDebugSystemObjects4::GetCurrentProcessId, dbgeng/IDebugSystemObjects::GetCurrentProcessId, debugger.getcurrentprocessid
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetCurrentProcessId"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSystemObjects.GetCurrentProcessId
- IDebugSystemObjects2.GetCurrentProcessId
- IDebugSystemObjects3.GetCurrentProcessId
- IDebugSystemObjects4.GetCurrentProcessId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects4::GetCurrentProcessId


## -description


The <b>GetCurrentProcessId</b> method returns the engine process ID for the current process.


## -parameters




### -param Id [out]

Receives the engine process ID for the current process.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For more information about processes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



