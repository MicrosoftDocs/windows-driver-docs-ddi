---
UID: NF:dbgeng.IDebugControl3.GetNumberEvents
title: IDebugControl3::GetNumberEvents (dbgeng.h)
description: The GetNumberEvents method returns the number of events for the current target, if the number of events is fixed.
old-location: debugger\getnumberevents.htm
tech.root: debugger
ms.assetid: fb570110-a0a5-4a95-9a26-c4e4ada309b2
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetNumberEvents"]
ms.keywords: GetNumberEvents, GetNumberEvents method [Windows Debugging], GetNumberEvents method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetNumberEvents method, IDebugControl3.GetNumberEvents, IDebugControl3::GetNumberEvents, IDebugControl_520cbec0-e8b3-49d1-9938-a8f496585758.xml, dbgeng/IDebugControl3::GetNumberEvents, debugger.getnumberevents
f1_keywords:
 - "dbgeng/IDebugControl3.GetNumberEvents"
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
- IDebugControl3.GetNumberEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetNumberEvents


## -description


The <b>GetNumberEvents</b> method returns the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/events">events</a> for the current target, if the number of events is fixed.


## -parameters




### -param Events [out]

Receives the number of events stored in the target.  If the target offers multiple events, <i>Events</i> will be set to the number of events available.  Otherwise, <i>Events</i> will be set to one.


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
The method was successful, and <i>Events</i> contains the total number of events possible for the target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but <i>Events</i> contains only the total number of events possible at the current time.  Targets that support variable execution might have different sets of events available at different points during the target's execution.

</td>
</tr>
</table>
 




## -remarks



Crash dump files contain a static list of events; each event represents a snapshot of the target at a particular point in time.  If the current target is a crash dump file, this method sets <i>Events</i> to the number of stored events and returns S_OK.

Live targets generate events dynamically and do not necessarily have a known set of events.  If the current target is a live target with unconstrained number of events, this method sets <i>Events</i> to the number of events currently available and returns S_FALSE.

For more information, see the topic <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-information">Event Information</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getcurrenteventindex">GetCurrentEventIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setnexteventindex">SetNextEventIndex</a>
 

 

