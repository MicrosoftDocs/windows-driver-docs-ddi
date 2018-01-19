---
UID: NF:dbgeng.IDebugBreakpoint2.GetParameters
title: IDebugBreakpoint2::GetParameters method
author: windows-driver-content
description: The GetParameters method returns the parameters for a breakpoint.
old-location: debugger\getparameters.htm
old-project: debugger
ms.assetid: 6b0e2a3d-2a62-4a79-a4e1-03168277caec
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetParameters, GetParameters
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
req.alt-api: IDebugBreakpoint.GetParameters,IDebugBreakpoint2.GetParameters
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

# IDebugBreakpoint2::GetParameters method



## -description
The <b>GetParameters</b> method returns the parameters for a breakpoint.



## -syntax

````
HRESULT GetParameters(
  [out] PDEBUG_BREAKPOINT_PARAMETERS Params
);
````


## -parameters

### -param Params [out]

The breakpoint's parameters.  For more information about the parameters, see <a href="..\dbgeng\ns-dbgeng-_debug_breakpoint_parameters.md">DEBUG_BREAKPOINT_PARAMETERS</a>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The <b>GetParameters</b> method is a convenience method that returns most of the parameters that the other <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> methods return.

For a list of the parameters and flags that this method retrieves, and for other ways to read and write these parameters and flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>