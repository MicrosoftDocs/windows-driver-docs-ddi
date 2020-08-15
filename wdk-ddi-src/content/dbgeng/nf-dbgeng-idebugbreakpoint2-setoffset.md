---
UID: NF:dbgeng.IDebugBreakpoint2.SetOffset
title: IDebugBreakpoint2::SetOffset (dbgeng.h)
description: The SetOffset method sets the location that triggers a breakpoint.
old-location: debugger\setoffset.htm
tech.root: debugger
ms.assetid: 25898500-f16e-4838-854f-5eb299727e2b
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::SetOffset"]
ms.keywords: ComOther_bb0d9a70-c4b5-4883-9dab-37bf04848d8c.xml, IDebugBreakpoint interface [Windows Debugging],SetOffset method, IDebugBreakpoint2 interface [Windows Debugging],SetOffset method, IDebugBreakpoint2.SetOffset, IDebugBreakpoint2::SetOffset, IDebugBreakpoint::SetOffset, SetOffset, SetOffset method [Windows Debugging], SetOffset method [Windows Debugging],IDebugBreakpoint interface, SetOffset method [Windows Debugging],IDebugBreakpoint2 interface, dbgeng/IDebugBreakpoint2::SetOffset, dbgeng/IDebugBreakpoint::SetOffset, debugger.setoffset
f1_keywords:
 - "dbgeng/IDebugBreakpoint.SetOffset"
 - "IDebugBreakpoint.SetOffset"
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
- IDebugBreakpoint.SetOffset
- IDebugBreakpoint2.SetOffset
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2::SetOffset


## -description


The <b>SetOffset</b> method sets the location that triggers a breakpoint.


## -parameters




### -param Offset 
[in]
The location on the target that triggers the breakpoint.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The breakpoint is deferred.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.




## -remarks



For more information about how to use breakpoints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.



