---
UID: NF:dbgeng.IDebugSystemObjects3.SetCurrentProcessId
title: IDebugSystemObjects3::SetCurrentProcessId (dbgeng.h)
description: The SetCurrentProcessId method makes the specified process the current process.
old-location: debugger\setcurrentprocessid.htm
tech.root: debugger
ms.assetid: 65129c6e-5c69-409b-95f5-07b98a494533
ms.date: 05/03/2018
ms.keywords: IDebugSystemObjects interface [Windows Debugging],SetCurrentProcessId method, IDebugSystemObjects2 interface [Windows Debugging],SetCurrentProcessId method, IDebugSystemObjects2::SetCurrentProcessId, IDebugSystemObjects3 interface [Windows Debugging],SetCurrentProcessId method, IDebugSystemObjects3.SetCurrentProcessId, IDebugSystemObjects3::SetCurrentProcessId, IDebugSystemObjects4 interface [Windows Debugging],SetCurrentProcessId method, IDebugSystemObjects4::SetCurrentProcessId, IDebugSystemObjects::SetCurrentProcessId, IDebugSystemObjects_e588cabd-e079-4dc0-ab0f-085181414985.xml, SetCurrentProcessId, SetCurrentProcessId method [Windows Debugging], SetCurrentProcessId method [Windows Debugging],IDebugSystemObjects interface, SetCurrentProcessId method [Windows Debugging],IDebugSystemObjects2 interface, SetCurrentProcessId method [Windows Debugging],IDebugSystemObjects3 interface, SetCurrentProcessId method [Windows Debugging],IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::SetCurrentProcessId, dbgeng/IDebugSystemObjects3::SetCurrentProcessId, dbgeng/IDebugSystemObjects4::SetCurrentProcessId, dbgeng/IDebugSystemObjects::SetCurrentProcessId, debugger.setcurrentprocessid
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSystemObjects.SetCurrentProcessId"
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
- IDebugSystemObjects.SetCurrentProcessId
- IDebugSystemObjects2.SetCurrentProcessId
- IDebugSystemObjects3.SetCurrentProcessId
- IDebugSystemObjects4.SetCurrentProcessId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects3::SetCurrentProcessId


## -description


The <b>SetCurrentProcessId</b> method makes the specified process the current process.


## -parameters




### -param Id [in]

Specifies the engine process ID for the process that is to become the current process.


## -returns



This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No process with the given process ID was found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No suitable candidate for the current thread could be found in the process.

</td>
</tr>
</table>
 




## -remarks



This method also changes the current thread, and may change the current target and current computer.

If the process is changed, the callback <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.

<div class="alert"><b>Note</b>    In kernel-mode debugging, the current process is a virtual process, it is not a system process.  This method cannot be used to change between system processes in kernel-mode debugging.  However, the implicit process may be changed by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitprocessdataoffset">SetImplicitProcessDataOffset</a>.</div>
<div> </div>
For more information about processes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/threads-and-processes">Threads and Processes</a>.  For details on monitoring events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.



