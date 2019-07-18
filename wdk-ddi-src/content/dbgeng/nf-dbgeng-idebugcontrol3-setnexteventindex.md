---
UID: NF:dbgeng.IDebugControl3.SetNextEventIndex
title: IDebugControl3::SetNextEventIndex (dbgeng.h)
description: The SetNextEventIndex method sets the next event for the current target by selecting the event from the static list of events for the target, if such a list exists.
old-location: debugger\setnexteventindex.htm
tech.root: debugger
ms.assetid: fbff721a-fdd9-4343-b9a9-92f41fb21ba2
ms.date: 05/03/2018
ms.keywords: IDebugControl3 interface [Windows Debugging],SetNextEventIndex method, IDebugControl3.SetNextEventIndex, IDebugControl3::SetNextEventIndex, IDebugControl_9a902b9c-c621-4d71-bae7-d3fd288b1cd8.xml, SetNextEventIndex, SetNextEventIndex method [Windows Debugging], SetNextEventIndex method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl3::SetNextEventIndex, debugger.setnexteventindex
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl3.SetNextEventIndex"
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
- IDebugControl3.SetNextEventIndex
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::SetNextEventIndex


## -description


The <b>SetNextEventIndex</b> method sets the next event for the current target by selecting the event from the static list of events for the target, if such a list exists.


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
 

The resulting index must be greater than zero and one less than the number of events returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberevents">GetNumberEvents</a>.


### -param NextIndex [out]

Receives the index of the next event.  If <i>NextIndex</i> is <b>NULL</b>, this information is not returned.


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



If the specified event is the same as the current event, this method does nothing.  Otherwise,  this method sets the execution status of the target to DEBUG_STATUS_GO (and notifies the event callbacks).  When <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-waitforevent">WaitForEvent</a> is called, the engine will generate the specified event for the event callbacks and set it as the current event.

This method is only useful if the target offers a list of events.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getcurrenteventindex">GetCurrentEventIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberevents">GetNumberEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

