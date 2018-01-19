---
UID: NF:dbgeng.IDebugBreakpoint2.SetOffset
title: IDebugBreakpoint2::SetOffset method
author: windows-driver-content
description: The SetOffset method sets the location that triggers a breakpoint.
old-location: debugger\setoffset.htm
old-project: debugger
ms.assetid: 25898500-f16e-4838-854f-5eb299727e2b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::SetOffset, SetOffset
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
req.alt-api: IDebugBreakpoint.SetOffset,IDebugBreakpoint2.SetOffset
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

# IDebugBreakpoint2::SetOffset method



## -description
The <b>SetOffset</b> method sets the location that triggers a breakpoint.



## -syntax

````
HRESULT SetOffset(
  [in] ULONG64 Offset
);
````


## -parameters

### -param Offset [in]

The location on the target that triggers the breakpoint.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>The breakpoint is deferred.

 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>