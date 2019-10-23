---
UID: NN:dbgeng.IDebugBreakpoint
title: IDebugBreakpoint (dbgeng.h)
description: IDebugBreakpoint interface
old-location: debugger\idebugbreakpoint.htm
tech.root: debugger
ms.assetid: ad4bcabb-304e-4427-9b0d-2e22429e8cdd
ms.date: 05/03/2018
ms.keywords: ComOther_93345db9-13c0-4b46-be4a-d3fbb6039cc7.xml, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], IDebugBreakpoint interface [Windows Debugging],described, dbgeng/IDebugBreakpoint, debugger.idebugbreakpoint
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugBreakpoint"
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
- IDebugBreakpoint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugBreakpoint interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugBreakpoint</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugBreakpoint</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugBreakpoint</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-addflags">AddFlags</a>
</td>
<td align="left" width="63%">
Adds flags to a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getadder">GetAdder</a>
</td>
<td align="left" width="63%">
Returns the client that owns the breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getcommand">GetCommand</a>
</td>
<td align="left" width="63%">
Returns the command string that is executed when a breakpoint is triggered.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getcurrentpasscount">GetCurrentPassCount</a>
</td>
<td align="left" width="63%">
Returns the remaining number of times that the target must reach the breakpoint location before the breakpoint is triggered.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getdataparameters">GetDataParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for a processor breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getflags">GetFlags</a>
</td>
<td align="left" width="63%">
Returns the flags for a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getid">GetId</a>
</td>
<td align="left" width="63%">
Returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getmatchthreadid">GetMatchThreadId</a>
</td>
<td align="left" width="63%">
Returns the engine thread ID of the thread that can trigger a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getoffset">GetOffset</a>
</td>
<td align="left" width="63%">
Returns the location that triggers a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getoffsetexpression">GetOffsetExpression</a>
</td>
<td align="left" width="63%">
Returns the expression string that evaluates to the location that triggers a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a>
</td>
<td align="left" width="63%">
Returns the parameters for a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getpasscount">GetPassCount</a>
</td>
<td align="left" width="63%">
Returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a>
</td>
<td align="left" width="63%">
Returns the type of the breakpoint and the type of the processor that a breakpoint is set for.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-removeflags">RemoveFlags</a>
</td>
<td align="left" width="63%">
Removes flags from a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setcommand">SetCommand</a>
</td>
<td align="left" width="63%">
Sets the command that is executed when a breakpoint is triggered.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setdataparameters">SetDataParameters</a>
</td>
<td align="left" width="63%">
Sets the parameters for a processor breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setflags">SetFlags</a>
</td>
<td align="left" width="63%">
Sets the flags for a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setmatchthreadid">SetMatchThreadId</a>
</td>
<td align="left" width="63%">
Sets the engine thread ID of the thread that can trigger a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setoffset">SetOffset</a>
</td>
<td align="left" width="63%">
Sets the location that triggers a breakpoint.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setoffsetexpression">SetOffsetExpression</a>
</td>
<td align="left" width="63%">
Sets an expression string that evaluates to the location that triggers a breakpoint.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-setpasscount">SetPassCount</a>
</td>
<td align="left" width="63%">
Sets the number of times that the target must reach the breakpoint location before the breakpoint is triggered.


</td>
</tr>
</table> 


## -remarks



Although <b>IDebugBreakpoint</b> implements the <b>IUnknown</b> interface, the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods are not used to control the lifetime of the breakpoint. Instead, an <b>IDebugBreakpoint</b> object is deleted after the method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removebreakpoint">RemoveBreakpoint</a> is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint2">IDebugBreakpoint2</a>
 

 

