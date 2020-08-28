---
UID: NF:dbgeng.IDebugControl2.GetBreakpointByIndex
title: IDebugControl2::GetBreakpointByIndex (dbgeng.h)
description: The GetBreakpointByIndex method returns the breakpoint located at the specified index.
old-location: debugger\getbreakpointbyindex.htm
tech.root: debugger
ms.assetid: 9389536e-30c3-4651-bb1e-2c75741694b2
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetBreakpointByIndex"]
ms.keywords: GetBreakpointByIndex, GetBreakpointByIndex method [Windows Debugging], GetBreakpointByIndex method [Windows Debugging],IDebugControl interface, GetBreakpointByIndex method [Windows Debugging],IDebugControl2 interface, GetBreakpointByIndex method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetBreakpointByIndex method, IDebugControl2 interface [Windows Debugging],GetBreakpointByIndex method, IDebugControl2.GetBreakpointByIndex, IDebugControl2::GetBreakpointByIndex, IDebugControl3 interface [Windows Debugging],GetBreakpointByIndex method, IDebugControl3::GetBreakpointByIndex, IDebugControl::GetBreakpointByIndex, IDebugControl_d290fd1e-da1d-4d02-9503-a3c0f8337cec.xml, dbgeng/IDebugControl2::GetBreakpointByIndex, dbgeng/IDebugControl3::GetBreakpointByIndex, dbgeng/IDebugControl::GetBreakpointByIndex, debugger.getbreakpointbyindex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl2::GetBreakpointByIndex
 - dbgeng/IDebugControl2::GetBreakpointByIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetBreakpointByIndex
 - IDebugControl2.GetBreakpointByIndex
 - IDebugControl3.GetBreakpointByIndex
---

# IDebugControl2::GetBreakpointByIndex


## -description

The <b>GetBreakpointByIndex</b>  method returns the breakpoint located at the specified index.

## -parameters

### -param Index 

[in]
Specifies the zero-based index of the breakpoint to return.  This is specific to the current process.  The value of <i>Index</i> should be between zero and the total number of breakpoints minus one. The total number of breakpoints can be determined by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberbreakpoints">GetNumberBreakpoints</a>.

### -param Bp 

[out]
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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>

