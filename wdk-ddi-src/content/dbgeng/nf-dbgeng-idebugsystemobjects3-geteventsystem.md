---
UID: NF:dbgeng.IDebugSystemObjects3.GetEventSystem
title: IDebugSystemObjects3::GetEventSystem (dbgeng.h)
description: The GetEventSystem method returns the engine target ID for the target in which the last event occurred.
old-location: debugger\geteventsystem.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetEventSystem"]
ms.keywords: GetEventSystem, GetEventSystem method [Windows Debugging], GetEventSystem method [Windows Debugging],IDebugSystemObjects3 interface, GetEventSystem method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetEventSystem method, IDebugSystemObjects3.GetEventSystem, IDebugSystemObjects3::GetEventSystem, IDebugSystemObjects4 interface [Windows Debugging],GetEventSystem method, IDebugSystemObjects4::GetEventSystem, IDebugSystemObjects_6cb96e5a-e9a5-4ff7-9f36-a7770bc77ef1.xml, dbgeng/IDebugSystemObjects3::GetEventSystem, dbgeng/IDebugSystemObjects4::GetEventSystem, debugger.geteventsystem
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
 - IDebugSystemObjects3::GetEventSystem
 - dbgeng/IDebugSystemObjects3::GetEventSystem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects3::GetEventSystem
---

# IDebugSystemObjects3::GetEventSystem


## -description

The <b>GetEventSystem</b> method returns the engine target ID for the target in which the last event occurred.

## -parameters

### -param Id 

[out]
Receives the engine target ID.

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

## -see-also

<a href="/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>



<a href="/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>

