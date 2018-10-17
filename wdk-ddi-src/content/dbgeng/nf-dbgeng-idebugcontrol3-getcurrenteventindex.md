---
UID: NF:dbgeng.IDebugControl3.GetCurrentEventIndex
title: IDebugControl3::GetCurrentEventIndex
author: windows-driver-content
description: The GetCurrentEventIndex method returns the index of the current event within the current list of events for the current target, if such a list exists.
old-location: debugger\getcurrenteventindex.htm
tech.root: debugger
ms.assetid: 148cf294-0410-4704-93ce-338529a214ad
ms.date: 5/3/2018
ms.keywords: GetCurrentEventIndex, GetCurrentEventIndex method [Windows Debugging], GetCurrentEventIndex method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetCurrentEventIndex method, IDebugControl3.GetCurrentEventIndex, IDebugControl3::GetCurrentEventIndex, IDebugControl_7aec300e-651e-46c6-a4e7-d4ed2b9ca674.xml, dbgeng/IDebugControl3::GetCurrentEventIndex, debugger.getcurrenteventindex
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
-	IDebugControl3.GetCurrentEventIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetCurrentEventIndex


## -description


The <b>GetCurrentEventIndex</b> method returns the index of the current event within the current list of events for the current target, if such a list exists.


## -parameters




### -param Index [out]

Receives the index of the current event in the target.  The index will be a number between zero and one less than the number of events returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>.  The index of the first event is zero.


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



Targets that do not have fixed sets of events will always return zero to <i>Index</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556737">SetNextEventIndex</a>
 

 

