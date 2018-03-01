---
UID: NF:dbgeng.IDebugBreakpoint2.GetParameters
title: IDebugBreakpoint2::GetParameters method
author: windows-driver-content
description: The GetParameters method returns the parameters for a breakpoint.
old-location: debugger\getparameters.htm
old-project: debugger
ms.assetid: 6b0e2a3d-2a62-4a79-a4e1-03168277caec
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ComOther_1e2f7a47-0f38-492a-a8b2-9eaa124a2f20.xml, GetParameters method [Windows Debugging], GetParameters method [Windows Debugging], IDebugBreakpoint interface, GetParameters method [Windows Debugging], IDebugBreakpoint2 interface, GetParameters,IDebugBreakpoint2.GetParameters, IDebugBreakpoint interface [Windows Debugging], GetParameters method, IDebugBreakpoint2, IDebugBreakpoint2 interface [Windows Debugging], GetParameters method, IDebugBreakpoint2::GetParameters, IDebugBreakpoint::GetParameters, dbgeng/IDebugBreakpoint2::GetParameters, dbgeng/IDebugBreakpoint::GetParameters, debugger.getparameters
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
req.lib: dbgeng.h
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
-	IDebugBreakpoint.GetParameters
-	IDebugBreakpoint2.GetParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
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
</table>
 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.




## -remarks



The <b>GetParameters</b> method is a convenience method that returns most of the parameters that the other <a href="..\dbgeng\nn-dbgeng-idebugbreakpoint.md">IDebugBreakpoint</a> methods return.

For a list of the parameters and flags that this method retrieves, and for other ways to read and write these parameters and flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.



