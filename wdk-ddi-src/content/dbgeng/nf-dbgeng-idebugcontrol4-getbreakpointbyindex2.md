---
UID: NF:dbgeng.IDebugControl4.GetBreakpointByIndex2
title: IDebugControl4::GetBreakpointByIndex2 (dbgeng.h)
description: The GetBreakpointByIndex2 method returns the breakpoint located at the specified index.
old-location: debugger\getbreakpointbyindex2.htm
tech.root: debugger
ms.assetid: 3487addb-e196-4295-95fc-0590802e766a
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetBreakpointByIndex2"]
ms.keywords: GetBreakpointByIndex2, GetBreakpointByIndex2 method [Windows Debugging], GetBreakpointByIndex2 method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetBreakpointByIndex2 method, IDebugControl4.GetBreakpointByIndex2, IDebugControl4::GetBreakpointByIndex2, dbgeng/IDebugControl4::GetBreakpointByIndex2, debugger.getbreakpointbyindex2
f1_keywords:
 - "dbgeng/IDebugControl4.GetBreakpointByIndex2"
 - "IDebugControl4.GetBreakpointByIndex2"
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
- IDebugControl4.GetBreakpointByIndex2
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetBreakpointByIndex2


## -description


The <b>GetBreakpointByIndex2</b>  method returns the breakpoint located at the specified index.


## -parameters




### -param Index [in]

Specifies the zero-based index of the breakpoint to return.  This is specific to the current process.  The value of <i>Index</i> should be between zero and the total number of breakpoints minus one. The total number of breakpoints can be determined by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberbreakpoints">GetNumberBreakpoints</a>.


### -param Bp [out]

Receives the returned breakpoint.


## -returns



This method can also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
No breakpoint was found with the given index, or the breakpoint with the given index is private.

</td>
</tr>
</table>
 




## -remarks



The index and returned breakpoint are specific to the current process.  The same index will return a different breakpoint if the current process is changed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberbreakpoints">GetNumberBreakpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

