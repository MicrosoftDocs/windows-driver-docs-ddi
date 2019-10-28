---
UID: NF:dbgeng.IDebugControl.GetSystemErrorControl
title: IDebugControl::GetSystemErrorControl (dbgeng.h)
description: The GetSystemErrorControl method returns the control values for handling system errors.
old-location: debugger\getsystemerrorcontrol.htm
tech.root: debugger
ms.assetid: 727df033-ddaf-45a7-bdca-51a9ee0404fb
ms.date: 05/03/2018
ms.keywords: GetSystemErrorControl, GetSystemErrorControl method [Windows Debugging], GetSystemErrorControl method [Windows Debugging],IDebugControl interface, GetSystemErrorControl method [Windows Debugging],IDebugControl2 interface, GetSystemErrorControl method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetSystemErrorControl method, IDebugControl.GetSystemErrorControl, IDebugControl2 interface [Windows Debugging],GetSystemErrorControl method, IDebugControl2::GetSystemErrorControl, IDebugControl3 interface [Windows Debugging],GetSystemErrorControl method, IDebugControl3::GetSystemErrorControl, IDebugControl::GetSystemErrorControl, IDebugControl_94595f9e-7e73-4291-a904-49f1a8fbbaa8.xml, dbgeng/IDebugControl2::GetSystemErrorControl, dbgeng/IDebugControl3::GetSystemErrorControl, dbgeng/IDebugControl::GetSystemErrorControl, debugger.getsystemerrorcontrol
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.GetSystemErrorControl"
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
- IDebugControl.GetSystemErrorControl
- IDebugControl2.GetSystemErrorControl
- IDebugControl3.GetSystemErrorControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetSystemErrorControl


## -description


The <b>GetSystemErrorControl</b> method returns the control values for handling system errors.


## -parameters




### -param OutputLevel [out]

Receives the level at which system errors are printed to the engine's output.  If the level of the system error is less than or equal to <i>OutputLevel</i>, the error is printed to the debugger console.


### -param BreakLevel [out]

Receives the level at which system errors break into the debugger.  If the level of the system error is less than or equal to <i>BreakLevel</i>, the error breaks into the debugger.


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



The level of a system error can take one of the following three values, listed from lowest to highest: SLE_ERROR, SLE_MINORERROR, and SLE_WARNING.  These values are defined in Winuser.h.

When a system error occurs, the engine calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">IDebugEventCallbacks::SystemError</a> method of the event callbacks.  If the level is less than or equal to <i>BreakLevel</i>, the error will break into the debugger.  If the level is greater than <i>BreakLevel</i>, the engine will proceed with execution in the target as indicated by the <b>IDebugEventCallbacks::SystemError</b> method calls.  For more information about how the engine proceeds after an event, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/monitoring-events">Monitoring Events</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">IDebugEventCallbacks::SystemError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-setsystemerrorcontrol">SetSystemErrorControl</a>
 

 

