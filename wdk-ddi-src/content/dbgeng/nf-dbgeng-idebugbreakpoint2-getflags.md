---
UID: NF:dbgeng.IDebugBreakpoint2.GetFlags
title: IDebugBreakpoint2::GetFlags method
author: windows-driver-content
description: The GetFlags method returns the flags for a breakpoint.
old-location: debugger\getflags.htm
old-project: debugger
ms.assetid: 0137a872-63e9-4630-86fa-accfaa9b6d6b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetFlags, GetFlags
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
req.alt-api: IDebugBreakpoint.GetFlags,IDebugBreakpoint2.GetFlags
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

# IDebugBreakpoint2::GetFlags method



## -description
The <b>GetFlags</b> method returns the flags for a breakpoint.



## -syntax

````
HRESULT GetFlags(
  [out] PULONG Flags
);
````


## -parameters

### -param Flags [out]

The breakpoint's flags.  For more information about the flag bit field and an explanation of each flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548095">GetParameters</a> method also returns the breakpoint's flags.

For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>