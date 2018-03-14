---
UID: NF:dbgeng.IDebugBreakpoint.SetMatchThreadId
title: IDebugBreakpoint::SetMatchThreadId method
author: windows-driver-content
description: The SetMatchThreadId method sets the engine thread ID of the thread that can trigger a breakpoint.
old-location: debugger\setmatchthreadid.htm
old-project: debugger
ms.assetid: 66170e28-24db-4125-bd4e-ef07e8e82e79
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_5100cd0c-7d69-4210-9d32-ca1e9bd321aa.xml, IDebugBreakpoint, IDebugBreakpoint interface [Windows Debugging], SetMatchThreadId method, IDebugBreakpoint2 interface [Windows Debugging], SetMatchThreadId method, IDebugBreakpoint2::SetMatchThreadId, IDebugBreakpoint::SetMatchThreadId, SetMatchThreadId method [Windows Debugging], SetMatchThreadId method [Windows Debugging], IDebugBreakpoint interface, SetMatchThreadId method [Windows Debugging], IDebugBreakpoint2 interface, SetMatchThreadId,IDebugBreakpoint.SetMatchThreadId, dbgeng/IDebugBreakpoint2::SetMatchThreadId, dbgeng/IDebugBreakpoint::SetMatchThreadId, debugger.setmatchthreadid
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugBreakpoint.SetMatchThreadId
-	IDebugBreakpoint2.SetMatchThreadId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint::SetMatchThreadId method


## -description


The <b>SetMatchThreadId</b> method sets the engine thread ID of the thread that can trigger a breakpoint.


## -syntax


````
HRESULT SetMatchThreadId(
  [in] ULONG Thread
);
````


## -parameters




### -param Thread [in]

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
The thread that <i>Thread</i> specifies could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The target is in a kernel and the breakpoint is a processor breakpoint.  Processor breakpoints cannot be limited to threads in kernel mode.

</td>
</tr>
</table>
 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



If you have set a thread for the breakpoint, the breakpoint can be triggered only if that thread hits the breakpoint.  If you have not set a thread, any thread can trigger the breakpoint.

If you have set a thread, you can remove the setting by setting <i>Id</i> to DEBUG_ANY_ID.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.



