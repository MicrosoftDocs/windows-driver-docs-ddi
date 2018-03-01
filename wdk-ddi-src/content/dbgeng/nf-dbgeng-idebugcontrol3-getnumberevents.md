---
UID: NF:dbgeng.IDebugControl3.GetNumberEvents
title: IDebugControl3::GetNumberEvents method
author: windows-driver-content
description: The GetNumberEvents method returns the number of events for the current target, if the number of events is fixed.
old-location: debugger\getnumberevents.htm
old-project: debugger
ms.assetid: fb570110-a0a5-4a95-9a26-c4e4ada309b2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetNumberEvents method [Windows Debugging], GetNumberEvents method [Windows Debugging], IDebugControl3 interface, GetNumberEvents,IDebugControl3.GetNumberEvents, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetNumberEvents method, IDebugControl3::GetNumberEvents, IDebugControl_520cbec0-e8b3-49d1-9938-a8f496585758.xml, dbgeng/IDebugControl3::GetNumberEvents, debugger.getnumberevents
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl3.GetNumberEvents
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetNumberEvents method


## -description


The <b>GetNumberEvents</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543067">events</a> for the current target, if the number of events is fixed.


## -syntax


````
HRESULT GetNumberEvents(
  [out] PULONG Events
);
````


## -parameters




### -param Events [out]

Receives the number of events stored in the target.  If the target offers multiple events, <i>Events</i> will be set to the number of events available.  Otherwise, <i>Events</i> will be set to one.


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

For more information, see the topic <a href="https://msdn.microsoft.com/library/windows/hardware/ff543075">Event Information</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545755">GetCurrentEventIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556737">SetNextEventIndex</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetNumberEvents method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

