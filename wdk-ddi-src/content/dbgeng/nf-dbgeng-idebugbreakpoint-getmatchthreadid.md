---
UID: NF:dbgeng.IDebugBreakpoint.GetMatchThreadId
title: IDebugBreakpoint::GetMatchThreadId (dbgeng.h)
description: The GetMatchThreadId method returns the engine thread ID of the thread that can trigger a breakpoint.
old-location: debugger\getmatchthreadid.htm
tech.root: debugger
ms.assetid: 0f0f7248-de85-4757-8006-48444af8edac
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint::GetMatchThreadId"]
ms.keywords: ComOther_6a9afca5-8445-48d9-8e28-8d38e6cf2658.xml, GetMatchThreadId, GetMatchThreadId method [Windows Debugging], GetMatchThreadId method [Windows Debugging],IDebugBreakpoint interface, GetMatchThreadId method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetMatchThreadId method, IDebugBreakpoint.GetMatchThreadId, IDebugBreakpoint2 interface [Windows Debugging],GetMatchThreadId method, IDebugBreakpoint2::GetMatchThreadId, IDebugBreakpoint::GetMatchThreadId, dbgeng/IDebugBreakpoint2::GetMatchThreadId, dbgeng/IDebugBreakpoint::GetMatchThreadId, debugger.getmatchthreadid
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
 - IDebugBreakpoint::GetMatchThreadId
 - dbgeng/IDebugBreakpoint::GetMatchThreadId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint.GetMatchThreadId
 - IDebugBreakpoint2.GetMatchThreadId
---

# IDebugBreakpoint::GetMatchThreadId


## -description

The <b>GetMatchThreadId</b> method returns the engine thread ID of the thread that can trigger a breakpoint.

## -parameters

### -param Id 

[out]
The engine thread ID of the thread that can trigger this breakpoint.

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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No specific thread has been set for this breakpoint. Any thread can trigger the breakpoint.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

If you have set a thread for the breakpoint, the breakpoint can be triggered only if that thread hits the breakpoint.  If you have not set a thread , any thread can trigger the breakpoint and <i>Id</i> receives <b>NULL</b>.

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the engine thread ID of the thread that can trigger the breakpoint.

For more information about breakpoint properties, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.