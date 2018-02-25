---
UID: NF:dbgeng.IDebugControl3.SetNextEventIndex
title: IDebugControl3::SetNextEventIndex method
author: windows-driver-content
description: The SetNextEventIndex method sets the next event for the current target by selecting the event from the static list of events for the target, if such a list exists.
old-location: debugger\setnexteventindex.htm
old-project: debugger
ms.assetid: fbff721a-fdd9-4343-b9a9-92f41fb21ba2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, C, D, E, I, IDebugControl3, IDebugControl3 interface [Windows Debugging], SetNextEventIndex method, IDebugControl3::SetNextEventIndex, IDebugControl_9a902b9c-c621-4d71-bae7-d3fd288b1cd8.xml, N, S, SetNextEventIndex method [Windows Debugging], SetNextEventIndex method [Windows Debugging], IDebugControl3 interface, SetNextEventIndex,IDebugControl3.SetNextEventIndex, b, d, dbgeng/IDebugControl3::SetNextEventIndex, debugger.setnexteventindex, e, g, l, n, o, r, t, u, v, x"
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
-	IDebugControl3.SetNextEventIndex
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::SetNextEventIndex method


## -description


The <b>SetNextEventIndex</b> method sets the next event for the current target by selecting the event from the static list of events for the target, if such a list exists.


## -syntax


````
HRESULT SetNextEventIndex(
  [in]  ULONG  Relation,
  [in]  ULONG  Value,
  [out] PULONG NextIndex
);
````


## -parameters




### -param Relation [in]

Specifies how to interpret <i>Value</i> when setting the index of the next event.  Possible values are: DEBUG_EINDEX_FROM_START, DEBUG_EINDEX_FROM_END, and DEBUG_EINDEX_FROM_CURRENT.


### -param Value [in]

Specifies the index of the next event relative to the first, last, or current event.  The interpretation of <i>Value</i> depends on the value of <i>Relation</i>, as follows.

<table>
<tr>
<th>Value of <i>Relation</i></th>
<th>Next Event Index</th>
</tr>
<tr>
<td>
DEBUG_EINDEX_FROM_START

</td>
<td>
<i>Value</i>.

</td>
</tr>
<tr>
<td>
DEBUG_EINDEX_FROM_END

</td>
<td>
Number of events minus <i>Value</i>.

</td>
</tr>
<tr>
<td>
DEBUG_EINDEX_FROM_CURRENT

</td>
<td>
The current event index plus <i>Value</i>.

</td>
</tr>
</table>
 

The resulting index must be greater than zero and one less than the number of events returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>.


### -param NextIndex [out]

Receives the index of the next event.  If <i>NextIndex</i> is <b>NULL</b>, this information is not returned.


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



If the specified event is the same as the current event, this method does nothing.  Otherwise,  this method sets the execution status of the target to DEBUG_STATUS_GO (and notifies the event callbacks).  When <a href="https://msdn.microsoft.com/library/windows/hardware/ff561229">WaitForEvent</a> is called, the engine will generate the specified event for the event callbacks and set it as the current event.

This method is only useful if the target offers a list of events.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545755">GetCurrentEventIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::SetNextEventIndex method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

