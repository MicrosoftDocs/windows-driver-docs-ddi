---
UID: NF:dbgeng.IDebugControl3.GetCurrentEventIndex
title: IDebugControl3::GetCurrentEventIndex method
author: windows-driver-content
description: The GetCurrentEventIndex method returns the index of the current event within the current list of events for the current target, if such a list exists.
old-location: debugger\getcurrenteventindex.htm
old-project: debugger
ms.assetid: 148cf294-0410-4704-93ce-338529a214ad
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 3, :, C, D, E, G, GetCurrentEventIndex method [Windows Debugging], GetCurrentEventIndex method [Windows Debugging], IDebugControl3 interface, GetCurrentEventIndex,IDebugControl3.GetCurrentEventIndex, I, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetCurrentEventIndex method, IDebugControl3::GetCurrentEventIndex, IDebugControl_7aec300e-651e-46c6-a4e7-d4ed2b9ca674.xml, b, d, dbgeng/IDebugControl3::GetCurrentEventIndex, debugger.getcurrenteventindex, e, g, l, n, o, r, t, u, v, x"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl3.GetCurrentEventIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetCurrentEventIndex method


## -description


The <b>GetCurrentEventIndex</b> method returns the index of the current event within the current list of events for the current target, if such a list exists.


## -syntax


````
HRESULT GetCurrentEventIndex(
  [out] PULONG Index
);
````


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

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556737">SetNextEventIndex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetCurrentEventIndex method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

