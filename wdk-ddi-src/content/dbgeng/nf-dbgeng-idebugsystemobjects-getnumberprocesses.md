---
UID: NF:dbgeng.IDebugSystemObjects.GetNumberProcesses
title: IDebugSystemObjects::GetNumberProcesses (dbgeng.h)
description: The GetNumberProcesses method returns the number of processes for the current target.
old-location: debugger\getnumberprocesses.htm
tech.root: debugger
ms.assetid: bf0c750f-0e29-42d9-a127-953e3d49b969
ms.date: 05/03/2018
ms.keywords: GetNumberProcesses, GetNumberProcesses method [Windows Debugging], GetNumberProcesses method [Windows Debugging],IDebugSystemObjects interface, GetNumberProcesses method [Windows Debugging],IDebugSystemObjects2 interface, GetNumberProcesses method [Windows Debugging],IDebugSystemObjects3 interface, GetNumberProcesses method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetNumberProcesses method, IDebugSystemObjects.GetNumberProcesses, IDebugSystemObjects2 interface [Windows Debugging],GetNumberProcesses method, IDebugSystemObjects2::GetNumberProcesses, IDebugSystemObjects3 interface [Windows Debugging],GetNumberProcesses method, IDebugSystemObjects3::GetNumberProcesses, IDebugSystemObjects4 interface [Windows Debugging],GetNumberProcesses method, IDebugSystemObjects4::GetNumberProcesses, IDebugSystemObjects::GetNumberProcesses, IDebugSystemObjects_28914631-9658-462c-8234-f48bb85efdf6.xml, dbgeng/IDebugSystemObjects2::GetNumberProcesses, dbgeng/IDebugSystemObjects3::GetNumberProcesses, dbgeng/IDebugSystemObjects4::GetNumberProcesses, dbgeng/IDebugSystemObjects::GetNumberProcesses, debugger.getnumberprocesses
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSystemObjects.GetNumberProcesses"
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
- IDebugSystemObjects.GetNumberProcesses
- IDebugSystemObjects2.GetNumberProcesses
- IDebugSystemObjects3.GetNumberProcesses
- IDebugSystemObjects4.GetNumberProcesses
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects::GetNumberProcesses


## -description


The <b>GetNumberProcesses</b> method returns the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-threads-and-processes">processes</a> for the current target.


## -parameters




### -param Number [out]

Receives the number of processes.


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



In kernel-mode debugging, there is only a single virtual process representing the kernel.

In user-mode debugging, the number of processes changes with the create-process and exit-process debugging <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/events">events</a>.

For more information about processes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.



