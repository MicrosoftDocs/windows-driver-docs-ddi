---
UID: NN:dbgeng.IDebugBreakpoint2
title: IDebugBreakpoint2 (dbgeng.h)
description: IDebugBreakpoint2 interface
old-location: debugger\idebugbreakpoint2.htm
tech.root: debugger
ms.assetid: 097c10e1-fd83-4a3d-8193-873644370e35
ms.date: 05/03/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], IDebugBreakpoint2 interface [Windows Debugging],described, dbgeng/IDebugBreakpoint2, debugger.idebugbreakpoint2
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- IDebugBreakpoint2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugBreakpoint2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a>. <b>IDebugBreakpoint2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugBreakpoint2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545690">GetCommandWide</a>
</td>
<td align="left" width="63%">
Returns the command string that is executed when a breakpoint is triggered.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548053">GetOffsetExpressionWide</a>
</td>
<td align="left" width="63%">
Returns the expression string that evaluates to the location that triggers a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556638">SetCommandWide</a>
</td>
<td align="left" width="63%">
 Sets the command that is executed when a breakpoint is triggered.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556748">SetOffsetExpressionWide</a>
</td>
<td align="left" width="63%">
 Sets an expression string that evaluates to the location that triggers a breakpoint.


</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549812">IDebugBreakpoint</a>
 

 

