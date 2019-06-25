---
UID: NF:dbgeng.IDebugControl2.SetEventFilterCommand
title: IDebugControl2::SetEventFilterCommand (dbgeng.h)
description: The SetEventFilterCommand method sets a debugger command for the engine to execute when a specified event occurs.
old-location: debugger\seteventfiltercommand.htm
tech.root: debugger
ms.assetid: d68d0a98-ec93-4643-a6c1-eff9d5618e03
ms.date: 05/03/2018
ms.keywords: IDebugControl interface [Windows Debugging],SetEventFilterCommand method, IDebugControl2 interface [Windows Debugging],SetEventFilterCommand method, IDebugControl2.SetEventFilterCommand, IDebugControl2::SetEventFilterCommand, IDebugControl3 interface [Windows Debugging],SetEventFilterCommand method, IDebugControl3::SetEventFilterCommand, IDebugControl::SetEventFilterCommand, IDebugControl_b0661dd4-9ecd-49ac-93e1-86d3c6c2c3f6.xml, SetEventFilterCommand, SetEventFilterCommand method [Windows Debugging], SetEventFilterCommand method [Windows Debugging],IDebugControl interface, SetEventFilterCommand method [Windows Debugging],IDebugControl2 interface, SetEventFilterCommand method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::SetEventFilterCommand, dbgeng/IDebugControl3::SetEventFilterCommand, dbgeng/IDebugControl::SetEventFilterCommand, debugger.seteventfiltercommand
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.SetEventFilterCommand
- IDebugControl2.SetEventFilterCommand
- IDebugControl3.SetEventFilterCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::SetEventFilterCommand


## -description


The <b>SetEventFilterCommand</b>  method sets a debugger command for the engine to execute when a specified event occurs.


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <b>GetNumberEventFilters</b> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Command [in]

Specifies the debugger command for the engine to execute when the event occurs.


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



For more information about event filters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-geteventfiltercommand">GetEventFilterCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setexceptionfiltersecondcommand">SetExceptionFilterSecondCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

