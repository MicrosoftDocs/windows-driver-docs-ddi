---
UID: NF:dbgeng.IDebugBreakpoint2.GetOffset
title: IDebugBreakpoint2::GetOffset method
author: windows-driver-content
description: The GetOffset method returns the location that triggers a breakpoint.
old-location: debugger\getoffset.htm
old-project: debugger
ms.assetid: 7da401c9-10c1-4a2b-91ea-c0f9f58fd87a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetOffset, GetOffset
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
req.alt-api: IDebugBreakpoint.GetOffset,IDebugBreakpoint2.GetOffset
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

# IDebugBreakpoint2::GetOffset method



## -description
The <b>GetOffset</b> method returns the location that triggers a breakpoint.



## -syntax

````
HRESULT GetOffset(
  [out] PULONG64 Offset
);
````


## -parameters

### -param Offset [out]

The location on the target that triggers the breakpoint.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The breakpoint is deferred and does not currently specify a location in the target's memory address space. To determine the breakpoint location in this case, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548048">GetOffsetExpression</a>.

 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the location that triggers a breakpoint.

For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>