---
UID: NF:dbgeng.IDebugControl4.GetBreakpointById2
title: IDebugControl4::GetBreakpointById2 (dbgeng.h)
description: The GetBreakpointById2 method returns the breakpoint with the specified breakpoint ID.
old-location: debugger\getbreakpointbyid2.htm
tech.root: debugger
ms.assetid: 110eaa8a-d564-4900-8a08-d081572a5f43
ms.date: 05/03/2018
ms.keywords: GetBreakpointById2, GetBreakpointById2 method [Windows Debugging], GetBreakpointById2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetBreakpointById2 method, IDebugControl4.GetBreakpointById2, IDebugControl4::GetBreakpointById2, dbgeng/IDebugControl4::GetBreakpointById2, debugger.getbreakpointbyid2
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
- IDebugControl4.GetBreakpointById2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetBreakpointById2


## -description


The <b>GetBreakpointById2</b>  method returns the breakpoint with the specified breakpoint ID.


## -parameters




### -param Id [in]

Specifies the breakpoint ID of the breakpoint to return.


### -param Bp [out]

Receives the breakpoint.


## -returns



This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No breakpoint was found with the given ID, or the breakpoint with the specified ID does not belong to the current process, or the breakpoint with the given ID is private (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546791">GetFlags</a>).

</td>
</tr>
</table>
 




## -remarks



If the specified breakpoint does not belong to the current process, the method will fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

