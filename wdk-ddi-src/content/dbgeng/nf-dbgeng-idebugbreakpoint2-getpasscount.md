---
UID: NF:dbgeng.IDebugBreakpoint2.GetPassCount
title: IDebugBreakpoint2::GetPassCount (dbgeng.h)
description: The GetPassCount method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.
old-location: debugger\getpasscount.htm
tech.root: debugger
ms.assetid: d7abe2aa-a33c-4184-a850-d0efa1e99221
ms.date: 05/03/2018
ms.keywords: ComOther_bf916108-efd7-436f-a89e-a26826e2e258.xml, GetPassCount, GetPassCount method [Windows Debugging], GetPassCount method [Windows Debugging],IDebugBreakpoint interface, GetPassCount method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetPassCount method, IDebugBreakpoint2 interface [Windows Debugging],GetPassCount method, IDebugBreakpoint2.GetPassCount, IDebugBreakpoint2::GetPassCount, IDebugBreakpoint::GetPassCount, dbgeng/IDebugBreakpoint2::GetPassCount, dbgeng/IDebugBreakpoint::GetPassCount, debugger.getpasscount
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugBreakpoint.GetPassCount"
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
- IDebugBreakpoint.GetPassCount
- IDebugBreakpoint2.GetPassCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::GetPassCount


## -description


The <b>GetPassCount</b> method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.


## -parameters




### -param Count [out]

The number of times that the target was originally required to hit the breakpoint before it is triggered.  The number of times that the target was originally required to pass the breakpoint without triggering it is the value that is returned to <i>Count</i>, minus one.


## -returns



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
 

This method can also return error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



The <b>GetPassCount</b> method returns the number of hits that were originally required to trigger the breakpoint. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugbreakpoint2-getcurrentpasscount">GetCurrentPassCount</a> method returns the number of hits that still must occur to trigger the breakpoint. For example, if a breakpoint was created with a pass count of 20, and there have been 5 passes so far, this method <b>GetPassCount</b> returns 20 and <b>GetCurrentPassCount</b> returns 15.

After the target has hit the breakpoint enough times to trigger it, the breakpoint is triggered every time that it is hit, unless you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugbreakpoint2-setpasscount">SetPassCount</a>.  You can also call <b>SetPassCount</b> to change the pass count before the breakpoint has been triggered. This call resets the original pass count and the remaining pass count.

If the debugger executes the code at the breakpoint location while stepping through the code, this execution does not contribute to the number of times that remain before the breakpoint is triggered.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the information that is returned in <i>Count</i>.

For more information about breakpoint properties, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.



