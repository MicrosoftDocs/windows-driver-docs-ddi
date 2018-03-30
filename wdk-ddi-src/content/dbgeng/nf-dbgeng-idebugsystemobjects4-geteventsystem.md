---
UID: NF:dbgeng.IDebugSystemObjects4.GetEventSystem
title: IDebugSystemObjects4::GetEventSystem method
author: windows-driver-content
description: The GetEventSystem method returns the engine target ID for the target in which the last event occurred.
old-location: debugger\geteventsystem.htm
old-project: debugger
ms.assetid: b0a3ce92-b29a-4c5e-8cab-18fc92787e2e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetEventSystem method [Windows Debugging], GetEventSystem method [Windows Debugging], IDebugSystemObjects3 interface, GetEventSystem method [Windows Debugging], IDebugSystemObjects4 interface, GetEventSystem,IDebugSystemObjects4.GetEventSystem, IDebugSystemObjects3 interface [Windows Debugging], GetEventSystem method, IDebugSystemObjects3::GetEventSystem, IDebugSystemObjects4, IDebugSystemObjects4 interface [Windows Debugging], GetEventSystem method, IDebugSystemObjects4::GetEventSystem, IDebugSystemObjects_6cb96e5a-e9a5-4ff7-9f36-a7770bc77ef1.xml, dbgeng/IDebugSystemObjects3::GetEventSystem, dbgeng/IDebugSystemObjects4::GetEventSystem, debugger.geteventsystem
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
-	IDebugSystemObjects3.GetEventSystem
-	IDebugSystemObjects4.GetEventSystem
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSystemObjects4::GetEventSystem method


## -description


The <b>GetEventSystem</b> method returns the engine target ID for the target in which the last event occurred.


## -parameters




### -param Id [out]

Receives the engine target ID.


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
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550892">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550893">IDebugSystemObjects4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>
 

 

