---
UID: NF:dbgeng.IDebugBreakpoint2.AddFlags
title: IDebugBreakpoint2::AddFlags method
author: windows-driver-content
description: The AddFlags method adds flags to a breakpoint.
old-location: debugger\addflags.htm
old-project: debugger
ms.assetid: 92161111-5e02-4a97-9656-9a297e9ea1af
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::AddFlags, AddFlags
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
req.alt-api: IDebugBreakpoint.AddFlags,IDebugBreakpoint2.AddFlags
req.alt-loc: Dbgeng.h
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

# IDebugBreakpoint2::AddFlags method



## -description
The <b>AddFlags</b> method adds flags to a <a href="debugger.b#breakpoint#breakpoint">breakpoint</a>.



## -syntax

````
HRESULT AddFlags(
  [in] ULONG Flags
);
````


## -parameters

### -param Flags [in]

Additional flags to add to the breakpoint.  <i>Flags</i> is a bit field that is combined together with the existing flags by using a bitwise OR.  For more information about the flag bit field and an explanation of each flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.  You cannot modify the DEBUG_BREAKPOINT_DEFERRED flag in the <a href="debugger.e#engine#engine">engine</a>. This bit in <i>Flags</i> must always be zero.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>