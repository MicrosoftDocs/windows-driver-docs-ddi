---
UID: NF:dbgeng.IDebugBreakpoint.GetAdder
title: IDebugBreakpoint::GetAdder (dbgeng.h)
description: The GetAdder method returns the client that owns the breakpoint.
old-location: debugger\getadder.htm
tech.root: debugger
ms.assetid: f57abfc5-d6ae-474b-bea9-bfc53dff7f57
ms.date: 05/03/2018
ms.keywords: ComOther_069dfd81-8ad8-4fe7-95c4-a3499c1b5512.xml, GetAdder, GetAdder method [Windows Debugging], GetAdder method [Windows Debugging],IDebugBreakpoint interface, GetAdder method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetAdder method, IDebugBreakpoint.GetAdder, IDebugBreakpoint2 interface [Windows Debugging],GetAdder method, IDebugBreakpoint2::GetAdder, IDebugBreakpoint::GetAdder, dbgeng/IDebugBreakpoint2::GetAdder, dbgeng/IDebugBreakpoint::GetAdder, debugger.getadder
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
- IDebugBreakpoint.GetAdder
- IDebugBreakpoint2.GetAdder
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint::GetAdder


## -description


The <b>GetAdder</b> method returns the client that owns the breakpoint.


## -parameters




### -param Adder [out]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a> interface pointer to the client object that added the breakpoint.


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



The client that owns the breakpoint is the client that created the breakpoint by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-addbreakpoint">AddBreakpoint</a> method.  A breakpoint might not have an owner. If a breakpoint does not have an owner, <i>Adder</i> is set to <b>NULL</b>.

For more information about how to use breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.



