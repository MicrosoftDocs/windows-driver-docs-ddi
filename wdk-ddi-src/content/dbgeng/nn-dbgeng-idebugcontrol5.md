---
UID: NN:dbgeng.IDebugControl5
title: IDebugControl5 (dbgeng.h)
description: IDebugControl5 interface
old-location: debugger\idebugcontrol5.htm
tech.root: debugger
ms.assetid: 6C358D49-970D-4687-B16E-7D1B44CB0A8E
ms.date: 05/03/2018
ms.keywords: IDebugControl5, IDebugControl5 interface [Windows Debugging], IDebugControl5 interface [Windows Debugging],described, dbgeng/IDebugControl5, debugger.idebugcontrol5
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugControl5"
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
- IDebugControl5
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl5 interface


## -description





## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl5</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>. <b>IDebugControl5</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugControl5</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getbreakpointbyguid">GetBreakpointByGuid</a>
</td>
<td align="left" width="63%">
The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getcontextstacktraceex">GetContextStackTraceEx</a>
</td>
<td align="left" width="63%">
The GetContextStackTraceEx method returns the frames at the top of the call stack, starting with an arbitrary <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/changing-contexts">register context</a> and returning the reconstructed register context for each stack frame. The GetContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-getstacktraceex">GetStackTraceEx</a>
</td>
<td align="left" width="63%">
The GetStackTraceEx method returns the frames at the top of the specified call stack. The GetStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-outputcontextstacktraceex">OutputContextStackTraceEx</a>
</td>
<td align="left" width="63%">
The OutputContextStackTraceEx method prints the call stack specified by an array of stack frames and corresponding register contexts. The OutputContextStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol5-outputstacktraceex">OutputStackTraceEx</a>
</td>
<td align="left" width="63%">
The OutputStackTraceEx method outputs either the supplied stack frame or the current stack frames.   The OutputStackTraceEx method provides inline frame support. For more information about working with inline functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-optimized-code-and-inline-functions-external">Debugging Optimized Code and Inline Functions</a>.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

