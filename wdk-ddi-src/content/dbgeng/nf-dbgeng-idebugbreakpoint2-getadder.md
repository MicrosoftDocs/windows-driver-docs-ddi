---
UID: NF:dbgeng.IDebugBreakpoint2.GetAdder
title: IDebugBreakpoint2::GetAdder method
author: windows-driver-content
description: The GetAdder method returns the client that owns the breakpoint.
old-location: debugger\getadder.htm
old-project: debugger
ms.assetid: f57abfc5-d6ae-474b-bea9-bfc53dff7f57
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetAdder, GetAdder
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
req.alt-api: IDebugBreakpoint.GetAdder,IDebugBreakpoint2.GetAdder
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugBreakpoint2::GetAdder method



## -description
The <b>GetAdder</b> method returns the client that owns the breakpoint.



## -syntax

````
HRESULT GetAdder(
  [out] PDEBUG_CLIENT *Adder
);
````


## -parameters

### -param Adder [out]

An <a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a> interface pointer to the client object that added the breakpoint.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The client that owns the breakpoint is the client that created the breakpoint by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537856">AddBreakpoint</a> method.  A breakpoint might not have an owner. If a breakpoint does not have an owner, <i>Adder</i> is set to <b>NULL</b>.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>