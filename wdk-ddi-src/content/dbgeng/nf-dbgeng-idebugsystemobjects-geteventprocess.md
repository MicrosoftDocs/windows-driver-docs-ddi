---
UID: NF:dbgeng.IDebugSystemObjects.GetEventProcess
title: IDebugSystemObjects::GetEventProcess (dbgeng.h)
description: The GetEventProcess method returns the engine process ID for the process on which the last event occurred.
old-location: debugger\geteventprocess.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects::GetEventProcess"]
ms.keywords: GetEventProcess, GetEventProcess method [Windows Debugging], GetEventProcess method [Windows Debugging],IDebugSystemObjects interface, GetEventProcess method [Windows Debugging],IDebugSystemObjects2 interface, GetEventProcess method [Windows Debugging],IDebugSystemObjects3 interface, GetEventProcess method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging],GetEventProcess method, IDebugSystemObjects.GetEventProcess, IDebugSystemObjects2 interface [Windows Debugging],GetEventProcess method, IDebugSystemObjects2::GetEventProcess, IDebugSystemObjects3 interface [Windows Debugging],GetEventProcess method, IDebugSystemObjects3::GetEventProcess, IDebugSystemObjects4 interface [Windows Debugging],GetEventProcess method, IDebugSystemObjects4::GetEventProcess, IDebugSystemObjects::GetEventProcess, IDebugSystemObjects_04f445d4-e407-4e0c-bd1b-9570ed4f0433.xml, dbgeng/IDebugSystemObjects2::GetEventProcess, dbgeng/IDebugSystemObjects3::GetEventProcess, dbgeng/IDebugSystemObjects4::GetEventProcess, dbgeng/IDebugSystemObjects::GetEventProcess, debugger.geteventprocess
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugSystemObjects::GetEventProcess
 - dbgeng/IDebugSystemObjects::GetEventProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects.GetEventProcess
 - IDebugSystemObjects2.GetEventProcess
 - IDebugSystemObjects3.GetEventProcess
 - IDebugSystemObjects4.GetEventProcess
---

# IDebugSystemObjects::GetEventProcess


## -description

The <b>GetEventProcess</b> method returns the engine process ID for the process on which the last event occurred.

## -parameters

### -param Id 

[out]
Receives the engine process ID.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

In kernel-mode debugging, the engine process ID for the virtual process representing the kernel is returned.

For more information about processes, see <a href="/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details about debugger engine events, see <a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.
